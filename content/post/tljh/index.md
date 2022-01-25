---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Setting a JupyterHub for the lab"
subtitle: ""
summary: "Just a record of how we set up the JupyterHub for teaching/research in the lab."
authors: ["P. Aristidou"]
tags: []
categories: ['blog']
date: 2020-06-29T00:00:48+03:00
lastmod: 2021-01-29T00:00:48+03:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: true

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
# 
projects: []
---

JupyterHub is a great platform for getting students to easily use Jupyter notebooks while avoiding the fuss of having them install on individual computers and maintaining. In our lab we use [The Littlest JupyterHub](https://tljh.jupyter.org/) to install JupyterHub since we have few users. You can install to cloud instances or to servers you own. There are guidelines at [this link](https://tljh.jupyter.org/en/latest/install/index.html) for the most common platforms. We install on [our own server](https://sps.cut.ac.cy/jhub), so we assume that you have an Ubuntu-based server with remote ssh access and admin rights.

## Installation process

First, we upgare the server and install python3, curl, git, and xorg (not necessary for JupyterHub but we use it to get GUI apps remotely)

```bash
sudo apt-get update
sudo apt-get upgrade -y
sudo apt-get install python3 python3-dev git curl xorg
```

If apache is enabled on the server. we disable it. It interferes with the JupyterHub shipped traefik. If you need to run both, I have no idea since I didn't need to :)

```bash
sudo systemctl status apache2
sudo systemctl disable apache2
sudo apt remove apache2
```

We download and install anaconda. You can head to https://repo.anaconda.com/archive/ and see which one is the latest and replace the _2020.11_ part of the link below. When asked if you want to add conda to .bashrc, say yes. I like the flexibility of conda VS the deb packages when it comes to python.

```bash
cd /tmp
curl -O https://repo.anaconda.com/archive/Anaconda3-2020.11-Linux-x86_64.sh
bash Anaconda3-2020.11-Linux-x86_64.sh
cd ~
source ~/.bashrc
conda info
```

If you need to, create a sudo account to link to JupyterHub.

```bash
adduser apetros
usermod -aG sudo apetros
```

Then, install JupyterHub with tljh.

```bash
curl -L https://tljh.jupyter.org/bootstrap.py | sudo -E python3 - --admin apetros
```

Then, we fine tune the server parameters to limit the resources for the students. Check [this link](https://tljh.jupyter.org/en/latest/topic/tljh-config.html) for details.

```bash
sudo tljh-config set limits.memory 6G
sudo tljh-config set limits.cpu 1
sudo tljh-config set user_environment.default_app jupyterlab
sudo tljh-config set services.cull.every 600
sudo tljh-config set services.cull.timeout 1800
sudo tljh-config reload 
```

Finally, we set up https. Replace _your-email_ and _your-domain_ with your own details.

```bash
sudo tljh-config set https.enabled true
sudo tljh-config set https.letsencrypt.email your_email
sudo tljh-config add-item https.letsencrypt.domains your_domain
sudo tljh-config reload proxy
```

## Post installation

If JupyterHub is up and running, then open a terminal and install the packages needed for you students. In my courses I use the following:

- *Pandas*: For energy analytics.
- *pyomo, ipopt, coincbc*: For optimization problems (economic dispatch, unit commitment, etc.)
- *pandapower*: Power-flow analysis and short-circuit analysis
- *pypsa, ramses*: Power-system dynamics



```bash
sudo -E conda install -c conda-forge scipy numpy pandas numba matplotlib pyomo ipopt glpk coincbc pypsa networkx cartopy 
sudo -E pip install pandapower
sudo -E conda install -c apetros pyramses
```

### PyRAMSES installation

[pyramses](https://pyramses.netlify.app/) needs to also install some runtime libraries from Intel Redistributable and set them in the LD_LIBRARY_PATH of JupyterHub.

First, we set up and install the [Intel Redistributable libraries](https://software.intel.com/content/www/us/en/develop/articles/installing-intel-parallel-studio-xe-runtime-2020-using-apt-repository.html). We ssh **on the server** and run:

```bash
sudo apt-key add GPG-PUB-KEY-INTEL-PSXE-RUNTIME-2020
cd /etc/apt/sources.list.d
sudo nano intel-psxe-runtime-2020.list
```

We append the following line:

```bash
deb https://apt.repos.intel.com/2020 intel-psxe-runtime main
```

Then, we update and install the redistributable libraries:

```bash
sudo apt-get update
sudo apt-get install intel-ifort-runtime intel-mkl-runtime
```

We create a py file that will add the path to the runtime libraries to all the users in JupyterHub. We add this file under `/opt/tljh/config/jupyterhub_config.d/`. Opent the file:

```bash
sudo nano /opt/tljh/config/jupyterhub_config.d/path.py
```

Add the following text (if you used the standard location for the Intel Libraries):

```bash
c.Spawner.environment = {
'LD_LIBRARY_PATH': '/opt/intel/psxe_runtime/linux/compiler/lib/intel64_lin:/opt/intel/psxe_runtime/linux/mkl/lib/intel64_lin'
}
```
Save, close and reload the hub:

```bash
sudo tljh-config reload
sudo tljh-config reload proxy
```

This should fix the necessary dependencies for ramses. You can click [here](https://sps.cut.ac.cy/Nordic_JhubStart) to clone the [repository with Nordic system](https://github.com/SPS-L/Nordic_JhubStart) to the lab's server and get you started.



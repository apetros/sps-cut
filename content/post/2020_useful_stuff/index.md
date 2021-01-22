---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Things to remember"
subtitle: ""
summary: "Just a collection of useful things for me to find again later."
authors: ["P. Aristidou"]
tags: []
categories: ['Open positions']
date: 2020-06-29T00:00:48+03:00
lastmod: 2020-06-29T00:00:48+03:00
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

## Scripts

### Batch convert PDF to images in Ubuntu

First, install poppler-utils:

  sudo apt-get install poppler-utils

Then, move to the folder with the PDFs and execute:

  for i in *.pdf; do pdftoppm -jpeg -r 300 "$i" "$i".jpg; done


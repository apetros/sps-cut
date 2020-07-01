+++
title = "Time-domain simulation of large electric power systems using domain-decomposition and parallel processing methods"
date = "2015-06-01"
authors = ["P. Aristidou"]
tags = []
publication_types = ["7"]
publication = "_PhD thesis at Université de Liège_"
publication_short = ""
abstract = "Dynamic simulation studies are used to analyze the behavior of power systems after a disturbance has occurred. Over the last decades, they have become indispensable to anyone involved in power system planning, control, operation, and security. Transmission system operators depend on fast and accurate dynamic simulations to train their personnel, analyze large sets of scenarios, assess the security of the network in real-time, and schedule the day ahead operation. In addition, those designing future power systems depend on dynamic simulations to evaluate proposed reinforcements, whether these involve adding new transmission lines, increasing renewable energy sources, or implementing new control schemes.   Even though almost all computers are now parallel, power system dynamic simulators are still based on monolithic, circuit-based, single-process algorithms. This is mainly due to legacy code, written in the 80's, that is still today in the core of the most important commercial tools and does not allow them to fully exploit the parallel computational resources of modern computers.   In this thesis, two parallel algorithms belonging to the family of Domain Decomposition Methods are developed to tackle the computational complexity of power system dynamic simulations. The first proposed algorithm is focused on accelerating the dynamic simulation of large interconnected systems; while, the second algorithm aims at accelerating dynamic simulations of large combined transmission and distribution systems.   Both proposed algorithms employ non-overlapping decomposition schemes to partition the power system model and expose parallelism. Then, divide-and-conquer techniques are utilized and adapted to exploit this parallelism. These algorithms allow the full usage of parallel processing resources available in modern, inexpensive, multi-core machines to accelerate the dynamic simulations. In addition, some numerical acceleration techniques are proposed to further speed-up the parallel simulations with little or no impact on accuracy.   All the techniques proposed and developed in this thesis have been thoroughly tested on academic systems, a large real-life system, and a realistic system representative of the continental European synchronous grid. The investigations were performed on a large multi-core machine, set up for the needs of this work, as well as on two multi-core laptops computers."
summary = ""
featured = false
projects = ["mod sim","pyramses"]
slides = ""
url_pdf = "/publication/2015ThAristidou/manuscript.pdf"
doi = "10.13140/RG.2.1.1119.1527"
url_code = ""
url_dataset = ""
url_poster = ""
url_slides = ""
url_source = ""
url_video = ""
math = true
highlight = true
[image]
image = ""
caption = ""
+++


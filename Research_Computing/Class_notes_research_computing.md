
#  Research computing - tools and resources 
This module is part of PHYS 516. The goal is to provide an overview of research computing tools and resources, 

* What are the challenges in research computing?
* What different types of resources are available?
* How to organize computational work? Since all research work is computational these days - how to organize your research work?

#### Disclaimer
* This 1.5hr module is intended to give you an overview of tools, resources and best practice experience. We do not have enough time to go into detail. If there is interest to follow-up any of the topics covered today in more detail, let the course coordinator know. 
* These are my views, based on my experience. Treat them as ideas and one possible way of approaching things. There are clearly other ways to go about research computing. Talk to different people to build your repertoire.


#### What to emphasize in this module
* the role of collaboration
    - super-important, how to work together on the same data/code etc?
    - $\rightarrow$ the cloud and distributed version control (DVC), [git](https://git-scm.com/book/en/v2)
* reproducability of science
    - virtualization 
    - DVC (distributed version control, git)
* storage strategy
    - what types of storage is needed, and what is available

## How scientists use computers

### Examples cyber challenge

#### Data deluge
* data example 3D hydro simulations of stars: one dump 4 quantities $1536^3$ x 8 byte x 4 quantities = 115GB - disk read (100MB/s) **20min**, network transport (20MB/s) **1.6hrs**
* 500 time steps = 57.5TB - disk read 6.6d, network transport 33d
* large data sets require remote access

#### Complexity
* multiphysics, multimessenger, multiwavelength, and multiepoch
* complex data interactions and collaborative cyber- research environments, data fusion 

#### Research data and collaboration
* research data management - in reality means combining access to data, data-specific analytics tools and capability to execute analytic tools to data
* sharing work flows, authentication and access models 

#### Reproducibility of science
* legacy software, tools, and workflows 
* reproducibility of science

### Components of research computing
It is useful to distinguish clearly different components of research computing.


#### Data
Data is generated all the time when experiments or simulations are carried out. Confronting both with each other or with models involves:

* move, store, archive data
* analyse data 
* model data
* statistics (see below)
* visualise data

#### Simulation

If we understand the physics then the **correct** (need to talk about that more ...) solution of the **appropriate** laws of nature, such as the _Conservation Laws_ of energy, momentum, mass, charge, etc, should resemble aspects of the real world as revealed through observational data.

Real-world problems have some challenges though:

* multi-physics: include simultaneously different physics components, such as conservation laws of mass, momentum and energy as well as the Maxwell equations for a magneto-hydrodynamics problem
* multi-scale: processes on vastly different temporal and spatial scales are simultaneously important and interacting

Numerical simulations combine the above challenges in ways impossible with purely analytical approaches. The simulations of high quality are numerical experiments that reveal the complex and non-linear behaviour of the appropriate combination of physics laws. This approach provides scientific insight in ways that complement traditional theory and physical experimental.

**Note:** models and simulations are different things!

#### Modeling
In order to break down complexity physicists often try to _model_ physics processes based on experimental of numerical simulation data. Modeling of data involves a lot of statics, fitting and ideally the model is physics based. More recently powerful models are derived from machine learning approaches. This is clearly an important emerging field, with lots of potential and interesting knowledge theory challenges; for example the recently raised [concern about reproducibility crisis of ML research](https://www.hpcwire.com/2019/02/19/machine-learning-reproducability-crisis-science/). Keep critically tuned into that conversation!

Simulations and modeling often involve ....

#### Numerical analysis

Solve mathematical problems numerically. Examples include: 

* integrating a function or differential equation
* finding the root of an equation
* solving a linear algebra problem with many variables

Fortunately, these days there are lots of really good _canned_ solutions, e.g. for FFTs. But there is [scipy.fftpack.fft](https://docs.scipy.org/doc/scipy/reference/generated/scipy.fftpack.fft.html#scipy.fftpack.fft) and [numpy.fft.fft](https://docs.scipy.org/doc/numpy/reference/generated/numpy.fft.fft.html#numpy.fft.fft) - which one to use?). It is useful to undertstand the underlying algotithms, and [Numerical Recipes](http://voyager.library.uvic.ca/vwebv/holdingsInfo?bibId=687673) is still the foundational starting point.


Numerical analysis is to be distinguished from ...

#### Symbolic computing

Despite the availability of powerful simulation codes and libraries to rapidly deploy proven methods in numerical analysis, from time to time we need to be able to work with complicated mathematics in an analytical fashion. The laws of physics come in the language of mathematics, and we need to _speak_ that language to understand physics and to write down new physics insights. Symbolic computing is a powerful way to support that. To get started consult the Python module [Sympy](https://www.sympy.org/en/index.html).



### Utilities
There are numerous tasks that we have to be familiar with, and that are common to more than one of the above roles. These utilities enable science and any type of quantitative analysis.

1. reading and writing data (IO) 
2. visualizing, plotting data
3. programming
3. (distributed) version control
4. documentation and sharing software
5. networking & storage
6. using libraries (e.g. for numerical analysis!)
8. parallel/threaded computing
9. debugging techniques

Our second-year computational physics course [PHYS 248](https://github.com/UVic-CompPhys/physmath248-2018) introduces many of the key concepts. Check back from time to time as this course is constantly evolving reflecting new developments.



## Case study

* Large 3D hydrodynamic simulations (show slides, algorithmic compression, data staging) 
* Example of modeling (vs. simulation)

## The hardware
* Your personal equipment: laptop & big screen (size vs. pixels)
* Desktop (no one uses those anymore)
* Workstation in sever room (no one uses those either, just a little exagerated)
* Virtual server in the cloud 
    - [Compute Canada cloud](https://www.computecanada.ca/research-portal/national-services/compute-canada-cloud)
    - [Google cloud platform](https://console.cloud.google.com)
* the big iron: massively parallel clusters, e.g. cedar and niagara in Compute Canada
    - Niagara demonstration

### Resource allocations
* Compute Canada deadline is coming up; astronomers have grouped together and obtain an ARC group allocation.
* One application for a group, usually lead by the group leader; not for individuals.
* Everybody has default allocation! Get an account and try it out!

### What to put on that cloud hardware?
* VNC (demo)
* jupyterhub
    - Cyberhubs slides

## Data safety and security

### Security
1. Research data in physics - usually we do not have security concerns, no patents, no sensitive data.
2. However, be aware when data security issues may arise (usually when copyright, intellectual property or personal data is involved).
2. Be aware of copyright issues, e.g. in presentations that you put online.
3. TAs: do not store any type of personal data on unencrypted volumes.
4. Stricktly separate your personal from your professional computing.
5. A word about email: consider them public documents.
6. OS and system updates, phishing, passwords.

### Safety
1. Backup, backup, and then backup - sensibly!
2. What to backup and where, what is your personal data management plan?
3. $\frac{\mathrm{Risk}}{\mathrm{Effort}} = \mathrm{const.}$
4. When to backup the presentation you are just working on?

## Languages
* Markdown, Latex [Overleaf](https://www.overleaf.com)
* Python (interpreted languages)
    - [PHYS248 Intro Computational Physics](https://github.com/UVic-CompPhys/physmath248-2018)
    - Anaconda distribution, with conda environement and package management
    - [Enthought distribution](http://docs.enthought.com/edm/index.html)
* Fortran, C (compiled languages)
* Bash (shell)
    - `.bashrc`
    - one-line scripts: `for name in Paul Anne Carla Henry Lisa; do echo Hallo $name > $name.txt; done`
    - substantial scripts, [example](https://github.com/cyberlaboratories/astrohubs/blob/master/mesahub/install_mesa.sh)

## Collaboration 

### Version control 
* subversion (outdated)
* git
    - Gitlab, e.g. [ARC gitlab server](http://arc-gitlab.phys.uvic.ca) allows unlimited private repositories (see Stephenson's [ARC Info Repo](http://arc-gitlab.phys.uvic.ca/syang314/arc-info)).
    - Commercial: [Github](https://github.com/), [Bitbucket](https://bitbucket.org)
        
### Communicating
* Skype, Zoom, Vidyo (WestGrid)
* Slack (have to pay eventually); better: Mattermost, e.g. [ARC mattermost](http://arc-gitlab.phys.uvic.ca)
* A word about email: don't use it.
* Twitter yes - Facebook no (my bias)

## Access, human-machine interface
* Terminal
    - editor: emacs of vim
* VNC: a virtual desktop (For ARC students see Stephenson's [ARC Info Repo](http://arc-gitlab.phys.uvic.ca/syang314/arc-info)).
* Jupyterhub
    - You can easily build your own custom Jupyterhub server in the cloud. You can use [Cyberhubs](http://iopscience.iop.org/article/10.3847/1538-4365/aab777/meta), and everything you need, including setup-by-step instructions are available on this [Cyberlaboratories Github repo](https://github.com/cyberlaboratories). Cyberhubs relies on the [Docker](https://www.docker.com) virtualization technology. Prebuilt [cyberhubs docker images](https://cloud.docker.com/u/cyberhubs/repository/registry-1.docker.io/cyberhubs) are available for deployment on the Compute Canada cloud. 
    - ARC provides group access to jupyterserver [ARC astrohub](), authentication via ARC's gitlab server. 

## Storage
* External hard drive (8TB $189 on amazon.ca)
* OwnCloud (from WestGrid), Google Drive, DropBox
* Your best friend: `sshfs` - mount external storage connected to machines that you can reach vis `ssh` on your laptop or cloud server.
* Server storage 
    - On ComputeCanada, 25TB  temporary storage for every account holder
    - On each ComputeCanada machine some combination of scratch, project and tape (hpss, nearline) storage; understand the different roles these different storage facilities take.
    - Case study: Niagara
* Very best friend: [Globus](http://www.globus.org) (check out Globus Personal Connect) allows fast and reliable transfer of large amounts of data.
* _Publish_ digital objects: [Zenodo](http://zenodo.org) assigns DOI for digitial objects (Talk slides, posters, data sets) up to 50GB. Connects to GitHub.  

## Virtualization
* VirtualBox
* Docker

## Prime directive
1. Everything can only be in one place.

## Workflow example



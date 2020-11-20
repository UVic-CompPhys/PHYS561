
#  Research computing - tools and resources 
This module is part of PHYS 516. The goal is to provide an overview of research computing tools and resources, 

* What are the challenges in research computing?
  * _Math is the language in which physics and astronomy is expressed_ .... this needs to be updated in your thinking: _Math and <u>computation</u> is the language in which physics and astronomy is expressed_
  * If you are not literate in that language of *computation* it is as if you live in a foreign country and you want to make friends but have skipped classes in language school - a foggy experience. 
* What different types of resources exit and are available?
* How to organize computational work? Since all research work is computational these days - how to organize your research work?

#### Disclaimer
* This 1.5hr module is intended to give you an overview of tools, resources and best practice experience. We do not have enough time to go into detail.
* These are my views, based on my experience. Treat them as ideas and one possible way of approaching things. There are clearly other ways to go about research computing. Talk to different people to build your repertoire.
* I am a computational astrophysicist. With my group and collaborators I am involved in performing the largest stellar hydrodynamics simulations in the community ... as an example, let's have a look at what I am doing right now .... 


#### What to emphasize in this module
* the role of collaboration; super-important, how to work together on the same data/code etc?
* reproducability of science
* Data storage and movement strategies
* threading, virtualization, DVC (distributed version control, git)



##  Cyber challenges

### Data deluge
* data example 3D hydro simulations of stars: one dump 4 quantities $1536^3$ x 8 byte x 4 quantities = 115GB - disk read (100MB/s) **20min**, network transport (20MB/s) **1.6hrs**
* 500 time steps = 57.5TB - disk read 6.6d, network transport 33d
* large data sets require remote access

### Complexity
* multiphysics, multimessenger, multiwavelength, and multiepoch
* complex data interactions and collaborative cyber- research environments, data fusion 

### Research data and collaboration
* research data management - in reality means combining access to data, data-specific analytics tools and capability to execute analytic tools to data
* sharing work flows, authentication and access models 

### Reproducibility of science
* legacy software, tools, and workflows 
* reproducibility of science

## Components of research computing
It is useful to distinguish clearly different components of research computing.


### Data
Data is generated all the time when experiments or simulations are carried out. Confronting both with each other or with models involves:

* create, move, store, archive data
* analyse data 
* model data
* statistics
* visualise data

### Simulation

If we understand the physics then the **correct**  solution of the **appropriate** laws of nature, such as the _Conservation Laws_ of energy, momentum, mass, charge, etc, should resemble aspects of the real world as revealed through observational data.

What does **correct** mean? 
* Verification: do you solve the equations right? $\rightarrow$ code comparison, compare with analytical solution
* Validation: do you solve the right equations? $\rightarrow$ compare with real data, observations

**Real-world problems** have some challenges though:

* Multi-physics: include simultaneously different physics components, such as conservation laws of mass, momentum and energy as well as the Maxwell equations for a magneto-hydrodynamics problem
* Multi-scale: processes on vastly different temporal and spatial scales are simultaneously important and interacting

Numerical simulations combine the above challenges in ways impossible with purely analytical approaches. The simulations of high quality are **numerical experiments** that reveal the complex and non-linear behaviour of the appropriate combination of physics laws. This approach provides scientific insight in ways that complement traditional theory and physical experimental.

**Note:** models and simulations are different things!

### Modeling
In order to break down complexity physicists often try to _model_ physics processes based on experimental of numerical simulation data. Modeling of data involves a lot of statics, fitting and ideally the model is physics based. More recently powerful models are derived from machine learning approaches. This is clearly an important emerging field, with lots of potential and interesting knowledge theory challenges; for example the recently raised [concern about reproducibility crisis of ML research](https://www.hpcwire.com/2019/02/19/machine-learning-reproducability-crisis-science/). Keep critically tuned into that conversation!

Simulations and modeling often involve ....

#### Numerical analysis

Solve mathematical problems numerically. Examples include: 

* integrating a function or differential equation
* finding the root of an equation
* solving a linear algebra problem with many variables

Fortunately, these days there are lots of really good _canned_ solutions, e.g. for FFTs. But there is [scipy.fftpack.fft](https://docs.scipy.org/doc/scipy/reference/generated/scipy.fftpack.fft.html#scipy.fftpack.fft) and [numpy.fft.fft](https://docs.scipy.org/doc/numpy/reference/generated/numpy.fft.fft.html#numpy.fft.fft) - which one to use?. It is useful to undertstand the underlying algotithms, and [Numerical Recipes](http://voyager.library.uvic.ca/vwebv/holdingsInfo?bibId=687673) is still the foundational starting point.


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
* Compute Canada provides a variety of computing resources
  * get a Compute Canada account - every user has a default allocation on all systems - try it
  * astronomers have grouped together and obtain an ARC group allocation ready to use, includes 500 core-years on cedar and 80 virtual cpus on the Arbutus cloud that can be configured into various servers
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
* Be on the lookout for new developments, e.g. Julia, but be aware of cost of adoption

## Threading

* For the past 10 years individual cores do not get faster anymore - but chip designers pack more cores on a CPU, e.g. Niagara has 40 cores per node, plus hyberthreading 
* These cores per node share the node memory
* If you don't use these cores per nodes (even on your laptop) in your everyday computing you will be left behind, computationally speaking
* Be `nice`

### Bash

* gnu utility `parallel`
* `xargs`

## Python 

* `multiprocessing` 

### Fortran/C

Two paradigms:

* OpenMP - shared memory 
* MPI - message-passing interface (most commonly used implementation: OpenMPI)
* You can 

## Collaboration 

### Version control 
* subversion (outdated)
* git
    - Gitlab, e.g. [ARC gitlab server](http://arc-gitlab.phys.uvic.ca) allows unlimited private repositories (see Stephenson's [ARC Info Repo](http://arc-gitlab.phys.uvic.ca/syang314/arc-info)).
    - Commercial: [Github](https://github.com/), [Bitbucket](https://bitbucket.org)
      
### Communicating
* Skype, Zoom
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
* Very best friend: [Globus](http://www.globus.org) 
    * Globus web interface and Globus Command Line tools
    * Globus Personal Connect allows fast and reliable transfer of large amounts of data
    * Through our ARC or your supervisor's Compute Canada account get access to Globus Plus to create your own endpoints
* _Publish_ digital objects: [Zenodo](http://zenodo.org) assigns DOI for digitial objects (Talk slides, posters, data sets) up to 50GB. Connects to GitHub.  

## Virtualization
* (VirtualBox)
* Docker

## Examples

### Threaded bash script

```shell
# tiled_movie_xvariables.sh                                                                                                                                                  
# FH, 1 May 2020                                                                                                                                                             

# Add for a range of dumps and one run label to images of 3                                                                                                                  
# quantities, tyle them and finally make movie for x variables                                                                                                               

source ~/.bashrc

# parameters                                                                                                                                                                 

export dirnames="Vradial Vhorizl vortmag"
export run=M111

export dump_start=100
export dump_end=1066

export num_threads=15

# don't change anything below                                                                                                                                                

cat << %% > process_and_glue.sh
#set -x                                                                                                                                                                      
dump=\$1
echo process_and_glue DUMP: \$dump
for dirn in $dirnames
do
    convert $run/png/\$dirn/HcoreM025Z0-*\$dump.png \
        -gravity center -shave 200x200 \
        -gravity south -pointsize 60 -font Bookman-Demi \
        -stroke white -annotate 0 \$dirn \
        tmp\$dirn\$dump.png
done
nice -n 10 montage  -geometry 1024x1024 tmp*\$dump.png tile\$dump.png
rm -f tmp*\$dump.png
%%
chmod u+x process_and_glue.sh

echo $(seq -f "%04g"  $dump_start $dump_end) | \
     nice -n 19 xargs -n 1 -P $num_threads   ./process_and_glue.sh
rm process_and_glue.sh

cedar_env                 # provides ffmpeg                                                                                                                                  

ffmpeg  -framerate 10   -y -f image2  -pattern_type glob -i "tile*.png" -preset slow -crf 18  -c:v libx264 -b:v 12000k  -pix_fmt yuv420p  $run-vortVht.mp4

rm tile*.png

```





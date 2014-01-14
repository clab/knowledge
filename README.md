# clab knowledge

> to know, is to know that you know nothing. that is the meaning of true knowledge. -- socrates

## meta
* purpose: this repository is meant to share knowledge (well, and pieces of information too) which is not suitable for sharing elsewhere, among members of clab. 
* editing: use the "markdown" format to edit this file. help can be found at http://stackoverflow.com/editing-help . Feel free to create a new file if need be, but make sure to link to it from this one for easy access. [GFL guidelines]  (https://github.com/brendano/gfl_syntax/blob/master/guidelines/guidelines.md) is a good example of a nicely written .md file, just in case you're not familiar with the Markdown script.

## papers we recently read
* 2013-10-22: [Adaptor grammars for learning non-concatenative morphology] (http://aclweb.org/anthology/D/D13/D13-1034.pdf). 2013. Jan Botha and Phil Blunsom. In proc. of EMNLP.
* 2013-11-26: [Diverse M-Best Solutions in Markov Random Fields] (https://filebox.ece.vt.edu/~dbatra/papers/MBestModes.pdf). 2012. Batra et al. In proc. of Computer Vision–ECCV.
* 2013-12-03: [A fast and simple algorithm for training neural probabilistic language models] (http://www.stats.ox.ac.uk/~teh/research/compling/MniTeh2012a.pdf). 2012. Mnih and Teh. In proc. of ICML.
* 2014-01-21: [Structured Sparsity in Structured Prediction] (http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.228.6262&rep=rep1&type=pdf). 2011. A. F. T. Martins, N. A. Smith, P. M. Q. Aguiar, and M. A. T. Figueiredo

## computational resources

### allegro
* software packages of general interest should be installed at ```allegro:/opt/tools``` and a modulefile (learn more about Environment Modules [here] (http://modules.sourceforge.net/)) should be added at ```allegro:/opt/modulefiles``` so that other people can find it by executing ```module avail```
* corpora can be found at ```allegro:/usr1/corpora```, ```allegro:/cab1/corpora```, ```allegro:/mal1/corpora```, or ```allegro:/mal2/corpora```

### trestles
#### login:
* ```ssh username@login.xsede.org``` providing your xsede.org portal password, followed by ```gsissh trestles```
* ```ssh username@trestles.sdsc.xsede.org``` providing your trestles-specific password. Email help@xsede.org to obtain your autogenerated trestles password, then change it at https://passive.sdsc.edu/
* ```ssh username@trestles-login1.sdsc.edu``` providing your trestles-specific password. This allows you to specify which of trestles' three login servers to use. 

#### software:
find already installed software packages by running ```module avail```

if you can't find a dependency you need by ```module avail```, you can either

* install it yourself in your home directory. 
* ask help@xsede.org to install it for you (especially if it's a generally useful tool); expect delays. also, they don't always agree :-/

#### running jobs:
for trivial jobs (e.g. compiling, bleu) can be directly run on the trestles login machine.

use ```qsub```, specifying one of two queues: ```-q normal``` which gives exclusive access to nodes, or ```-q shared``` which gives shared access to nodes (e.g. allows you to request only 8 out of the 32 cores on a node; useful for running a debugger on the same node). 

you can run interactive jobs as follows ```qsub -I -q normal -l nodes=1:ppn=32,walltime=48:00:00```. 48 is the maximum number of hours you can request for interactive jobs. in order to avoid losing your job if the login server closes your ssh connection (e.g. due to long inactivity), you can login to a specific login server and start a ```/home/diag/glock/user/screen/bin/screen``` session before submitting the ```qsub -I``` job.


#### hardware configurations:
trestle consists of about 10K nodes, each has 32 cores and 64GB of RAM (as well as 120GB of flash disk memory which is much slower than RAM but much faster than regular disk). 

#### where to write files?
```/home/$USER``` (backed up; max 10gb; use for your source code/binaries; don't use for data). note: you would think each user has a home directory by default, but I had to email  help@xsede.org to request one!
```/scratch/$USER/$PBS_JOBID``` (local flash disk, so orders of magnitude faster I/O than regular/network disk space; use for temporary files during the job runtime only; it's wiped off momentarily once the job finishes)
```/oasis/project/nsf/cmu134/$USER/``` for data

#### official documentation
* old: https://www.xsede.org/web/guest/sdsc-trestles
* new: http://www.sdsc.edu/us/resources/trestles/
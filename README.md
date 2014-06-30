# clab knowledge

> to know, is to know that you know nothing. that is the meaning of true knowledge. -- socrates

## meta
* purpose: this repository is meant to share knowledge (well, and pieces of information too) which is not suitable for sharing elsewhere, among members of clab. 
* editing: use the "markdown" format to edit this file. help can be found at http://stackoverflow.com/editing-help . Feel free to create a new file if need be, but make sure to link to it from this one for easy access. [GFL guidelines]  (https://github.com/brendano/gfl_syntax/blob/master/guidelines/guidelines.md) is a good example of a nicely written .md file, just in case you're not familiar with the Markdown script.

## notes about writing
* a paper needs to be organized. here are some tricks for looking at the global structure of your paper: read the subject headings in your paper. do they tell the story you want? read the first sentence or two in each section one after the next, does it tell your paper's story? this advice gets more and more important as your paper gets longer.

## papers for summer reading group 2014
* 2014-05-22: [Dependency grammar induction via bitext projection constraints] (http://dl.acm.org/citation.cfm?id=1687931) K. Ganchev and J. Gillenwater and B. Taskar, 2009. ACL.
* 2014-05-29: [Two Step CCA: A new spectral method for estimating vector models of words](http://www.cis.upenn.edu/~ungar/papers/icml12_2step.pdf) Dhillon et al. (Yes, this is monolingual, but yes, we will discuss a multilingual extension)
* 2014-06-05: [Syntactic Transfer Using a Bilingual Lexicon] (http://www.eecs.berkeley.edu/~gdurrett/DurPauKle_emnlp12.pdf)  G. Durrett, A. Pauls, and D. Klein. EMNLP'12.
* 2014-06-12: [Unsupervised Induction of Cross-lingual Semantic Relations] (http://www.aclweb.org/anthology/D13-1064) M. Lewis and M. Steedman. EMNLP'13
* 2014-06-19: [A New Approach to Lexical Disambiguation of Arabic Text](http://anthology.aclweb.org//D/D10/D10-1071.pdf) R. Shah et al.
* 2014-07-03: [Accurate Language Identification of Twitter Messages](http://www.aclweb.org/anthology/W14-1303) Lui and Baldwin. 
 
## papers for spring 2014
* 2014-02-04: [Structured Sparsity in Structured Prediction] (http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.228.6262&rep=rep1&type=pdf). 2011. A. F. T. Martins, N. A. Smith, P. M. Q. Aguiar, and M. A. T. Figueiredo
* 2014-02-11: [Convolution Kernels for Natural Language] (http://books.nips.cc/papers/files/nips14/AA58.pdf). 2002. Michael Collins and Nigel Duffy
* 2014-03-04: [Large Margin Classification Using the Perceptron Algorithm] (http://cseweb.ucsd.edu/~yfreund/papers/LargeMarginsUsingPerceptron.pdf)
* 2014-03-18: [Unsupervised Induction of Cross-lingual Semantic Relations]
(http://aclweb.org/anthology/D/D13/D13-1064.pdf). Lewis and Steedman, 2013. EMNLP.
* 2014-03-25 [Efﬁcient Inference for Distributions on Permutations] (http://papers.nips.cc/paper/3183-efficient-inference-for-distributions-on-permutations.pdf). Huang, Guestrin and Guibas, 2007. NIPS.
* 2014-04-01 [Combining labeled and unlabeled data with co-training] (http://www.u.arizona.edu/~echan3/539/BlumMitchell98.pdf). Blum and Mitchell, 1998. Conference on Computational Learning Theory.
* 2014-04-08 [Optimal Beam Search for Machine Translation] (http://people.csail.mit.edu/srush/optbeam.pdf). Rush and Chang and Collins.
* 2014-04-15 [A Convolutional Neural Network for Modelling Sentences] (http://nal.co/papers/Kalchbrenner_DCNN_ACL14). Kalchbrenner and Grefenstette and Blunsom. 2014. ACL.


## papers we recently read
* 2013-10-22: [Adaptor grammars for learning non-concatenative morphology] (http://aclweb.org/anthology/D/D13/D13-1034.pdf). 2013. Jan Botha and Phil Blunsom. In proc. of EMNLP.
* 2013-11-26: [Diverse M-Best Solutions in Markov Random Fields] (https://filebox.ece.vt.edu/~dbatra/papers/MBestModes.pdf). 2012. Batra et al. In proc. of Computer Vision–ECCV.
* 2013-12-03: [A fast and simple algorithm for training neural probabilistic language models] (http://www.stats.ox.ac.uk/~teh/research/compling/MniTeh2012a.pdf). 2012. Mnih and Teh. In proc. of ICML.


## computational resources

### allegro
* software packages of general interest should be installed at ```allegro:/opt/tools``` and a modulefile (learn more about Environment Modules [here] (http://modules.sourceforge.net/)) should be added at ```allegro:/opt/modulefiles``` so that other people can find it by executing ```module avail```
* corpora can be found at ```allegro:/usr1/corpora```, ```allegro:/cab1/corpora```, ```allegro:/mal1/corpora```, or ```allegro:/mal2/corpora```
* when something goes wrong with allegro, email help@cs.cmu.edu or call SCS Operations at 412-268-2608 (Open 24 x 7)

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

### stampede
#### login:
* create an account at https://portal.xsede.org/
* send your username to Noah/Chris, they’ll put in the request to add you
* it takes at least 30 minutes to update a user information
* ssh username@login.xsede.org
* gsissh stampede

#### available resources:
* $HOME : 5G, backed-up
* $WORK : 400G, not backed-up, permanent; cdw
* $SCRATCH : 2PB,  not backed-up, high-speed purged after 30 days; cds
* Cluster contains 6,400+nodes, with 32G RAM, and 16 nodes with 1TB RAM
* Max run time (for normal queue): 48h


#### queues:
* available queues: [https://portal.xsede.org/web/xup/tacc-stampede#running-table1](https://portal.xsede.org/web/xup/tacc-stampede#running-table1)
* to see all queues: ```showq```, ```showq | grep $USER```
* interactive shell: ```srun -p development -t 0:30:00 -n 32 --pty /bin/bash -l```
* to run a job: ```sbatch ./DO.run```

DO.run script:
```
#!/bin/bash
#----------------------------------------------------
# Example SLURM job script to run a job
# on TACC's Stampede system.
#----------------------------------------------------
#SBATCH -J test_job       # Job name
#SBATCH -o test_job.o%j   # Name of stdout output file(%j expands to jobId)
#SBATCH -e test_job.o%j   # Name of stderr output file(%j expands to jobId)
#SBATCH -p normal      # Submit to the 'normal' or 'development' queue
#SBATCH -N 1              # Total number of nodes requested (16 cores/node)
#SBATCH -n 1                # Total number of mpi tasks requested
#SBATCH -t 00:30:00         # Run time (hh:mm:ss) - 0.5 hours

# Run the job
./job.sh
```
* to kill a job:  ```scancel <jobId>```

#### applications:
* to see all available modules: module spider
* boost: boost/1.51.0
* to load required modules, and to install software locally or on cluster - same as in trestles

#### documentation:
* [https://portal.xsede.org/web/xup/tacc-stampede](https://portal.xsede.org/web/xup/tacc-stampede)
* man slurm
* man sbatch

## useful tools
### linux
* find the total/used/available on various disks and mount points by running ```df -h```
* check which processes are using shared memory by running ```losf | grep /run/shm```

## current courses to look out for:

### nonlinear optimization (18-799)

four sections:
* Xavier - GHC :: 4307 - Tue, Thu - 09:00AM to 10:20AM
* Ramakrishnan - GHC :: 4101 - Mon, Wed - 04:30PM to 05:50PM
* Cai	- GHC :: 4215 - Tue, Thu - 03:00PM to 04:20PM
* Mengshoel	- INI :: DEC - Tue, Thu - 12:00PM to 01:20PM
* Sankaranarayanan - BH :: A35 - Tue, Thu - 09:00AM to 10:20AM

http://users.isr.ist.utl.pt/~jxavier/NonlinearOptimization18799-2011.html

### how to write fast code (18-645) 

Lane; Chong	- BH :: A51 - Mon - 03:30PM to 04:20PM

http://users.ece.cmu.edu/~pueschel/teaching/18-645-CMU-spring08/course.html

### machine translation (11-731)

http://demo.clab.cs.cmu.edu/sp2014-11731/

## corpora

### LDC corpora

from:	 Alex Rudnicky Alex.Rudnicky@cs.cmu.edu

to:	 LTI-faculty-all <lti-faculty-all@cs.cmu.edu>, "lti-students@cs.cmu.edu" <lti-students@cs.cmu.edu>

date:	 Fri, Jan 24, 2014 at 5:28 PM

subject:	 LDC holdings at LTI

This is a periodic reminder to all that CMU has a (more-or-less) complete collection of Linguistic Data Consortium (LDC) corpora available to everyone, for educational or research purposes, within the University. Due to licensing the collection is only accessible from CMU IP addresses. Go to http://www.speech.cs.cmu.edu/inner/LDC/LDC/table.html
 
Angela Luck angieb@cs.cmu.edu is the official librarian for the collection. You should contact her for lending and other issues.
 
LDC corpora were originally focused on the needs of the speech community, but over time have come to include materials of interest to the text, video and other communities. Until a few years ago acquisition was directly subsidized by the Speech Group (but available to all). More recently this role has been transferred to the LTI, which assesses ongoing contracts that use LDC corpora to meet the annual dues for our LDC membership (btw, we’re a charter member!). The Speech Group continues to pay for the server on which the data are kept.
 
The collection is not complete. One reason is that in the early days, the LDC allowed members only a fixed number of corpora per year. We acquired only those that were relevant to ongoing projects. If you need one of the missing ones, you should be prepared to maybe contribute the cost from your project.
 
Before disk storage became cheap, we only had CDs of corpora. People borrowed these; not everyone turned them in. This is the other reason some corpora are missing. In many cases we have their name; it’s in the square brackets at the entry of the entry description. Feel free to hunt them down or otherwise vocally bring this issue up in their presence. The end goal is to get the disc(s) back into the collection so that the data are available to all.
 
We have some other corpora in the collection. Most of these are in speech (since that’s nominally my field). If you have corpora that might be of interest to other (believe me, they will be), please feel free to contributes copies to this collection.

### other places to look for corpora already acquired
* allegro:/usr0/corpora/
* allegro:/usr1/corpora/
* allegro:/mal1/corpora/
* allegro:/mal2/corpora/ (largest collection)
* allegro:/cab1/corpora/

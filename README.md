fornax-platform.
================

## What is the NASA Astrophysics Science Platform?

Fornax is a compute system in the cloud near to NASA data in the cloud which provides a place where astronomers can do data intensive research with reduced barriers.  The first barrier we remove is the need to install software and deal with packages on your personal computer.  This greatly simplifies the setup and startup for any astronomer who now no longer needs to worry about setting up a python working environment.  Kernels with pre-installed astronomy software are provided upon login to Jupyterlab for all users of Fornax.  The second barrier we remove is the need for every astronomer to buy compute/memory commensurate to data science level projects.  You will no longer need to buy the fastest/ most memory  personal computer.  When you need those capabilities, we will have it ready for you.  When you need to just write code, we have smaller compute ready for that too.  These two things (increased compute/memory and ease of use) should lower the barrier of entry to data science projects for all NASA astronomers.  You no longer need to have an expensive computer, you no longer need to be an expert at installing software, you just need to have an idea!  Lastly, by lowering the barrier to entry, we also increase the potential for reproducibility of large data results in astronomy.  Before, if you were wanting to reproduce some data intensive work done in the literature, it would have been challenging to to have the right compute and setup, now you just need a login....  

* What does it do? (Basic Capabilities)
  * Increased compute,
  * Increased memory,
  * Increased reproducibility,
  * Increased inclusion,
  * Increased ease of use
* Who is it for?
  * US based astronomers
* Limits: What does it not do?
  * How many cores/RAM do I get?
  * How much disk space do I have access to?
  * what restrictions are there to prevent egress charges?

## Getting started
* How do I get an account?
* How to Log in?
  * Log in at  https://daskhub.fornaxdev.mysmce.com/
* How to log out?
  *  go to `File` Menu: `hub control panel` and `stop my server`.  This insures the server is not still running when you logout which would be a waste of resources
  *  then logout in the upper right
* How to choose which server to open upon login
  * This depends on which type of science you want to do. Placeholder to fill this in once server names stabilize.
* How to choose which size server to open upon login?
  * Make sure to use `mini` size for writing/debugging/testing before switching to larger sizes
  * On demand means an AWS server that starts when the user asks for it (e.g., start your Fornax server), runs as long as you continue to use and pay for it.
  * 128 core: do not use unless given permission
* Navigating jupyter lab
  * How do I start a new notebook?
    * The blue `+` in the upper left brings you to the launcher where you can start a new, empty notebook or open a terminal window
  * How do I get a terminal window?
    * The blue `+` in the upper left brings you to the launcher where you can start a new notebook or open a terminal window
  * How to upload data into the platform?
    * The uparrow in the upper left allows you to upload data
    * if it is a large amount of data, consider creating a zip or tar archive first
    * You can also from within your Jupyter Lab use the shell to 'scp' or 'git pull' from external sites that are publicly visible.
    * What are our storage limits for uploaded data?
    * How will I know if I run into a storage limit?
  *  How to download data from the plaltform to my local machine?
     * If it is a small file, you can right click on the file name in the file browser and scroll to `Download`
     * if it is a large amount of data, consider creating a zip or tar archive first
  * Home Directory
    * When you log into the science console, the active directory is your $HOME directory.  This directory is unique to you: edits and uploads are not visible to other users.  
  * Does my work persist between sessions?
    * Files in your home directory will persist between sessions.
    * pip installs will persist across kernel restarts, but not across logging out and back in.
      * If you want software installs to be persistent, consider setting up an environment: See below under "Making a conda environment that persists across sessions"
  * What is the info at the bottom of the jupyterlab window
    * The github branch is listed as well as the name of the kernel in use
    * the kernel is listed as either 'idle' or 'busy' which is useful to know if your kernel is working or has crashed.
* How to share files from inside the SP with collaborators
  * Download them to favorite storage place (university box account) or put in cloud (put $$ in your proposals to cover this)
* How do I know what computing resources are available to me?
* How do I save my notebook as a python script?
* Save your work!
   * the platform will cull servers after a user is inactive for a certain amount of time - what is that time limit??
* How do I run a notebook non-interactively?
* How to open a plot (png, pdf, etc.) either generated by a notebook or uploaded ?
  * double clicking on them in the file browser will open them in a new tab
* What is a kernel and how do I choose one?
  * In Jupyter, kernels are the background processes that execute cells and return results for display.
  * To select the kernel on which you want to run your Notebook, go to the Kernel menu and choose Change Kernel. You can also click directly on the name of the active kernel to switch to another.
* Will notebooks that I run on the SP also work on my laptop?
  * To run the demo notebooks on your laptop, you will also need to have the container that we use which includes software used by the notebooks.
    * see below under "Can I run the container from the SP on my own personal computer/laptop?"
* Do I need to worry about costs when working in the SP?
  * NASA will pay for the work that you do, but please be mindful of those costs.
* How do I know what costs I am incurring?

## Data Access
* How do I add my own data?
  * small files can be added with the upload button, which is an `uparrow` in the upper right
  * large file transfers??
* Where should I store my data in the SP? 
* How to access images in the cloud?
  * [Tutorial](https://github.com/spacetelescope/tike_content/blob/main/content/notebooks/data-access/data-access.ipynb) notebook on STScI data
  * Where is Abdu's similar notebook with pyvo tools that was used for the July2023 HQ demo?
  * placeholder for Brigitta's SIA access notebook
* How to access catalogs in the cloud?
  * placeholder for Troy's parquet access notebook

## Managing Software
* Making a conda environment that persists across sessions
  * If the pre-installed environments don't have the software you need, you can create your own persistent environment available across multiple sessions.
  * need instructions on how to do this.
* Can I get a list of what software is already pre-installed on the platform?
* How do I install my own software?
  * Persistent User-Installed Software
    *  See "making a conda environment that persists across sessions" above 
  * Non-persistent User-Installed Software 
    * you can !pip install your favorite software from inside a notebook.  This installed software will stay through kernel restarts, but will not be persistent if you stop your server and restart it (logging out and back in).
    * For the tutorial notebooks we tend to have a requirements.txt file in the repo which lists all the software dependencies.  Then the first line in the notebook is `!pip install -r requirements.txt`  That way other people can run the notebook and will know which software is involved.
* What is the terminal command to list package version info using pip
  * `pip show packagname`
* Can I launch apps from icons? Like MOPEX or SPICE
* Can I run licensed software (IDL) in the SP?
* Can I bring my own docker image?
* Can I run the container from the SP on my own personal computer/laptop?

## Examples and Tutorials
* Cloud ([STScI](https://github.com/spacetelescope/tike_content/blob/main/content/notebooks/data-access/data-access.ipynb))
* [Parquet](https://github.com/IPAC-SW/ipac-sp-notebooks/blob/main/aws-open-data-catalogs/wise-allwise-catalog-demo.ipynb)
* Image cutouts
* Optimizing code for fast processing
  * By looking inside the code for slow pieces (CPU profiling)
  * By looking inside the code for memory troubles (memory profiling)
  * By parallelization
    * Python built in [multiprocessing](https://github.com/IPAC-SW/ipac-sp-notebooks/tree/main/parallelize)
    * Daskhub gateway
* [MAST](https://github.com/spacetelescope/tike_content/blob/main/markdown/science-examples.md)
* HEASARC [sciserver_cookbooks](https://github.com/HEASARC/sciserver_cookbooks/blob/main/Introduction.md)
* [Cross matching two large catalogs](https://github.com/IPAC-SW/ipac-sp-notebooks/blob/main/gaia_cross_SEIP/gaia_cross_SEIP.ipynb)
* [Work with theoretical catalogs](https://github.com/IPAC-SW/ipac-sp-notebooks/blob/main/cosmosims/CosmoDC2_Parquet.ipynb)
* Fully worked science use cases
  * [Forced photometry](https://github.com/IPAC-SW/ipac-sp-notebooks/blob/main/cosmosims/CosmoDC2_Parquet.ipynb)
  * [Light curves](https://github.com/IPAC-SW/ipac-sp-notebooks/blob/main/cosmosims/CosmoDC2_Parquet.ipynb)
* User contributions: open issue or PR on Github (which Github repo?)

## Troubleshooting
* If my internet connection goes away or is intermittent - what happens to the running notebook?
* Restart kernel
* Restart SP - will solve version issues if packages with different versions were loaded since these won’t persist across SP restarts
* helpdesk

## Getting Help
* We need to setup a helpdesk!!


## Additional Resources
* New to Python? -
  * [numpy tutorials](https://github.com/IPAC-SW/ipac-sp-notebooks/blob/main/cosmosims/CosmoDC2_Parquet.ipynb)
  * [Scipy lecture notes](https://scipy-lectures.org/)
  * [Data science handbook](https://jakevdp.github.io/PythonDataScienceHandbook/)
* [Guide to documenting python functions](https://developer.lsst.io/python/numpydoc.html#numpydoc-sections-in-docstrings)
* [Github](https://docs.github.com/en/get-started/quickstart)
* [Debugging](https://jakevdp.github.io/PythonDataScienceHandbook/01.06-errors-and-debugging.html#Debugging:-When-Reading-Tracebacks-Is-Not-Enough)
* Three NASA archives are involved in this work
  * [IRSA](https://irsa.ipac.caltech.edu/frontpage/)
  * [HEASARC](https://heasarc.gsfc.nasa.gov)
  * [MAST](https://archive.stsci.edu)
* [Jupyterlab](https://jupyter.org)


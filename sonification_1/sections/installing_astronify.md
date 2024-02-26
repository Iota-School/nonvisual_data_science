[<<< Previous](../README.md) | [Next >>>](intro_to_sonification.md)

# Installing Astronify

Anaconda, which we downloaded as our Python distribution, comes with many popular and handy packages pre-installed. These pre-installed packages include Pandas, which we are already familiar with at this point, as well as Astropy, which we will use later. However, less widely used packages will not come pre-installed, so you will need to do this yourself. Astronify falls into this category, which gives us a great opportunity to learn how to install packages.

Pip and conda are both package managers in Python, and we can use them to install new Python packages. Some packages are only availible via one or the other, whereas other packages will be availible for installation with either pip or conda. Packages are much more widely availible via pip than via conda, as a general rule. When in doubt, you should Google the package you want to install, and there should be an installation guide that will tell you whether the package is availible via pip or conda. For Astronify, we will install using pip.nn

Begin by opening Anaconda Prompt as we have done in the previous three tutorials, but **do not** start IPython. Installing Astronify should be as simple as running the following line of code in your Anaconda Prompt (all lowercase):

~~~
pip install astronify
~~~

A whole bunch of text is going to be printed out in the terminal. You might be prompted to confirm whether you want to proceed with an output that should read something like this:

~~~
Proceed (y/n)?
~~~

If you recieve this prompt, type y for yes, hit enter, and the installation should complete. Once installation is complete, a new input line should appear.

## A Few Caveats

Hopefully, if you are using a Windows computer, that should have installed with no problems. To our knowledge, Astronify should also install smoothly on older Macbooks, but we have had difficulty installing it on both Linux computers and on Macs with Apple chips (so newer Macbooks from the last few years). This, alongside our intention of using NVDA to teach, was part of our motivation for encouraging participants to use Windows computers for these tutorials.

You may have also encountered difficulty installing Astronify if you already have packages other than Anaconda's defaults installed. Sometimes, different packages will conflict with each other in ways that are hard to predict, so if you use many packages, we encourage you to look into separating your different packages into Conda enviroments. Enviroments are beyond the scope of these tutorials, however, so feel free to research in your own time or to attend our office hours if you are experiencing installation woes!a

[<<< Previous](../README.md) | [Next >>>](intro_to_sonification.md)

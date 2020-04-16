# Mac-brew-and-jupyter-notebook-problem #
Records for solving the problem of reinstalling Homebrew and Jupyter notebook, relocate the python interpreter within the terminal and so on

For domestic user only:

#My mac has some problems of using Homebrew, Git and Jupyter Notebook#

First, solve the problem of homebrew. Since the *brew* command is no more useful, I decided not to uninstall it, just install it straight forward using 

>/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

There's might be a problem of 

>curl: (7) Failed to connect to raw.githubusercontent.com port 443: Operation

Solution: Dowload this web as brew_install.rb 

>https://raw.githubusercontent.com/Homebrew/install/master/install

and then 

>ruby brew_install.rb

**DON'T MESS UP WITH YOUR ./~BASH_PROFILE FILE!!!**

Sometimes it requires you to replace the download source to domestic source, see the link below

>https://www.jianshu.com/p/b97e7738014c

My case is that my mac can only start installing Homebrew using 4G hotspot, I don't understand why.

Second, solve the jupyter notebook problem. My case is that I can only open jupyter using

>python3 -m IPython notebook

It will display "Command not found" when using "jupyter notebook"

*/bin* is the place to store the terminal command, so I add the */bin* to system environment variable list, aka *./~bash_profile*

>sudo vim ./~bash_profile
>add following line to the profile
>export PATH=$PATH:/usr/local/Cellar/jupyterlab/2.1.0/bin
>
>source ./~bash_profile

Done

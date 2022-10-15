# venvmgr

venvmgr (Virtual Environment Manager) is a bash script which eases and aids python development by abstracting manual creation and management of python virtual environments, commonly called "venvs".

venvmgr does not rely on any external software and makes creation, activation, and deletion of virtual environments very easy, straightforward, and fast.
To get started using venvmgr all you need to do is run the bash script with a desired venv name, and venvmgr will create it for you, then activate it. For more details see the [Installation section](#installation) below.

When a venv is created with venvmgr, not only is the path standardized among all venvs and therefore easy to remember and find, a "project" directory is also created and will contain a blank python file, which has as its only line a shebang pointing to the venv's python executable.

## Layout
venvmgr relies on the existence of a directory which will be used as a python home, in which venvs and python source is stored. By default this is `~/Dev/python_home`, but this may be changed by supplying the desired path as a parameter.

The python home looks like this:
```
python_home/
├── venvs/
|   ├── venv1/
|   |   ├── bin/
|   |   └── ...
|   |
|   └── venv2/
|       └── ...
|
└── projects/
    ├── project1/
    |   └── project1.py 
    |
    └── project2/
        ├── project2.py
        ├── requirements.txt
        └── modulename.py
```

## Installation
venvmgr can be used as a simple bash script with no installation; to do this, simply download or copy the script to your hard drive and source it with your parameters:
`source ~/path/to/venvmgr.sh pelican`.

However, venvmgr can be installed to your system with this oneliner, which puts it in your `/opt` directory and adds it as a function to your bash or zsh rc, and to the current shell:  
`sh -c "$(wget https://gitlab.com/k-caps/venvmgr/-/raw/main/venvmgr.sh -O -)" -I`    
Once it has been installed, you simply will be able to call it by name from any location:  
`venvmgr -h pyhome -C pelican`

## Usage
`source venvmgr.sh [options] PROJECT_NAME`  
OR (if -I has been used)  
`venvmgr [options] PROJECT_NAME`  
 
**OPTIONS:**  
  `-h`	Directory to use as python_home  
  `-v`	Which python version to use [2|3]  
  `-C`   Clean up a given project and its venv. Can be used with `-h` to remove from a certain python home only"  
  `-I`	Install this script to `/opt/venvmgr` and add it to this and future shells  
  `-H`	Print this help and exit  

This is also printed when supplying the `-H` flag to venvmgr.


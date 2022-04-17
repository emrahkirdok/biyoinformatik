# Conda Build Environment

# Creating an environment with commands

Use the terminal or an Anaconda Prompt for the following steps:

1.	To create an environment:
```
conda create --name myenv
```
2.	 When conda asks you to proceed, type ```y```:
```
proceed ([y]/n)?
```
This creates the myenv environment in ```/envs/.``` No packages will be installed in this environment.

3.	To create an environment with a specific version of Python:
```
conda create -n myenv python=3.6
```
4.	To create an environment with a specific package:
```
conda create -n myenv scipy
```
OR:
```
conda create -n myenv python
conda install -n myenv scipy
```
5.	To create an environment with a specific version of a package:
```
conda create -n myenv scipy=0.15.0
```
OR:
```
conda create -n myenv python
conda install -n myenv scipy=0.15.0
```
6.	To create an environment with a specific version of Python and multiple packages:
```
conda create -n myenv python=3.6 scipy=0.15.0 astroid babel
```
To automatically install pip or another program every time a new environment is created, add the default programs to the create_default_packages section of your ```.condarc```configuration file. The default packages are installed every time you create a new environment. If you do not want the default packages installed in a particular environment, use the ```--no-default-packages``` flag:
```
conda create --no-default-packages -n myenv python
```
# Creating an environment from an environment.yml file

Use the terminal or an Anaconda Prompt for the following steps:

1.	Create the environment from the ```environment.yml```file:
```
conda env create -f environment.yml
```
The first line of the ```yml``` file sets the new environment's name. For details see Creating an environment file manually.

2.	Activate the new environment: ```conda activate myenv```

3.	Verify that the new environment was installed correctly:
```
conda env list
```
# Specifying a location for an environment

You can control where a conda environment lives by providing a path to a target directory when creating the environment. For example, the following command will create a new environment in a subdirectory of the current working directory called ```envs```:
```
conda create --prefix ./envs jupyterlab=0.35 matplotlib=3.1 numpy=1.16
```
You then activate an environment created with a prefix using the same command used to activate environments created by name:
```
conda activate ./envs
```
# Updating an environment

You may need to update your environment for a variety of reasons. For example, it may be the case that:

+	one of your core dependencies just released a new version (dependency version number update).
+	you need an additional package for data analysis (add a new dependency).
+	you have found a better package and no longer need the older package (add new dependency and remove old dependency).

If any of these occur, all you need to do is update the contents of your ```environment.yml``` file accordingly and then run the following command:
```
$ conda env update --prefix ./env --file environment.yml  --prune
```
# Cloning an environment

Use the terminal or an Anaconda Prompt for the following steps:

You can make an exact copy of an environment by creating a clone of it:
```
conda create --name myclone --clone myenv
```
To verify that the copy was made:
```
conda info --envs
```
In the environments list that displays, you should see both the source environment and the new copy.

# Building identical conda environments

You can use explicit specification files to build an identical conda environment on the same operating system platform, either on the same machine or on a different machine.

Use the terminal or an Anaconda Prompt for the following steps:

1.	Run conda ``` list --explicit ``` to produce a spec list such as:
```
# This file may be used to create an environment using:
# $ conda create --name <env> --file <this file>
# platform: osx-64
@EXPLICIT
https://repo.anaconda.com/pkgs/free/osx-64/mkl-11.3.3-0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/numpy-1.11.1-py35_0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/openssl-1.0.2h-1.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/pip-8.1.2-py35_0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/python-3.5.2-0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/readline-6.2-2.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/setuptools-25.1.6-py35_0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/sqlite-3.13.0-0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/tk-8.5.18-0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/wheel-0.29.0-py35_0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/xz-5.2.2-0.tar.bz2
https://repo.anaconda.com/pkgs/free/osx-64/zlib-1.2.8-3.tar.bz2
```
To create this spec list as a file in the current working directory, run:
```
conda list --explicit > spec-file.txt
```
To use the spec file to create an identical environment on the same machine or another machine:
```
conda create --name myenv --file spec-file.txt
```
To use the spec file to install its listed packages into an existing environment:
```
conda install --name myenv --file spec-file.txt
```
One setting may be useful to you when using ```conda init``` is:
```
auto_activate_base: bool
```
This setting controls whether or not conda activates your base environment when it first starts up.

## Nested activation

By default, ```conda activate``` will deactivate the current environment before activating the new environment and reactivate it when deactivating the new environment. Sometimes you may want to leave the current environment PATH entries in place so that you can continue to easily access command-line programs from the first environment. This is most commonly encountered when common command-line utilities are installed in the base environment. To retain the current environment in the PATH, you can activate the new environment using:
```
conda activate --stack myenv
```
If you wish to always stack when going from the outermost environment, which is typically the base environment, you can set the ```auto_stack``` configuration option:
```
conda config --set auto_stack 1
```
# Deactivating an environment

To deactivate an environment, type: ```conda deactivate```

Conda removes the path name for the currently active environment from your system command.

# Determining your current environment

Use the terminal or an Anaconda Prompt for the following steps.

By default, the active environment---the one you are currently using---is shown in parentheses () or brackets [] at the beginning of your command prompt:
```
(myenv) $
```
If you do not see this, run:
```
conda info --envs
```
In the environments list that displays, your current environment is highlighted with an asterisk (*).

By default, the command prompt is set to show the name of the active environment. To disable this option:
```
conda config --set changeps1 false
```
To re-enable this option:
```
conda config --set changeps1 true
```
# Viewing a list of your environments

To see a list of all of your environments, in your terminal window or an Anaconda Prompt, run:
```
conda info --envs
```
OR

conda env list

A list similar to the following is displayed:
```
conda environments:
myenv                 /home/username/miniconda/envs/myenv
snowflakes            /home/username/miniconda/envs/snowflakes
bunnies               /home/username/miniconda/envs/bunnies
```
# Viewing a list of the packages in an environment

To see a list of all packages installed in a specific environment:

+ If the environment is not activated, in your terminal window or an Anaconda Prompt, run:
```
conda list -n myenv
```
+ If the environment is activated, in your terminal window or an Anaconda Prompt, run:
```
conda list
```
+ To see if a specific package is installed in an environment, in your terminal window or an Anaconda Prompt, run:
```
conda list -n myenv scipy
```
# Using pip in an environment

To use pip in your environment, in your terminal window or an Anaconda Prompt, run:
```
conda install -n myenv pip
conda activate myenv
pip <pip_subcommand>
```
# Setting environment variables

If you want to associate environment variables with an environment, you can use the config API. This is recommended as an alternative to using activate and deactivate scripts since those are an execution of arbitrary code that may not be safe.

First, create your environment and activate it:
```
conda create -n test-env
conda activate test-env
```
To list any variables you may have, run ```conda env config vars list```.

To set environment variables, run ```conda env config vars set my_var=value```.

Once you have set an environment variable, you have to reactivate your environment: ```conda activate test-env```.

To check if the environment variable has been set, run ```echo my_var``` or ```conda env config vars list```.

When you deactivate your environment, you can use those same commands to see that the environment variable goes away.

You can specify the environment you want to affect using the ```-n``` and ```-p ```flags. The ```-n``` flag allows you to name the environment and ```-p```allows you to specify the path to the environment.

To unset the environment variable, run ```conda env config vars unset my_var -n test-env```.

When you deactivate your environment, you can see that environment variable goes away by rerunning ```echo my_var``` or ```conda env config vars list``` to show that the variable name is no longer present.

Environment variables set using ```conda env config vars``` will be retained in the output of ```conda env export```. Further, you can declare environment variables in the environment.yml file as shown here:
```
name: env-name
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.7
  - codecov
variables:
  VAR1: valueA
  VAR2: valueB
```
# Saving environment variables

Conda environments can include saved environment variables.

Suppose you want an environment "analytics" to store both a secret key needed to log in to a server and a path to a configuration file. The sections below explain how to write a script named ```env_vars``` to do this on Windows and macOS or Linux.

This type of script file can be part of a conda package, in which case these environment variables become active when an environment containing that package is activated.

You can name these scripts anything you like. However, multiple packages may create script files, so be sure to use descriptive names that are not used by other packages. One popular option is to give the script a name in the form ```packagename-scriptname.sh```, or on Windows, ```packagename-scriptname.bat```.

## Windows

1.	Locate the directory for the conda environment in your Anaconda Prompt by running in the command shell ```%CONDA_PREFIX%```.

2.	Enter that directory and create these subdirectories and files:
```
cd %CONDA_PREFIX%.
mkdir .\etc\conda\activate.d
mkdir .\etc\conda\deactivate.d
type NUL > .\etc\conda\activate.d\env_vars.bat
type NUL > .\etc\conda\deactivate.d\env_vars.bat
```
Edit ```.\etc\conda\activate.d\env_vars.bat``` as follows:
et MY_KEY='secret-key-value'
set MY_FILE=C:\path\to\my\file

Edit ```.\etc\conda\deactivate.d\env_vars.bat``` as follows:
```
set MY_KEY=
set MY_FILE=
```

# Sharing an environment
You may want to share your environment with someone else---for example, so they can re-create a test that you have done. To allow them to quickly reproduce your environment, with all of its packages and versions, give them a copy of your ```environment.yml``` file.

## Exporting the environment.yml file

Activate the environment to export: ```conda activate myenv```

Export your active environment to a new file:
```
conda env export > environment.yml
```
## Exporting an environment file across platforms

If you want to make your environment file work across platforms, you can use the ```conda env export --from-history``` flag. This will only include packages that you’ve explicitly asked for, as opposed to including every package in your environment.

For example, if you create an environment and install Python and a package:
```
conda install python=3.7 codecov
```
This will download and install numerous additional packages to solve for dependencies. This will introduce packages that may not be compatible across platforms.

If you use ```conda env export```, it will export all of those packages. However, if you use ```conda env export --from-history```, it will only export those you specifically chose:
```
(env-name) ➜  ~ conda env export --from-history
name: env-name
channels:
  - conda-forge
  - defaults
dependencies:
  - python=3.7
  - codecov
prefix: /Users/username/anaconda3/envs/env-name
```
## Creating an environment file manually

You can create an environment file ```environment.yml``` manually to share with others.

EXAMPLE: A simple environment file:
```
name: stats
dependencies:
  - numpy
  - pandas
```
EXAMPLE: A more complex environment file:
```
name: stats2
channels:
  - javascript
dependencies:
  - python=3.6   # or 2.7
  - bokeh=0.9.2
  - numpy=1.9.*
  - nodejs=0.10.*
  - flask
  - pip:
    - Flask-Testing
```
You can exclude the default channels by adding ```nodefaults``` to the channels list.

channels:
```
  - javascript
  - nodefaults
```
# Restoring an environment

Conda keeps a history of all the changes made to your environment, so you can easily "roll back" to a previous version. To list the history of each change to the current environment: ```conda list --revisions```

To restore environment to a previous revision: ```conda install --revision=REVNUM``` or ```conda install --rev REVNUM```.

Example: If you want to restore your environment to revision 8, run ```conda install --rev 8```.

# Removing an environment

To remove an environment, in your terminal window or an Anaconda Prompt, run:
```
conda remove --name myenv --all
```
You may instead use ```conda env remove --name myenv```.

To verify that the environment was removed, in your terminal window or an Anaconda Prompt, run:
```
conda info --envs
```
The environments list that displays should not show the removed environment.

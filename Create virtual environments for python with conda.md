### How to set up a virtual environments using conda for the Anaconda Python distribution

> _A virtual environment is a named, isolated, working copy of Python that that maintains its own files, directories, and paths so that you can work with specific versions of libraries or Python itself without affecting other Python projects. Virtual environmets make it easy to cleanly separate different projects and avoid problems with different dependencies and version requiremetns across components. The `conda` command is the preferred interface for managing intstallations and virtual environments with the [Anaconda](https://store.continuum.io/cshop/anaconda/) Python distribution. If you have a vanilla Python installation or other Python distribution see [virtualenv](http://virtualenv.readthedocs.org/en/latest/)_

## Outline

* Check conda is installed and available
* Update conda if necessary
* Create a virtual environment
* Activate a virtual environment
* Install additional python packages
* Deactivate a virtual environment
* Delete a virtual environment

## Jargon

link to PATH, 

## Requirements

* Anaconda Python distribution installed and accessible

## 1. Check conda is installed and in your PATH

1.  Open a terminal client.
2.  Enter `conda -V` into the terminal command line and press enter.
3.  If conda is installed you should see somehting like the following.

```language-bash
$ conda -V
conda 3.7.0
```

## 2. Check conda is up to date

1.  In the terminal client enter

```language-bash
conda update conda
```

1.  Upadate any packages if necessary by typing `y` to proceed.

## 3. Create a virtual environment for your project

1.  In the terminal client enter the following where _yourenvname_ is the name you want to call your environment, and replace _x.x_ with the Python version you wish to use. (To see a list of available python versions first, type `conda search "^python$"` and press enter.) 

```language-bash
conda create -n yourenvname python=x.x anaconda
```

1.  Press `y` to proceed. This will install the Python version and all the associated anaconda packaged libraries at “path_to_your_anaconda_location/anaconda/envs/yourenvname”

## 4. Activate your virtual environment.

1.  To activate or switch into your virtual environment, simply type the following where _yourenvname_ is the name you gave to your environement at creation.

```language-bash
source activate yourenvname
```

1.  Activating a conda environment modifies the PATH and shell variables to point to the specific isolated Python set-up you created. The command prompt will change to indicate which conda environemnt you are currently in by prepending `(yourenvname)`. To see a list of all your environments, use the command `conda info -e`.

## 5. Install additional Python packages to a virtual environment.

1.  To install additional packages only to your virtual environment, enter the following command where _yourenvname_ is the name of your environemnt, and _[package]_ is the name of the package you wish to install. _Failure to specify “-n yourenvname” will install the package to the root Python installation._

```language-bash
conda install -n yourenvname [package]
```

## 6. Deactivate your virtual environment.

1.  To end a session in the current environment, enter the following. There is no need to specify the envname - which ever is currently active will be deactivated, and the PATH and shell variables will be returned to normal.

```language-bash
source deactivate
```

## 6. Delete a no longer needed virtual environment

1.  To delete a conda environment, enter the following, where _yourenvname_ is the name of the environment you wish to delete.

```language-bash
conda remove -n yourenvname -all
```

## Related info

The conda offical documentation can be found [here](http://conda.pydata.org/docs/intro.html).

# OAV-Donkey-Env-Setup

## Donkey environment setup

The instructions for setting up and installing Donkey can be confusing.  The instructions use a mix of conda and virtualenv environments depending on the donkey fork that you are using.  We've captured the minimum set of packages to install using conda.  This is very useful, since conda will pull in all the dependencies needed for the packages that you specify.  So we only need to specify the top level packages used by our python scripts.

## PC Setup

Here are the commands for setting up a conda environment on your PC.  This will setup a python 3.6 environment, with tensorflow-gpu==1.13.1 and keras==2.2.4.  Conda is used to install packages where they are available from the conda channels.  Several packages had to be installed using pip (using the "pip install -e .[pc]") command.

Run these commands in a miniconda window.  In the example below, the conda environment will be called "d2env" and the donkey project directory is called "donkey-tawn".  You can change these names as desired.  Just update the commands below with your own names.

```
// Create a conda environment with python 3.6, activate it, and then install the required packages

>conda create -n d2env python=3.6
>conda activate d2env

// If you have a GPU, you can install tensorflow-gpu
>conda install tensorflow-gpu keras

// Otherwise, just install tensorflow
>conda install tensorflow keras

// Install packages used by the Tawn's donkey project fork
>conda install pillow docopt tornado requests python-socketio flask pandas  matplotlib scikit-learn

// Go into your project directory and clone the donkey repository.  Here, we're assuming you have a 
// "projects" directory in your user home directory.  In this example the project directory is called 
// "donkey-tawn".  Name this to whatever you want.

>cd projects
>git clone git@github.com:tawnkramer/donkey.git ./donkey-tawn
>cd donkey-tawn
>pip install -e .[pc]
>donkey createcar --path ./mycar
>cd mycar
```

You can test the install by training a model:
```
>python train.py --tub=[path-to-tub] --model=[model-file-name.h5] --type=linear
```


## Raspberry Pi setup

TBD...

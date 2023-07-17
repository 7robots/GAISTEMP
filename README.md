# GAISTEMP
 GAISTEMP Project



## Container Build Instructions

- In your build directory, make sure you've created an .env file that contains your OpenAI API key.
- the .env file should contain the following line:

API_TOKEN=myapikey

- Now build the container image

docker build -t gai-jupyter .

## Launch Jupyter

- Run launch script to create a new container instance and run it

/bin/sh launch.sh 

- Copy the URL output from the launch script and paste into your web brower
- This should authenticate you into Jupyter
- In the upper left file browser on the Jupyter Notebook page, double-click on the GPT-API-Demo notebook file to start the notebook we will use for this exercise

![Select Notebook](./work/select-notebook.png "Select Notebook")


## Container Details

This project builds a custom docker container image, based on the jupyter/scipy-notebook image on Docker Hub.

The build script adds two pip packages

- OpenAI: used for API access to OpenAI/ChatGPT
- python-dotenv: used by python and jupyter notebook to source environment variables from a file called .env

The build script also adds two files to the container runtime:

- .env: this text file contains the OpenAI API key as an environment variable
- GPT-API-Demo.ipynb: the Jupyter notebook used for the ChatGPT Demo

# NSIDC-Data-Access-Notebook

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/nsidc/NSIDC-Data-Access-Notebook/master?urlpath=lab/tree/notebooks)

A Jupyter notebook exploring data coverage, size, and customization service availability along with direct data download utilizing the NSIDC DAAC's access and service API.

This notebook was originally developed for the April 2019 USFS – NASA Joint Applications Workshop.

# Usage with Docker

## On Mac OSX or Linux


1. Install [Docker](https://docs.docker.com/install/). Use the left-hand navigation to select the appropriate install depending on operating system.

2. Create a new folder to host the notebook.

3. Download the [NSIDC-Data-Access-Notebook from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

4. Unzip the file, which should contain a folder with a .ipynb file. Move the .ipynb file to the newly created folder.

5. From command line, launch the docker container using the following command, replacing [path/notebook_folder] with your path and notebook folder name:


```docker run -p 8888:8888 -v [path/notebook_folder]:/home/jovyan jupyter/datascience-notebook```


Example:


```docker run -p 8888:8888 -v /Users/name/Desktop/notebook_folder:/home/jovyan jupyter/datascience-notebook```


The initialization will take some time and will require 5.6 GB of space. Once the startup is complete you will see a line of output similar to this:

```http://(6a8bfa6a8518 or 127.0.0.1):8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f```

6. Copy everything from the :8888 to the end. Open up a web browser and in the address field type localhost, paste the copied text, and hit return. The address should look something like this:

`localhost:8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f`

7. You will be brought to the Jupyter notebook running through the Docker container. You can now interact with the notebook to explore and access data.


## On Windows

1. Install [Docker](https://docs.docker.com/docker-for-windows/install/).

2. Create a new folder to host the notebook.

3. Download the [NSIDC-Data-Access-Notebook from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

4. Unzip the file, which should contain a folder with a .ipynb file. Move the .ipynb file to the newly created folder.

5. From a terminal window (use Command Prompt or PowerShell, not PowerShell ISE), launch the docker container using the following command, replacing [path\notebook_folder] with your path and notebook folder name:

```docker run -p 8888:8888 -v [path\notebook_folder]:/home/jovyan jupyter/datascience-notebook```

Example:

```docker run -p 8888:8888 -v C:\notebook_folder:/home/jovyan jupyter/datascience-notebook```

The initialization will take some time and will require 5.6 GB of space. Once the startup is complete you will see a line of output similar to this:

```http://(6a8bfa6a8518 or 127.0.0.1):8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f```

6. Copy everything from the :8888 to the end. Open up a web browser and in the address field type localhost, paste the copied text, and hit return. The address should look something like this:

`localhost:8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f`

7. You will be brought to the Jupyter notebook running through the Docker container. You can now interact with the notebook to explore and access data.
(miniconda3-latest/envs/jupyterhub-vm)


# Usage with Conda

1. Install miniconda3 (Python 3.7) for your platform from https://docs.conda.io/en/latest/miniconda.html

2. Download the [NSIDC-Data-Access-Notebook from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

3. Unzip the file,  and open a terminal in the folder's location.

4. From the terminal install the required environment with the following command:
   `conda env create -f binder/environment.yml`
    you should now see that the dependencies were installed and our environment is ready to be used.

5. Activate the environment with `source activate icepick` or `conda activate icepick`

6. Launch the notebook locally with the following command
    `jupyter notebook --allow-root --notebook-dir=./notebooks  --ip='0.0.0.0' --port=8888`
    This should open a browser where you need to put the token string as the password if asked.

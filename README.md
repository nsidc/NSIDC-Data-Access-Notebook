# NSIDC-Data-Access-Notebook

A Jupyter notebook exploring data coverage, size, and customization service availability along with direct data download utilizing the NSIDC DAAC's Data Access and Service API. If you are new to Jupyter Notebooks, you can read the [documentation](https://jupyter-notebook.readthedocs.io/en/stable/index.html), or you can walk through the user interface tour once you have loaded the notebook by selecting `Help` -> `User Interface Tour` in the menubar. 

This notebook was originally developed for the April 2019 USFS – NASA Joint Applications Workshop.

# Usage with Binder

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/nsidc/NSIDC-Data-Access-Notebook/master?urlpath=lab/tree/notebooks)

The Binder button above allows you to explore and run the notebook in a shared cloud computing environment without the need to install dependencies on your local machine. Note that this option will not directly download data to your computer; instead the data will be downloaded to the cloud environment. If you are interested in bulk downloading data, we recommend running this notebook locally using the Conda or Docker options.


# Usage with Conda

1. Install miniconda3 (Python 3.7) for your platform from https://docs.conda.io/en/latest/miniconda.html

2. Download the [NSIDC-Data-Access-Notebook from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

3. Unzip the file, and open a command line or terminal window in the `NSIDC-Data-Access-Notebook` folder's location.

4. From a command line or terminal window, install the required environment with the following command:

   ```conda env create -f binder/environment.yml```

    you should now see that the dependencies were installed and our environment is ready to be used.

5. Activate the environment with ```source activate icepick``` or ```conda activate icepick```

6. Launch the notebook locally with the following command:

    ```jupyter notebook```

This should open a browser window displaying your current working directory contents. Navigate to the `notebooks` folder and click on the `NSIDC DAAC Customize and Access Data Tutorial.ipynb` file. You can now interact with the notebook to explore and access data.


# Usage with Docker

## On Mac OSX or Linux


1. Install [Docker](https://docs.docker.com/install/). Use the left-hand navigation to select the appropriate install depending on operating system.

2. Download the [NSIDC-Data-Access-Notebook repository from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

3. Unzip the file, and open a terminal window in the `NSIDC-Data-Access-Notebook` folder's location.

4. From the terminal window, launch the docker container using the following command, replacing [path/notebook_folder] with your path and notebook folder name:


```docker run -p 8888:8888 -v [path/notebook_folder]:/home/jovyan jupyter/datascience-notebook```


Example:


```docker run -p 8888:8888 -v /Users/name/Desktop/NSIDC-Data-Access-Notebook:/home/jovyan jupyter/datascience-notebook```


The initialization will take some time and will require 5.6 GB of space. Once the startup is complete you will see a line of output similar to this:

```http://(6a8bfa6a8518 or 127.0.0.1):8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f```

6. Copy everything from the :8888 to the end. Open up a web browser and in the address field type localhost, paste the copied text, and hit return. The address should look something like this:

`localhost:8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f`

7. You will be brought to the Jupyter Lab interface running through the Docker container. The left side of the interface displays your local directory structure. Navigate to the `notebooks` folder of the `NSIDC-Data-Access-Notebook` repository folder and click on the `NSIDC DAAC Customize and Access Data Tutorial.ipynb` file. You can now interact with the notebook to explore and access data.


## On Windows

1. Install [Docker](https://docs.docker.com/docker-for-windows/install/).

2. Download the [NSIDC-Data-Access-Notebook repository from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

3. Unzip the file, and open a terminal window (use Command Prompt or PowerShell, not PowerShell ISE) in the `NSIDC-Data-Access-Notebook` folder's location.

5. From the terminal window, launch the docker container using the following command, replacing [path\notebook_folder] with your path and notebook folder name:

```docker run -p 8888:8888 -v [path\notebook_folder]:/home/jovyan jupyter/datascience-notebook```

Example:

```docker run -p 8888:8888 -v C:\notebook_folder:/home/jovyan jupyter/datascience-notebook```

The initialization will take some time and will require 5.6 GB of space. Once the startup is complete you will see a line of output similar to this:

```http://(6a8bfa6a8518 or 127.0.0.1):8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f```

6. Copy everything from the :8888 to the end. Open up a web browser and in the address field type localhost, paste the copied text, and hit return. The address should look something like this:

`localhost:8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f`

7. You will be brought to the Jupyter notebook running through the Docker container. You can now interact with the notebook to explore and access data.



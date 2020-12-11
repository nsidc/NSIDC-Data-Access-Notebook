# NSIDC-Data-Access-Notebook

A Jupyter notebook exploring data coverage, size, and customization service availability along with direct data download utilizing the NSIDC DAAC's Data Access and Service API. If you are new to Jupyter Notebooks, you can read the [documentation](https://jupyter-notebook.readthedocs.io/en/stable/index.html), or you can walk through the user interface tour once you have loaded the notebook by selecting Help -> User Interface Tour in the menubar.

This notebook was originally developed for the April 2019 USFS – NASA Joint Applications Workshop.

# Usage with Binder

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/nsidc/NSIDC-Data-Access-Notebook/73ba6a37a0a2934c8da336aeb85004cabf923dd4)

The Binder button above allows you to explore and run the notebook in a shared cloud computing environment without the need to install dependencies on your local machine. Note that this option will not directly download data to your computer; instead the data will be downloaded to the cloud environment. If you are interested in bulk downloading data, we recommend running this notebook locally using the Conda or Docker options.

# Usage with Docker

Docker is the preferred way of running these notebooks, refer to the installation guide for your operating system [Install Docker](https://docs.docker.com/get-docker/). We are going to use NSIDC's tutorial image, we can pull it from the Docker registry with:

`docker pull nsidc/tutorials`

## On Mac OSX or Linux


1. Install [Docker](https://docs.docker.com/install/). Use the left-hand navigation to select the appropriate install depending on operating system.

2. Download the [NSIDC-Data-Access-Notebook repository from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

3. Unzip the file, and open a terminal window in the `NSIDC-Data-Access-Notebook` folder's location.

4. From the terminal window, launch the docker container using the following command, replacing [path/notebook_folder] with your path and notebook folder name:


```bash
docker run --name tutorials -p 8888:8888 -v [path/notebook_folder]:/home/jovyan/work nsidc/tutorials
```
Example:
```bash
docker run --name tutorials -p 8888:8888 -v /Users/name/Desktop/NSIDC-Data-Access-Notebook:/home/jovyan/work nsidc/tutorials
```
If you want to mount a directory with write permissions you need to grant the container the same permissions as the one on the directory to be mounted and tell it that has "root" access (within the container) this is important if you want to persist your work or download data to a local directory and not just the docker container.

```bash
docker run --name tutorials -e NB_UID=$(id -u) --user root -p 8888:8888 -v  /Users/name/Desktop/NSIDC-Data-Access-Notebook:/home/jovyan/work nsidc/tutorials
```

The initialization will take some time and will require 1.8 GB of space. Once the startup is complete you will see a line of output similar to this:

```bash
http://(6a8bfa6a8518 or 127.0.0.1):8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f
```

5. Copy everything from the :8888 to the end. Open up a web browser and in the address field type localhost, paste the copied text, and hit return. The address should look something like this:

> `localhost:8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f`

6. You will be brought to the Jupyter Lab interface running through the Docker container. The left side of the interface displays your local directory structure. Navigate to the **`work`** folder of the `NSIDC-Data-Access-Notebook` repository folder. You can now interact with the notebooks to explore and access data.

> **Note**: if you prefer to use **Jupyterlab** you need to use the following URL and login with the same token:
>  `http://127.0.0.1:8888/lab`

## On Windows

1. Install [Docker](https://docs.docker.com/docker-for-windows/install/).

2. Download the [NSIDC-Data-Access-Notebook repository from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

3. Unzip the file, and open a terminal window (use Command Prompt or PowerShell, not PowerShell ISE) in the `NSIDC-Data-Access-Notebook` folder's location.

5. From the terminal window, launch the docker container using the following command, replacing [path\notebook_folder] with your path and notebook folder name:

```bash
docker run --name tutorials -p 8888:8888 -v [path\notebook_folder]:/home/jovyan/work nsidc/tutorials 
```

Example:

```bash 
docker run --name tutorials -p 8888:8888 -v C:\notebook_folder:/home/jovyan/work nsidc/tutorials
```

If you want to mount a directory with write permissions you need to grant the container the same permissions as the one on the directory to be mounted and tell it that has "root" access (within the container)
```bash
docker run --name tutorials --user root -p 8888:8888 -v C:\notebook_folder:/home/jovyan/work nsidc/tutorials
```
The initialization will take some time and will require 1.8 GB of space. Once the startup is complete you will see a line of output similar to this:

```
To access the notebook, open this file in a browser:
        file:///home/jovyan/.local/share/jupyter/runtime/nbserver-6-open.html
    Or copy and paste one of these URLs:
        http://(6a8bfa6a8518 or 127.0.0.1):8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f
```

6. Follow the instructions and copy one of the URLs into a web browser and hit return. The address should look something like this:

`http://127.0.0.1:8888/?token=2d72e03269b59636d9e31937fcb324f5bdfd0c645a6eba3f`

7. You will now see the NSIDC-Data-Access repository within the Jupyter Notebook interface. Navigate to **/work** to open the notebooks. 

8. You can now interact with the notebooks to explore and access data.

> **Note**: if you prefer to use **Jupyterlab** you need to use the following URL and login with the same token:
>  `http://127.0.0.1:8888/lab`

## Usage with Conda

1. Install miniconda3 (Python 3.7) for your platform from https://docs.conda.io/en/latest/miniconda.html

2. Download the [NSIDC-Data-Access-Notebook from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip).

3. Unzip the file, and open a command line or terminal window in the `NSIDC-Data-Access-Notebook` folder's location.

4. From a command line or terminal window, install the required environment with the following command:

   ```conda env create -f binder/environment.yml```

    you should now see that the dependencies were installed and our environment is ready to be used.

5. Activate the environment with ```source activate icepick``` or ```conda activate icepick```

6. Launch the notebook locally with the following command:

    ```jupyter lab```

This should open a browser window displaying your current working directory contents. Navigate to the `notebooks` folder and click on the `Customize and Access NSIDC Data.ipynb` file. You can now interact with the notebook to explore and access data.



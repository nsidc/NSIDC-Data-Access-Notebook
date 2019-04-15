# NSIDC-Data-Access-Notebook

A Jupyter notebook exploring data coverage, size, and customization service availability along with direct data download utilizing the NSIDC DAAC's access and service API.  

This notebook was originally developed for the April 2019 USFS – NASA Joint Applications Workshop.

# Usage

## On a Mac or Linux


1. Install [Docker](https://docs.docker.com/install/).

2. Create a new folder to host the notebook.

3. Download the [NSIDC-Data-Access-Notebook link from Github](https://github.com/nsidc/NSIDC-Data-Access-Notebook/archive/master.zip)

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



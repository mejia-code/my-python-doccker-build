# My python docker image

1. mkdir `python-docker`
1. create a new text file in `python-docker` called `Dockerfile`
   ![Dockerfile](images/dockerfile.png)
1. add the following to the `Dockerfile`:

   ```dockerfile
   FROM python:3.7-alpine #

   ```

   Base imgage is python 3.7 alpine. It is a lightweight version of python. It is a good practice to use the latest version of python. You can find the latest version of python [here](https://hub.docker.com/_/python)

1. add our `script.py` to the `Dockerfile`:

   ```dockerfile
   FROM python:3.7-alpine # base image to use for our container image
   ADD script.py /script.py # add script.py to the root of the container: `/`
   ```

1. install dependencies:
   ```dockerfile
    RUN pip install pystrich # install pystrich package from pypi (python package index). pystrich is a package that generates barcodes.
   ```

# My python docker image

1. mkdir `python-docker`
1. create a new text file in `python-docker` called `Dockerfile`
   ![Dockerfile](images/dockerfile.png)

1. create a new text file in `python-docker` called `requirements.txt`
   ![requirements.txt](images/requirements.png)

---

1. add the following to the `Dockerfile`:

   ```dockerfile
   FROM python:3.7-alpine #
   ```

   Base imgage is python 3.7 alpine. It is a lightweight version of python. It is a good practice to use the latest version of python. You can find the latest version of python [here](https://hub.docker.com/_/python)

1. add our `script.py` to the `Dockerfile`:

   ```dockerfile
   FROM python:3.7-alpine # base image to use for our container image
   ADD script.py / # add the script.py file to the root directory of the container: `/`
   ```

1. install dependencies:

   ```dockerfile
    RUN pip install pystrich # install pystrich package from pypi (python package index). `pystrich` is a package that generates barcodes.
   ```

   This directory defines the context of your build, meaning it contains all of the things you need to build your image.

   The context is sent to the Docker daemon, which then executes the commands in the Dockerfile to build the image.

   The context is also used by the `ADD` and `COPY` commands in the Dockerfile to copy files into the image.

1. run the script:
   ```dockerfile
   CMD ["python", "script.py"] # run the script.py file
   ```
   The `CMD` instruction sets the default command and/or parameters, which can be overwritten from the command line when docker container runs.

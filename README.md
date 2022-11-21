# My python docker image

1. mkdir `python-docker`
1. create a new text file in `python-docker` called `Dockerfile`
   ![Dockerfile](images/dockerfile.png)
1. add the following to the `Dockerfile`:

   ```dockerfile
   FROM python:3.7-alpine

   ```

1. add our `script.py` to the `Dockerfile`:

   ```dockerfile
   FROM python:3.7-alpine
   ADD script.py /script.py

   ```

   ˝

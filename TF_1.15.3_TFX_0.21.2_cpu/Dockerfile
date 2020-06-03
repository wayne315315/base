FROM tensorflow/tensorflow:2.1.0-py3

# Install essential pip packages for applications 
RUN python3 -m pip install pip==20.1.1 --no-input --default-timeout 1000
RUN python3 -m pip install setuptools==47.1.1 --no-input --default-timeout 1000
RUN python3 -m pip uninstall -y tensorflow

WORKDIR ~
COPY requirements.txt .
RUN python3 -m pip install -r requirements.txt --default-timeout 1000 \
    --no-deps --no-cache-dir --no-input

# Clean up
RUN rm $(ls)
WORKDIR /
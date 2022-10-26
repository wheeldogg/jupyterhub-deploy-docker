# JupyterLab Example

This is an example of using JupyterLab as the single-user Notebook server image with JupyterHub.

The example builds a Docker image that uses the yml environment from django and creates conda with this.

## Build the Image

Build and tag the image using the `Dockerfile` in this directory.

```
docker build -t django_server .
```

## Run JupyterHub Container

To have JupyterHub spawn the `django_server` image for single-user Notebook
servers, set the following environment variables before you run the JupyterHub container.

This is also set in the .env file if not set on the host

```
export DOCKER_NOTEBOOK_IMAGE=django_server
```

Then run the following **from the root directory** of this repository:

```
# bring down the JupyterHub container, if running
docker-compose down

# bring it back up
docker-compose up -d
```

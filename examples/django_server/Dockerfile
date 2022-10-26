# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.

FROM jupyter/minimal-notebook

# Install django conda environment
COPY django_dev_server.yml .
RUN conda env create --name django_dev_server --file=django_dev_server.yml

USER jovyan

# Make RUN commands use the new environment:
SHELL ["conda", "run", "-n", "django_dev_server", "/bin/bash", "-c"]
RUN python -m ipykernel install --user --name django_dev_server --display-name "Python (django_dev_server)"
# shamelessly stolen from https://github.com/binder-examples/dockerfile-rstudio/edit/master/Dockerfile

FROM rocker/binder:3.4.2

# Copy repo into ${HOME}, make user own $HOME
USER root

# COPY . ${HOME}

# jupyter config
RUN jupyter notebook --allow-root --generate-config -y
RUN echo "c.NotebookApp.password = ''" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.token = ''" >> ~/.jupyter/jupyter_notebook_config.py
RUN chown -R ${NB_USER} ${HOME}
USER ${NB_USER}

## run any install.R script we find
RUN if [ -f install.R ]; then R --quiet -f install.R; fi

FROM python:3
RUN apt-get update && apt-get install -yq --no-install-recommends \
    build-essential \
    emacs \
    git \
    inkscape \
    jed \
    libsm6 \
    libxext-dev \
    libxrender1 \
    lmodern \
    netcat \
    pandoc \
    python-dev \
    texlive-fonts-extra \
    texlive-fonts-recommended \
    texlive-generic-recommended \
    texlive-latex-base \
    texlive-latex-extra \
    texlive-xetex \
    tzdata \
    unzip \
    nano \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app
RUN pip3 install --upgrade pip
RUN pip3 install --upgrade jupyter
RUN pip3 install notebook
RUN pip3 install pandas numpy matplotlib seaborn
RUN pip3 install requests parse folium
RUN pip3 install beautifulsoup4
RUN pip3 install -U googlemaps

# jupyter config
RUN jupyter notebook --allow-root --generate-config -y
RUN echo "c.NotebookApp.password = ''" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.token = ''" >> ~/.jupyter/jupyter_notebook_config.py

# COPY . .


EXPOSE 8888
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--allow-root"]


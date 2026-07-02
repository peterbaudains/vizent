FROM sphinxdoc/sphinx

WORKDIR /docs

COPY .env /docs

# Install pandoc
RUN apt-get update \
    && apt-get install -y wget \
    && wget https://github.com/jgm/pandoc/releases/download/3.1.6/pandoc-3.1.6-1-amd64.deb
RUN dpkg -i pandoc-3.1.6-1-amd64.deb

ENV LANG=C.UTF-8
ENV LC_ALL=C.UTF-8


# Install cartopy dependencies
RUN apt -y install libgeos-dev \
                   gcc \
                   g++

# Install python sphinx requirements
RUN pip install nbsphinx mpl_sphinx_theme sphinx-autobuild pandoc

# Install vizent depdendencies
RUN pip install scipy Pillow cartopy 

# Install vizent gallery dependencies
RUN pip install pandas python-dotenv

# Install jupyter ipykernel
RUN pip install ipykernel

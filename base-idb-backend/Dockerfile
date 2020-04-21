FROM python:2.7
RUN apt-get update && apt-get install -y --no-install-recommends \
    gfortran \
    libatlas-base-dev \
    ffmpeg \
    libblas-dev \
    libgdal-dev \
    liblapack-dev \
    libpq-dev \
  && rm -rf /var/lib/apt/lists/*

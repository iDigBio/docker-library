FROM ubuntu:bionic
RUN apt-get update && apt-get install -y --no-install-recommends \
    iputils-ping \
    curl \
    dnsutils \
    traceroute \
    httpie \
    postgresql-client \
    s3cmd \
  && rm -rf /var/lib/apt/lists/*

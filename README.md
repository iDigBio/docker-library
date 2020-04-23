# docker-library
A collection of Dockerfiles

This repo holds a number of Dockerfiles for building "base" images that can then be used in other projects.

## Using the images built from docker-library

The Dockerfiles contained in this repo are built and pushed to Docker Hub.

You can use them in a Dockerfile:

```
FROM idigbio/docker-library.base-idb-backend
```

You can run them directly:

```
$ docker run --rm -it idigbio/docker-library.base-idb-backend bash
```

## Adding a new Dockerfile to docker-library

There are 3 steps to add a new Dockerfile to this library repo.

1. Create a new directory. Choose wisely because the directory name will
also be used as the docker hub repository name.
2. Add a README and Dockerfile to the directory.
3. Add the job specifics to `.travis.yml` in the `jobs.include` section,
using the directory name as the value of DOCKERFILE_DIR and a component of 
DOCKER_IMAGE_NAME.

Example:
```yaml
jobs:
  include:
  - name: "Base for idb-backend"
    env:
      - DOCKERFILE_DIR=base-idb-backend
      - DOCKER_IMAGE_NAME=idigbio/docker-library.base-idb-backend
```

When the changes are comitted to master, Travis will trigger builds of new docker images and push them to Docker Hub.

---
sidebar_position: 9
---

# Containers

## Container Basics
- Containers are used to ensure that the application is always run with the same asumptions.
- Whether in development or production, containers ensure that the application always has the correct dependencies.
- The most common tool to create containers is Docker.

## Terminology

- Image: A package with the compiled app and dependencies.
- Container: A running instance of a container image.
- Dockerfile: The build instructions for creating an image.
- Build: Creating an image from Dockerfile
- Volumes: File systems that are made available to the container.
- MSB: Multi-stated Build
- Registry: A place to store container images
- Docker Compose: A tool to run multiple container images together

## Dockerfiles
- In order to create containers with Docker, we must create an image.
- Images are created from Dockerfiles.  A Dockerfile must have a base image and probably does several steps to set up the enviornment for the new images.
- The `docker build` command is used to build images from docker files.
- Then the images can be run, which turns them into containers.

### Multi-stage Builds
- Sometimes, it is ideal to have a one environment for building the source or for some other action, and another for running it in production.
- One soltuion to this would be to have two different dockerfiles along with a shell script to manage them, but this is complex and leads to large container sizes
- Instead, multi-stage builds can be added to the docker file to seperate various stages of the development and deployment process.

## Running Containers
- Containers can be started with `docker run [options] [container]`.
- They can be stopped with `docker stop [container]`.

## Docker Compose
- Docker compose is used to orchestrate the running of several different containers for a singular project
- Various configurations can be passed into the docker-compose.yml, so that command line arguments do not need to be used everytime a container needs to be started.
- The containers can be started with `docker compose up` and closed with `docker compose down`.

    

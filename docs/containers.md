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

## Docker
- In order to create containers with Docker, we must create an image.
- Images are created from Dockerfiles.  A Dockerfile must have a base image and probably does several steps to set up the enviornment for the new images.
- The `docker build` command is used to build images from docker files.
- Then the images can be run, which turns them into containers.
- 

    

# Dockerized File Extension Manager

This repository contains a Docker setup to manage files with specific extensions within a directory using the `rmbyext` tool. The Dockerfile provided will build a Python-based container that can remove files based on their extension.

## Files in this Repository

### Dockerfile-exec

- **Base Image**: The Dockerfile starts with a lightweight Python 3 Alpine image.
- **Working Directory**: The working directory inside the container is set to `/data`.
- **Dependencies**: The necessary dependencies are installed, including `git` to fetch the `rmbyext` tool from its GitHub repository. After the installation, `git` is removed to keep the image size small.
- **Entrypoint**: The container is set up to execute the `rmbyext` tool by default.
- **Default Command**: If no additional argument is provided, the tool defaults to handling `.txt` files.

## Directory Structure

The directory `storage-dir` contains the following files:

- `books.txt`
- `cars.txt`
- `meals.txt`
- `motor.pdf`
- `trucks.md`

## How to Use

### Building the Docker Image

To build the Docker image, use the following command:

```bash
docker image build -t exec-image:1.0 -f Dockerfile-exec .

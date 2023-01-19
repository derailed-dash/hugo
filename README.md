# Dazbo's Hugo

## Tagline

A Hugo image with git pre-installed.

## GitHub

https://github.com/derailed-dash/hugo

## Overview

This is a modified Docker container image, based on the Alpine klakegg/hugo.

It contains a docker-compose.yml for building the image from the Dockerfile, and launching the Hugo server.

## Usage Instructions

### Updating and Serving

Simply launch the container as follows:

```bash
docker compose up
```

Note that this configuration monitors for changes and automatically updates the site content.

### To Run Container Interactively

If you want to interactively work with the container (e.g. for debugging):

```bash
docker run --rm -it --entrypoint /bin/sh -v $(pwd):/src -p 1313:1313 hugo-engine:0.1
```

(Use `${pwd}` in Powershell.)

### To Run a Build

We can perform a one-off build to generate the output:

```bash
docker run --rm -it -v $(pwd):/src hugo-engine:0.1
```

By default, the data in the mapped volume (`/src`) is used to build the output in a folder called `public`.

Alternatively, from the interactive container, we can simply run the following, in order to build from the current directory:

```bash
hugo -s .
```
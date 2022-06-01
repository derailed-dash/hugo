# Dazbo's Hugo

## Tagline

A Hugo image with git pre-installed.

## GitHub

https://github.com/derailed-dash/hugo

## Overview

This is a modified Docker container image, based on the Alpine klakegg/hugo.

It contains a docker-compose.yml for building the image from the Dockerfile, and launching the Huge server.

## Usage Instructions

### Run the container interactively

```bash
docker run --rm -it --entrypoint /bin/sh -v $(pwd):/src -p 1313:1313 hugo-engine:0.1
```

### Updating and Serving

Simply launch the container as follows:

```bash
docker compose up
```

Note that this configuration monitors for changes and automatically updates the site content.

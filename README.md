# Dockerized Hugo Environment

## What is Hugo?

Hugo is a popular open-source static site generator written in Go. It is known for its incredible speed and flexibility. Unlike dynamic site generators (like WordPress) which build a page every time a visitor requests it, static site generators build the pages once, ahead of time. This results in faster loading times, improved security, and simpler hosting.

Hugo is a great choice for:

*   Blogs
*   Documentation websites
*   Portfolios
*   Landing pages

## Why Use This Dockerized Environment?

This repository provides a convenient and portable Docker-based environment for developing and building Hugo websites. The key benefits are:

*   **Consistency:** Ensures that you and your team are using the same version of Hugo and its dependencies, regardless of your local machine's setup.
*   **Isolation:** The entire environment is containerized, so it won't interfere with other projects or software on your system.
*   **Portability:** You can easily share and run this environment on any machine with Docker installed.
*   **Git Included:** This image comes with `git` pre-installed, which is useful for themes and version control.

This project is based on the `klakegg/hugo:0.111.3-alpine` image, providing a minimal and up-to-date Hugo setup.

## Usage Instructions

### Building and Serving Locally

To build the Docker image and start the Hugo development server, run:

```bash
docker compose up --build
```

Your site will be available at `http://localhost:1313`. The server will automatically watch for changes in your content and rebuild the site.

### Running Commands Interactively

To run commands inside the container, such as `hugo new site .`, you can start an interactive shell:

```bash
docker run --rm -it --entrypoint /bin/sh -v $(pwd):/src -p 1313:1313 hugo-engine:1.0
```
*(Use `${pwd}` instead of `$(pwd)` in Powershell.)*

### Performing a One-Off Build

To generate your static site into the `public` directory without starting the server:

```bash
docker run --rm -it -v $(pwd):/src hugo-engine:1.0
```

Inside the interactive container, you can also run the build command directly:
```bash
hugo -s .
```

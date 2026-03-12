## Docker-101 Lab – Our Application

This repository contains the **Our Application** Dockerfile and instructions for building and running the image.

### Prerequisites

- **Docker** installed and running on your machine.

### Build the Docker image

From the root of this project (where the `Dockerfile` lives), run:

```bash
docker build -t our-application .
```

This command:

- Uses the current directory as the build context.
- Builds an image based on the `Dockerfile`.
- Tags the resulting image as `our-application`.

### Run the Docker container

Once the image is built, start a container from it:

```bash
docker run --rm our-application
```

If your Node application listens on a specific port (for example, `3000`), and you want to access it from your host machine, publish that port:

```bash
docker run --rm -p 3000:3000 our-application
```

- **`--rm`**: automatically removes the container when it exits.
- **`-p 3000:3000`**: maps port `3000` inside the container to port `3000` on your host.

### Summary

1. **Build**: `docker build -t our-application .`
2. **Run (basic)**: `docker run --rm our-application`
3. **Run (with port mapping)**: `docker run --rm -p 3000:3000 our-application`


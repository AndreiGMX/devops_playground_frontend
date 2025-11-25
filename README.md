# DevOps Playground Frontend

This is the standalone frontend component of the DevOps Playground project. It serves a static HTML application using Nginx.

## 🚀 Getting Started

### Prerequisites

- Docker installed on your machine.

### Local Development

You can build and run the container locally using Docker:

```bash
# Build the image
docker build -t devops-playground-frontend .

# Run the container
docker run -p 8080:80 devops-playground-frontend
```

The application will be available at `http://localhost:8080`.

## 🏗 Architecture

- **Frontend**: Static HTML/CSS/JS served by Nginx.
- **Server**: Nginx (Alpine-based image).
- **Configuration**: Custom `nginx.conf` handles routing and API proxying.

## 🔄 CI

The project uses GitHub Actions for Continuous Integration and Delivery:

- **Workflow**: `.github/workflows/ci.yml`
- **Trigger**: Pushes to the `main` branch.
- **Registry**: GitHub Container Registry (GHCR).
- **Process**:
  1. Checks out code.
  2. Builds the Docker image.
  3. Pushes the image to GHCR with tags: `branch-name`, `branch-sha`, and `latest`.

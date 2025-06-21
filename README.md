# 🧠 Ollama with GPU Acceleration (Dockerized)

Run Ollama models locally with full GPU acceleration using Docker. This setup supports both **Linux** and **Windows (via WSL2)** environments.

---

## 📌 Project Overview

This repository provides a ready-to-run `docker-compose.yml` for deploying the [`ollama/ollama`](https://hub.docker.com/r/ollama/ollama) container with:

- NVIDIA GPU acceleration (via `nvidia-container-runtime`)
- Persistent model caching using volumes
- Exposed HTTP API on `localhost:11434`

---

## ⚙️ Prerequisites

### ✅ Required for Linux

- Docker: https://docs.docker.com/engine/install/linux-postinstall/
- Docker Compose v2+: `docker compose version`
- NVIDIA drivers (450+)
- [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html)

### ✅ Required for Windows (via WSL2)

- Docker Desktop (https://www.docker.com/products/docker-desktop/)
  - Enable WSL2 integration for your Linux distro (e.g. Ubuntu)
  - Enable GPU support under Settings > Resources > **WSL Integration** and **GPU**
- NVIDIA drivers for Windows: https://www.nvidia.com/Download/index.aspx
- WSL2 Linux kernel: `Ubuntu`, `Debian`, etc.

---

## 🛠️ Setup Instructions

### 🐧 On Linux

```bash
# Clone the repo
git clone https://github.com/your-org/ollama-gpu-docker.git
cd ollama-gpu-docker

# Create a directory to store model data
mkdir -p ./ollama

# Run the container
docker compose up -d
```

## Pull The Model
```bash
curl -X POST http://localhost:11434/api/pull -d '{"name": "llama3"}'
```
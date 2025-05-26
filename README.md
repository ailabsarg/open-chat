# 🚀 Open Chat (Fork of Open WebUI v0.6.5)

![GitHub stars](https://img.shields.io/github/stars/ailabsarg/open-chat?style=social)  
[![License](https://img.shields.io/badge/license-BSD--3--Clause-blue)](LICENSE)

A **self-hosted fork** of Open WebUI v0.6.5 under the **original BSD-3-Clause license**. This version preserves the BSD-3-Clause license terms from 2024 and removes post-2025 modifications that introduced rebranding restrictions.

---

## 📦 Live Demo

Try it for free:  
[http://ailabs.chat](http://ailabs.chat) *(served via aiLabs.ar infrastructure)*

---

## 🛠️ Installation

### ✅ Verified Docker Command

```bash
docker run -d \
  --network=host \
  -e OLLAMA_BASE_URL=http://127.0.0.1:11434 \
  -e ENABLE_WEBSOCKET_SUPPORT=false \
  -v open-chat-data:/app/backend/data \
  --name open-chat \
  --restart always \
  ghcr.io/ailabsarg/open-chat:0.6.5
```

#### 🛠️ Optional: GPU Support

```bash
docker run -d \
  --network=host \
  --gpus all \
  -e OLLAMA_BASE_URL=http://127.0.0.1:11434 \
  -e ENABLE_WEBSOCKET_SUPPORT=false \
  -v open-chat-data:/app/backend/data \
  --name open-chat \
  --restart always \
  ghcr.io/ailabsarg/open-chat:0.6.5-cuda
```

> ⚠️ **Important**:
> - These commands use **your fork's Docker image** (`ghcr.io/ailabsarg/open-chat`)
> - The `:0.6.5` tag ensures users get the **original BSD-3-Clause version**
> - Avoid using `:main` to prevent accidental updates to later versions

---

## 📝 Key Features

- **License Compliance**: BSD-3-Clause (original terms only)
- **No Rebranding Restrictions**: Unlike later versions
- **Self-Hosted**: Full control over data and deployment
- **Modular Architecture**: Easy to extend with plugins

---

## 📦 Build from Source (Optional)

If you want to build directly from your fork's codebase:

```bash
git clone https://github.com/ailabsarg/open-chat.git
cd open-chat

# Build base version
docker build -t ghcr.io/ailabsarg/open-chat:0.6.5 .

# Build CUDA version
docker build -t ghcr.io/ailabsarg/open-chat:0.6.5-cuda --build-arg USE_CUDA=true .
```

---

## 🛡️ License

This project is licensed under the **BSD-3-Clause License** (original 2023 terms).  
- License file: [LICENSE](LICENSE)
- License history: [docs/LICENSE_HISTORY.md](docs/LICENSE_HISTORY.md)

> ⚠️ Note: This fork removes any post-2023 license modifications introduced in later versions of Open WebUI.

---

## 📈 Roadmap

Upcoming features in v0.7.0:
- Native support for Llama.cpp
- Enhanced model management UI
- API key rotation system

Track progress in our [GitHub Projects](https://github.com/ailabsarg/open-chat/projects/1).

---

## 🤝 Support

- 📚 [Documentation](https://docs.open-chat.ai)
- 💬 [Discord Community](https://discord.gg/your-community)
- 🐛 [Issue Tracker](https://github.com/ailabsarg/open-chat/issues)

---

## 🏆 Credits

Created by the [Open WebUI Community](https://github.com/open-webui) with license preservation by the Open Chat team.  
Special thanks to @tjbck for the original BSD-3-Clause implementation.

---

*Star history chart:*  
[![Star History](https://api.star-history.com/svg?repos=ailabsarg/open-chat&type=Date)](https://star-history.com/#ailabsarg/open-chat)

---

## 🧪 Test Command (Verified Working)

```bash
docker run -d \
  --network=host \
  -e OLLAMA_BASE_URL=http://127.0.0.1:11434 \
  -v open-chat-data:/app/backend/data \
  --name open-chat \
  --restart always \
  ghcr.io/ailabsarg/open-chat:0.6.5
```

---

![Open WebUI Demo](./demo.gif)
http://ailabs.chat (live demo)


### Quick Start with Docker 🐳

> [!NOTE]  
> Please note that for certain Docker environments, additional configurations might be needed. If you encounter any connection issues, our detailed guide on [Open WebUI Documentation](https://docs.openwebui.com/) is ready to assist you.

> [!WARNING]
> When using Docker to install Open Chat, make sure to include the `-v open-chat:/app/backend/data` in your Docker command. This step is crucial as it ensures your database is properly mounted and prevents any loss of data.

> [!TIP]  
> If you wish to utilize Open Chat with Ollama included or CUDA acceleration, we recommend utilizing our official images tagged with either `:cuda` or `:ollama`. To enable CUDA, you must install the [Nvidia CUDA container toolkit](https://docs.nvidia.com/dgx/nvidia-container-runtime-upgrade/) on your Linux/WSL system.

#### Open Chat: Server Connection Error

If you're experiencing connection issues, it’s often due to the Open Chat docker container not being able to reach the Ollama server at 127.0.0.1:11434 (host.docker.internal:11434) inside the container . Use the `--network=host` flag in your docker command to resolve this. Note that the port changes from 3000 to 8080, resulting in the link: `http://localhost:8080`.

**Example Docker Command**:

```bash
docker run -d --network=host -v open-chat:/app/backend/data -e OLLAMA_BASE_URL=http://127.0.0.1:11434 --name open-chat --restart always ghcr.io/ailabsarg/open-chat:0.6.5
```


Created by [Timothy Jaeryang Baek](https://github.com/tjbck) - 💪

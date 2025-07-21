<a name="readme-top"></a>

<div align="center">
  <img src="./docs/static/img/logo.png" alt="Logo" width="200">
  <h1 align="center">OpenHands: Code Less, Make More</h1>
</div>

<div align="center">
  <a href="https://github.com/All-Hands-AI/OpenHands/graphs/contributors"><img src="https://img.shields.io/github/contributors/All-Hands-AI/OpenHands?style=for-the-badge&color=blue" alt="Contributors"></a>
  <a href="https://github.com/All-Hands-AI/OpenHands/stargazers"><img src="https://img.shields.io/github/stars/All-Hands-AI/OpenHands?style=for-the-badge&color=blue" alt="Stargazers"></a>
  <a href="https://github.com/All-Hands-AI/OpenHands/blob/main/LICENSE"><img src="https://img.shields.io/github/license/All-Hands-AI/OpenHands?style=for-the-badge&color=blue" alt="MIT License"></a>
  <br/>
  <a href="https://docs.all-hands.dev/usage/getting-started"><img src="https://img.shields.io/badge/Documentation-000?logo=googledocs&logoColor=FFE165&style=for-the-badge" alt="Check out the documentation"></a>
  <a href="https://arxiv.org/abs/2407.16741"><img src="https://img.shields.io/badge/Paper%20on%20Arxiv-000?logoColor=FFE165&logo=arxiv&style=for-the-badge" alt="Paper on Arxiv"></a>
  <hr>
</div>

## 🚀 About OpenHands

OpenHands is an AI-powered platform for software development. Our agents can modify code, run commands, browse the web, and call APIs - just like a human developer.

![App screenshot](./docs/static/img/screenshot.png)

## 🔧 Quick Start

### ☁️ Cloud Option
The easiest way to get started is with [OpenHands Cloud](https://app.all-hands.dev) ($20 free credits for new users).

### 💻 Local Installation

Run OpenHands locally with Docker:

```bash
docker pull docker.all-hands.dev/all-hands-ai/runtime:0.49-nikolaik

docker run -it --rm --pull=always \
    -e SANDBOX_RUNTIME_CONTAINER_IMAGE=docker.all-hands.dev/all-hands-ai/runtime:0.49-nikolaik \
    -v /var/run/docker.sock:/var/run/docker.sock \
    -v ~/.openhands:/.openhands \
    -p 3000:3000 \
    --name openhands-app \
    docker.all-hands.dev/all-hands-ai/openhands:0.49
```

Access at [http://localhost:3000](http://localhost:3000) and connect your preferred LLM provider.

## 📖 Resources

- [Documentation](https://docs.all-hands.dev/usage/getting-started)
- [Installation Guide](https://docs.all-hands.dev/usage/installation)
- [Troubleshooting](https://docs.all-hands.dev/usage/troubleshooting)
- [Development Guide](https://github.com/All-Hands-AI/OpenHands/blob/main/Development.md)

## 🤝 Community

- [Slack](https://join.slack.com/t/openhands-ai/shared_invite/zt-3847of6xi-xuYJIPa6YIPg4ElbDWbtSA)
- [Discord](https://discord.gg/ESHStjSjD4)
- [GitHub Issues](https://github.com/All-Hands-AI/OpenHands/issues)

## 📜 License

Distributed under the MIT License. See [`LICENSE`](./LICENSE) for more information.

## 📚 Citation

```
@inproceedings{
  wang2025openhands,
  title={OpenHands: An Open Platform for {AI} Software Developers as Generalist Agents},
  author={Xingyao Wang and Boxuan Li and Yufan Song and Frank F. Xu and Xiangru Tang and Mingchen Zhuge and Jiayi Pan and Yueqi Song and Bowen Li and Jaskirat Singh and Hoang H. Tran and Fuqiang Li and Ren Ma and Mingzhang Zheng and Bill Qian and Yanjun Shao and Niklas Muennighoff and Yizhe Zhang and Binyuan Hui and Junyang Lin and Robert Brennan and Hao Peng and Heng Ji and Graham Neubig},
  booktitle={The Thirteenth International Conference on Learning Representations},
  year={2025},
  url={https://openreview.net/forum?id=OJd3ayDDoF}
}
```

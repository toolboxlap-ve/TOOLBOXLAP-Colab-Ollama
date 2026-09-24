# TOOLBOXLAP — Google Colab + Ollama + ngrok API

One-cell educational/demo launcher for running a Hugging Face / Ollama model on a Google Colab GPU runtime, exposing an OpenAI-compatible API through ngrok, testing it, and copying the resulting Base URL into Cline.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama/blob/main/colab/TOOLBOXLAP-Colab-Ollama.ipynb)

**Website:** https://toolboxlap.com  |  **YouTube:** https://www.youtube.com/@TOOLBOXLAP-u1c  |  **GitHub:** https://github.com/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama

## Quick start

1. Open the notebook with the **Open in Colab** button above.
2. Select a GPU runtime.
3. Run the single code cell.
4. Enter a model name, or press Enter for the default model.
5. Enter your ngrok authtoken when prompted. The input is hidden.
6. Wait for Ollama to download and load the model.
7. The notebook starts the OpenAI-compatible Flask API and the ngrok tunnel.
8. Copy the printed Base URL into Cline.

## What it does

The one-cell workflow is:

**Colab GPU → Ollama → Hugging Face model → OpenAI-compatible API → ngrok → Cline / VS Code**

The launcher uses a default public client model ID of `toolboxlap` and automatically tests the public endpoint before printing the final connection details.

## Default model

```text
hf.co/HauhauCS/Qwen3.5-9B-Uncensored-HauhauCS-Aggressive:Q4_K_M
```

You can enter another Hugging Face / Ollama-compatible model, provided it fits the available GPU memory and runtime resources.

## Cline setup

After the cell finishes, copy the values it prints:

```text
Provider: OpenAI Compatible
Base URL: https://YOUR-NGROK-URL/v1
Model ID: toolboxlap
Custom Header: ngrok-skip-browser-warning = true
```

## API testing

The demo uses this API testing site:

https://api-hero.pages.dev/

## Related links

- Google Colab: https://colab.research.google.com/
- Kaggle: https://www.kaggle.com/
- ngrok: https://ngrok.com/
- TOOLBOXLAP Kaggle API repo: https://github.com/toolboxlap-ve/TOOLBOXLAP-kaggle-api
- TOOLBOXLAP website: https://toolboxlap.com/

## Important note about Colab

Google's current FAQ says managed Colab runtimes prohibit offering unrelated web services and connecting to remote proxies. It also says resource availability and limits can change over time.

This repository is provided as an educational demonstration of the workflow and does not promise that every Google-managed Colab session will permit or maintain the public tunnel. A runtime may block, terminate, or otherwise restrict the workflow. Follow Google's current Colab terms and policies when running it.

## Security

Never commit an ngrok authtoken, API key, or other secret to GitHub. The notebook requests the ngrok token interactively with hidden input, and the token is not stored in this repository.

## Repository structure

```text
TOOLBOXLAP-Colab-Ollama/
├── README.md
├── LICENSE
└── colab/
    ├── TOOLBOXLAP-Colab-Ollama.ipynb
    └── TOOLBOXLAP-Colab-Ollama-Network.ipynb
```

## License

MIT

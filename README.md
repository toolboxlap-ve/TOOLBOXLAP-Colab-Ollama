# TOOLBOXLAP — Google Colab + Ollama

Run Hugging Face / Ollama models in a Google Colab GPU runtime with a one-cell launcher.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama/blob/main/colab/TOOLBOXLAP-Colab-Ollama.ipynb)

**Website:** https://toolboxlap.com  |  **YouTube:** https://www.youtube.com/@TOOLBOXLAP-u1c  |  **GitHub:** https://github.com/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama

## Notebooks

### Standard managed-Colab notebook
Use this for Ollama + Hugging Face + a local OpenAI-compatible API inside the managed Colab runtime:

https://colab.research.google.com/github/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama/blob/main/colab/TOOLBOXLAP-Colab-Ollama.ipynb

### Network-capable notebook
Use this when the notebook kernel is a **local/self-controlled runtime** connected through the Colab interface. In that environment, the launcher can optionally open an ngrok tunnel and print a public OpenAI-compatible Base URL:

https://colab.research.google.com/github/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama/blob/main/colab/TOOLBOXLAP-Colab-Ollama-Network.ipynb

The network notebook automatically detects the runtime. On a Google-managed Colab runtime it keeps the API local and does not start ngrok.

## What this project does

The workflow is:

- start a GPU runtime
- install/start Ollama
- pull a Hugging Face / Ollama model
- expose an OpenAI-compatible endpoint
- test the endpoint
- optionally create a public ngrok tunnel when running on a local/self-controlled runtime

## Important Colab limitation

Google's current Colab FAQ says managed runtimes prohibit offering unrelated web services and connecting to remote proxies. This repository does not attempt to bypass those restrictions. The public-tunnel mode is only enabled when the Python kernel is outside Colab's managed runtime.

For a managed Colab session, use the local API mode. For a public API demonstration, use a local/self-controlled runtime through the Colab interface, or use the TOOLBOXLAP Kaggle project where applicable.

## Quick start

1. Open one of the notebooks above.
2. In managed Colab, select a GPU runtime.
3. Run the single code cell.
4. Enter a model name or press Enter for the default.
5. Wait for Ollama to download/start the model.
6. The notebook prints the local API URL.
7. In the network-capable notebook, a local/self-controlled runtime can additionally enter an ngrok authtoken and receive a public Base URL.

## Default model

```text
hf.co/HauhauCS/Qwen3.5-9B-Uncensored-HauhauCS-Aggressive:Q4_K_M
```

Choose a model that fits the available GPU memory and runtime resources.

## API

Local endpoint:

```text
http://127.0.0.1:5000/v1
```

Public endpoint (local/self-controlled runtime only):

```text
https://YOUR-NGROK-URL/v1
```

Public client settings:

```text
Provider: OpenAI Compatible
Model ID: toolboxlap
Custom Header: ngrok-skip-browser-warning = true
```

## Related resources

- Kaggle: https://www.kaggle.com/
- ngrok: https://ngrok.com/
- API test site used in the Kaggle video: https://api-hero.pages.dev/
- TOOLBOXLAP Kaggle API repo: https://github.com/toolboxlap-ve/TOOLBOXLAP-kaggle-api
- TOOLBOXLAP website: https://toolboxlap.com/

## Security

Never commit API keys or ngrok tokens to GitHub. The network notebook requests the ngrok token interactively with hidden input.

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

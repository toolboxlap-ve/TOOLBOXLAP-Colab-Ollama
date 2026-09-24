# TOOLBOXLAP — Google Colab + Ollama

Run Hugging Face / Ollama models inside a Google Colab GPU runtime with a one-cell launcher, then test an OpenAI-compatible API locally inside the notebook.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama/blob/main/colab/TOOLBOXLAP-Colab-Ollama.ipynb)

**Website:** https://toolboxlap.com  |  **YouTube:** https://www.youtube.com/@TOOLBOXLAP-u1c  |  **GitHub:** https://github.com/toolboxlap-ve/TOOLBOXLAP-Colab-Ollama

## What this project does

This companion repo follows the same TOOLBOXLAP workflow used in the Kaggle project:

- start a GPU notebook runtime
- install/start Ollama
- pull a Hugging Face / Ollama model
- expose an OpenAI-compatible endpoint inside the notebook runtime
- send a local test request

## Important Colab limitation

Google's current Colab FAQ says managed runtimes do not allow offering unrelated web services and prohibit connecting to remote proxies. Because of those restrictions, this repo intentionally keeps the API **local to the Colab runtime** and does not include an ngrok public-tunnel launcher.

For a public OpenAI-compatible API workflow, use the TOOLBOXLAP Kaggle repo or another environment where that type of service is permitted.

## Quick start

1. Open the notebook with the **Open in Colab** button above.
2. In Colab, select a GPU runtime.
3. Run the single code cell.
4. Enter a model name when prompted, or press Enter to use the default model.
5. The notebook starts Ollama and a local OpenAI-compatible endpoint.
6. The notebook tests `/v1/models` locally.

## Default model

```text
hf.co/HauhauCS/Qwen3.5-9B-Uncensored-HauhauCS-Aggressive:Q4_K_M
```

You can replace it with another compatible model that fits the available GPU memory and runtime resources.

## Local API

The notebook uses:

```text
http://127.0.0.1:5000/v1
```

This address is only reachable from the Colab runtime itself. It is not a public internet endpoint.

## Related resources

- Kaggle: https://www.kaggle.com/
- ngrok: https://ngrok.com/
- API test site used in the Kaggle video: https://api-hero.pages.dev/
- TOOLBOXLAP Kaggle API repo: https://github.com/toolboxlap-ve/TOOLBOXLAP-kaggle-api
- TOOLBOXLAP website: https://toolboxlap.com/

## Security

Do not commit API keys, access tokens, or other secrets to GitHub. Enter secrets interactively in the notebook when a workflow actually requires them.

## Repository structure

```text
TOOLBOXLAP-Colab-Ollama/
├── README.md
├── LICENSE
└── colab/
    └── TOOLBOXLAP-Colab-Ollama.ipynb
```

## License

MIT

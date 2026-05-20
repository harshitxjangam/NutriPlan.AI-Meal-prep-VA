# NutriPlan AI

NutriPlan AI is a personalized meal planning and grocery budget virtual assistant. It uses open-source language models with recipe, nutrition, pantry, profile, cost, and web-search tools to answer food planning questions.

## Main Notebook

Open:

`Nutriplan.AI final.ipynb`

Run sections 1-8 to install dependencies, sign in to Hugging Face, build the recipe database, load the VA pipeline, and launch the Gradio chat UI.

The notebook requires a Hugging Face token. Add your own token when prompted or store it as `HF_TOKEN` in Colab secrets. Do not commit tokens or credentials.

After the Gradio UI opens, click `Load selected model` before asking a question. Loading the model is separated from chat requests so the interface does not appear to hang or time out during first model load. Phi-3.5-mini is recommended for quick testing; Llama-3.1-8B can take longer to load depending on the GPU runtime.

## What The UI Supports

- Select Phi-3.5-mini or Llama-3.1-8B
- Load or switch the selected Hugging Face model before chat
- Select one of three sample user profiles
- Ask default or custom meal planning questions
- Get profile-aware recipe, pantry, nutrition, budget, web-search, and food-safety answers
- View response metadata such as model, latency, and tool calls

## Recommended Runtime

Use Google Colab with GPU enabled:

1. Open the notebook in Colab.
2. Go to `Runtime > Change runtime type > GPU`.
3. Run sections 1-8.
4. Use the Gradio link printed by the final UI cell.

The models are loaded from Hugging Face using 4-bit quantization when CUDA is available.

## Benchmark Artifacts

The `benchmarks/` folder contains the saved model comparison and safety outputs:

- `benchmark_results.csv`
- `benchmark_summary.csv`
- `security_results.csv`
- `caching_timing.json`
- `benchmark_partial.json`
- `Nutriplan.AI benchmarks.ipynb`

These files are for result inspection and report support. The main testable application is the root notebook.

## Notes

- Live grocery deal results depend on DuckDuckGo search availability in the runtime.
- Nutrition and grocery costs are estimates from the dataset and ingredient price assumptions.
- This repo does not include model weights, raw datasets, database files, or personal API tokens.

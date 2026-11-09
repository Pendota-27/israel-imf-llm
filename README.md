# israel-imf-llm

A Google Colab notebook that reads one IMF Article IV report with Gemini models and tests the results against the report.

**Source:** IMF Country Report No. 26/161, *Israel: 2026 Article IV Consultation* (77 pages), in `data/`. No IMF Article IV or Staff Report on Israel is dated 2024 or 2025, so this is the nearest report; it presents outturns for both years.

Open `Israel_Article_IV_Against_The_Brief.ipynb` in Colab with `data/` and `cache/` in `/content`, then choose *Runtime > Run all*. All 148 model requests are answered from `cache/replies.duckdb`, so no API key is needed. To call the models again, add a Gemini key as the Colab secret `GEMINI_FREE_KEY` and delete that file.

Model calls run concurrently with `asyncio`. Writer: `gemini-3.5-flash`. Judge: `gemini-3.8-flash`. Embeddings: `intfloat/e5-base-v2` with a FAISS `IndexFlatL2`. Results and the two 300 dpi figures are in `results/`.

MIT licence, see `LICENSE`. The IMF report remains the property of the International Monetary Fund and is included only so the notebook can run.

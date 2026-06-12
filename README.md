# AI-Generated Greenwashing in Fashion Marketing

Analysis code and anonymised data for "AI-Generated Greenwashing in Fashion Marketing: The Role of Knowledge Grounding and Consumer Perceptions".

Four Turkish fashion brands (Companies F, G, H, M) were studied across five greenwashing types (vagueness, misleading, concealment, overselling, irrelevance) and three grounding conditions: no context (NC), unstructured information (UI), and structured information via knowledge graph (SI).

## Notebooks

- `01-KG-RAG.ipynb` — Extract entities and factual statements from company web pages (GPT-4.1)
- `01_2_updatedcsv_to_graph.ipynb` — Build per-company knowledge graphs from verified entity CSVs
- `02_generate_content_and_judge_all.ipynb` — Generate 60 marketing texts (4 companies × 5 types × 3 conditions) and score with LLM judge
- `03_judge_evaluation.ipynb` — Inspect and aggregate raw judge scores
- `03_select_outputs.ipynb` — Stratified selection of 20-text anchor set for human validation
- `04_human_agreement.ipynb` — Inter-rater reliability: exact/adjacent agreement, weighted kappa, binomial tests
- `05_kruskal_wallis.ipynb` — Kruskal-Wallis tests and Dunn post-hoc comparisons across grounding conditions

## Data

- `extracted_entities/` — Verified entity–attribute–value triples per company (CSV + raw JSON)
- `knowledge_graphs/` — Per-company knowledge graphs in node-link JSON
- `generated_content/` — 60 generated texts with LLM-judge scores and justifications
- `greenwashing_evaluation_rubric.json` — Four-point scoring rubric for the five greenwashing types
- `greenwashing_prompt_types.xlsx` — The five greenwashing-inducing prompt definitions
- `anchor_set_20_89.csv` — 20-text anchor set with human rater and LLM judge scores

## Notes

**Anonymisation:** company names are scrubbed from all file names and contents. Original source documents and the Turkish expert rater manual are excluded and available on request.

**Requirements:** Google Colab, Python 3.10. OpenAI API keys loaded from Colab `userdata` secrets — no keys stored here. Packages: `openai`, `networkx`, `pandas`, `scipy`, `scikit-learn`.

**Citation:** to be added upon publication.

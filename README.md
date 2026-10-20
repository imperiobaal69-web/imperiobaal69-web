# Paulo Villalobos

Software engineer. Machine learning, data pipelines, backend systems.
Porto, Portugal · remote · [CV](https://paulo.foaap.app/Paulo-Villalobos-CV.pdf) · [paulo@foaap.app](mailto:paulo@foaap.app)

Most of my work has been private. These are the systems I've chosen to publish.
Every number below is produced by code in the linked repository.

---

**[cordis-field-classifier](https://github.com/imperiobaal69-web/cordis-field-classifier)** - machine learning

52,000 EU research projects classified into 37 scientific fields. Prior,
TF-IDF, frozen embeddings and a fine-tuned transformer under one protocol;
tested on a later funding programme the models never saw.

- Fine-tuned model: 0.709 micro-F1 in-distribution and 0.709 on the later
  programme, where TF-IDF falls to 0.637 (95% bootstrap intervals on every
  number).
- The official CORDIS export makes `pandas.read_csv` drop 285 projects and
  corrupt 960 more without an error. The reader here recovers every record.
- Fine-tuning first stalled at the label-frequency baseline; traced to a pooler
  the encoder never trained, replaced, and documented.

`Python` `PyTorch` `Transformers` `scikit-learn` `FastAPI` `Docker`

**[pt-open-data-pipeline](https://github.com/imperiobaal69-web/pt-open-data-pipeline)** - data engineering

Portuguese card-spending statistics (INE) for 308 municipalities since 2020:
immutable raw layer with checksums, DuckDB, dbt staging -> marts, incremental
loads, Parquet exports, scheduled refresh.

- 82 dbt tests, including additivity across geographic levels and a guard
  that fails the build if INE changes a series' unit or scaling. They caught a
  published inconsistency: one region-month where INE's online figure is 0 while
  its 13 municipalities add up to 2,553.
- Documents the API behaviour it depends on (silent latest-month default,
  failures returned as HTTP 200) and what the public data cannot answer.

`Python` `SQL` `dbt` `DuckDB` `Parquet`

**[mesh-governance](https://github.com/imperiobaal69-web/mesh-governance)** - software engineering

Evidence store with append-only history enforced by database triggers,
idempotent transactional commands, independent review bound to exact revisions,
and publication rules that refuse rollback to stale evidence. 42 tests,
standard library only, typed under `mypy --strict`.

`Python` `SQLite`

---

Also: [foaap-engine-public](https://github.com/imperiobaal69-web/foaap-engine-public)
(stateful context engine for AI applications, JavaScript, 32 tests) ·
[energy-baseline-public](https://github.com/imperiobaal69-web/energy-baseline-public)
(validation layer for LLM extraction, 13 tests) ·
[bicis-sapiens-web](https://github.com/imperiobaal69-web/bicis-sapiens-web)
(production React + Supabase site, row-level security checked in CI) ·
live: [NEXUS](https://nexus.foaap.app/#/), [FOAAP](https://foaap.app/)

I use AI assistants while building. The problem, the architecture, the
evaluation and every claim are mine to defend.

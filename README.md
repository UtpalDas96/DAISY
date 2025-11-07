# 🌼 DAISY — Deloitte AI System

**Purpose**: DAISY is a repository template and starter kit to help Deloitte teams build an internal AI practice. It contains curated study material, boilerplate code for ML/Generative/Production workflows, tutorial links, onboarding checklists, and reusable GitHub templates.

---

## Quick goals

* Centralize learning resources (reading lists, courses, cheat-sheets).
* Provide production-ready boilerplate (Python packages, FastAPI inference, Docker, CI/CD).
* Include reproducible examples (notebooks, small datasets, experiments).
* Provide governance & contribution guidelines for internal teams.

---

## Top-level structure (suggested)

```
DAISY/
├─ .github/
│  ├─ workflows/
│  │  ├─ ci.yml
│  │  └─ publish.yml
│  ├─ ISSUE_TEMPLATE/
│  │  ├─ bug.md
│  │  └─ feature_request.md
│  └─ PULL_REQUEST_TEMPLATE.md
├─ docs/
│  ├─ learning_path.md
│  ├─ onboarding.md
│  └─ style_guides.md
├─ study_material/
│  ├─ readme.md
│  ├─ courses.md
│  └─ cheat_sheets/
├─ boilerplate/
│  ├─ python_package_template/
│  │  ├─ src/aaa/
│  │  ├─ tests/
│  │  ├─ pyproject.toml
│  │  └─ README.md
│  ├─ fastapi_inference/
│  │  ├─ app/
│  │  ├─ Dockerfile
│  │  └─ requirements.txt
│  └─ streaming_agent_template/
├─ tutorials/
│  ├─ 01-training-basics.ipynb
│  ├─ 02-fine-tuning.ipynb
│  └─ 03-rag-with-neo4j.md
├─ examples/
│  ├─ small_classification/
│  └─ rag_demo/
├─ infra/
│  ├─ terraform/
│  └─ k8s/
├─ scripts/
│  └─ helper_scripts.sh
├─ LICENSE
├─ README.md
├─ CONTRIBUTING.md
└─ CODE_OF_CONDUCT.md
```

---

## README.md (starter)

````
# DAISY — Deloitte AI System

DAISY is a starter repo to accelerate building AI capability across Deloitte teams. It contains curated study material, production-ready boilerplate, tutorials and examples.

## Contents
- `study_material/` — curated learning paths & cheat-sheets
- `boilerplate/` — reproducible templates (Python package, inference API, Docker)
- `tutorials/` — step-by-step tutorials & notebooks
- `examples/` — small runnable demos
- `docs/` — onboarding, style guides

## Get started (local)
1. Clone:
   ```bash
   git clone git@github.com:YOUR_ORG/DAISY.git
   cd DAISY
````

2. Create a Python venv and install dependencies (example for boilerplate FastAPI):

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   pip install -r boilerplate/fastapi_inference/requirements.txt
   uvicorn boilerplate.fastapi_inference.app.main:app --reload
   ```

## Contributing

See `CONTRIBUTING.md`.

## License

This project uses the MIT License — see `LICENSE`.

```
```

---

## Example CONTRIBUTING.md (high level)

* Use issues for feature requests & bugs.
* Follow the branching model: `main` (stable), `dev` (integration), feature branches as `feature/<short-desc>`.
* Add unit tests for new code (pytest).
* Run formatters and linters before PR (black, ruff, isort).
* Fill PR template and link related issues.

---

## Suggested CI: .github/workflows/ci.yml (summary)

* Matrix: python versions (3.10, 3.11)
* Steps: checkout, setup python, install deps, run ruff/black check, run pytest, build Docker image (optional)

(Include an actual example `ci.yml` when you want — I can paste a ready-to-run GitHub Actions file.)

---

## Boilerplate highlights

**Python package template**

* `pyproject.toml` + `poetry` or `pip`-native layout
* `src/` layout, proper unit tests, `tox` or `nox` matrix for testing

**FastAPI inference service**

* Health endpoint
* /predict endpoint: accepts JSON, returns predictions
* Model loading from `models/` or huggingface/onnx cache
* Dockerfile optimized for small image (multi-stage)

**RAG / Vector Store example**

* Notebook showing embedding generation (sentence-transformers), vector store (FAISS or Neo4j vector) and a minimal RAG pipeline

**Agent template**

* Shell to integrate a planner, executor, and tool wrappers (calendar, slack, google drive) — safe mocked integrations

---

## Study material (example lists)

* Foundations: Linear Algebra, Probability, Optimization — recommended books and 3-week study plan.
* ML: CS229 notes, Fast.ai course, Hands-On ML (Aurélien Géron)
* LLMs: Papers: Attention Is All You Need, Transformer surveys; Tutorials: Hugging Face course; Practical: fine-tuning, inference optimization.
* Responsible AI: fairness, explainability, model cards (write templates in `docs/`)

---

## Governance & Templates

* `MODEL_CARDS/` template for every model added
* `SECURITY.md` quick guide for handling data and secrets
* `DATA_LICENSES.md` guidance on allowed datasets

---

## Onboarding checklist (docs/onboarding.md)

* Setup GitHub + 2FA
* Access to Deloitte internal packages/registry
* Follow `README` and run first demo
* Complete "DAISY learning path" (first three modules)

---

## Next steps I can do for you (pick any and I will execute now):

* Generate full `ci.yml` GitHub Actions file.
* Create a ready-to-copy `FastAPI` inference boilerplate (complete with Dockerfile and sample model loader).
* Produce `pyproject.toml` + package skeleton for `python_package_template`.
* Produce `README.md`, `CONTRIBUTING.md`, `LICENSE` full content files for you to paste into the repo.

---

If you want I can now generate specific files (CI, FastAPI sample, Python package skeleton) — say which one and I'll produce the full content ready to paste.

*— Utpal (DAISY helper)*

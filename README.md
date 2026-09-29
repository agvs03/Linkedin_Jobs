# LinkedIn Jobs – AI-Assisted Job Application Bot

A Python/Selenium bot that searches LinkedIn job listings and uses an LLM (OpenAI, Gemini, Claude, Ollama via LangChain) to answer application questions and generate a tailored resume for each role.

> **Credit:** This project is based on the open-source [Auto_Jobs_Applier_AIHawk](https://github.com/feder-cr/Auto_Jobs_Applier_AIHawk) by feder-cr, adapted for personal learning. The resume generator lives in the companion repo [Resume_Builder](https://github.com/agvs03/Resume_Builder).

> **Note:** Automated interaction with LinkedIn may violate its User Agreement. Use responsibly and at your own risk — this repo is for educational purposes.

## Features
- Job search filtered by position, location, experience level, job type and date posted
- LLM-generated answers to application form questions
- Per-job tailored resume PDF generation
- Pluggable LLM back-ends: OpenAI, Gemini, Anthropic, Ollama, Hugging Face

## Project structure
```
main.py                     # CLI entry point
app_config.py               # Runtime settings
src/
  aihawk_authenticator.py   # LinkedIn login flow
  aihawk_job_manager.py     # Job search + iteration
  aihawk_easy_applier.py    # Fills "Easy Apply" forms
  llm/llm_manager.py        # LLM abstraction layer
data_folder_example/        # Sample config / resume / secrets
tests/                      # pytest suite
docs/                       # Setup guides (PDF)
```

## Setup
```bash
git clone git@github.com:agvs03/Linkedin_Jobs.git
cd Linkedin_Jobs
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Configure the files in `data_folder/`:

| File | Purpose |
|---|---|
| `secrets.yaml` | Your LLM API key (`llm_api_key`). **Never commit a real key.** |
| `config.yaml` | Search preferences and LLM model selection |
| `plain_text_resume.yaml` | Your resume in structured YAML |

## Run
```bash
python main.py
```

## Tests
```bash
pytest
```

## License
MIT – see [LICENSE](LICENSE).

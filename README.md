# Fine-Tune-Invoice-Parser
# Invoice Parser Fine-Tuning (SmolVLM / Idefics-3 + TRL + LoRA)

Fine-tune **HuggingFaceTB/SmolVLM-Instruct (Idefics-3)** to extract structured JSON from invoices using the dataset
[`mychen76/invoices-and-receipts_ocr_v1`]. This repo provides:
- End-to-end training script (dataset → preprocessing → LoRA → TRL SFT → eval)
- Reproducible environment (pip)
- Optional GPU/precision guidance (bf16/fp16)
- Simple website header animation for your project page (HTML/CSS/SVG) ✨

---

## 1) Quickstart (Colab)

> The simplest path is Colab — 1 GPU, paste the **`colab_train.py`** cell into a single Colab cell.

- Open Colab → Runtime ▸ Change runtime type ▸ **GPU**
- Copy/paste **`colab_train.py`** into one cell and run.
- Outputs are saved to `./outputs` and `./fine_tuned_model`.

---

## 2) Local Setup (Linux/Mac)

```bash
git clone <your-repo-url> invoice-parser-vlm
cd invoice-parser-vlm

# Python 3.10+ recommended
python -m venv .venv
source .venv/bin/activate

pip install --upgrade pip
pip install -r requirements.txt


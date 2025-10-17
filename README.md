# 🧾 Fine-Tune-Invoice-Parser

### Invoice Parser Fine-Tuning (SmolVLM / Idefics-3 + TRL + LoRA)

This project fine-tunes **HuggingFaceTB/SmolVLM-Instruct (Idefics-3)** to extract structured JSON data from invoice images using the dataset  
[`mychen76/invoices-and-receipts_ocr_v1`](https://huggingface.co/datasets/mychen76/invoices-and-receipts_ocr_v1).

It’s designed as an **end-to-end, single-file Colab workflow** — load → preprocess → fine-tune (LoRA + TRL SFT) → evaluate.

---

## 🌟 Features

- 🔧 **One-click training**: Run everything inside `colab_train.ipynb`
- 🧠 **Vision-Language Fine-Tuning** with *SmolVLM/Idefics-3*
- ⚙️ **LoRA + TRL SFT** integration for efficient parameter-efficient training
- 🧾 **Evaluation Script** for loss + output comparison
- 💡 **Colab-friendly** — no API keys, fully open-source
- 🚀 **Reproducible Environment** (uses specific versions of `transformers`, `trl`, `peft`)

---

## 🪄 Quickstart (Google Colab)

1. Open the Colab notebook:  
   **[`colab_train.ipynb`](https://colab.research.google.com/github/Vishnuratee/Fine-Tune-Invoice-Parser/blob/main/Fine-tune_Invoice_Parser.ipynb)**

2. In Colab:
   - Go to **Runtime → Change runtime type → GPU**
   - Click **Run all**

3. The script will:
   - Download dataset  
   - Preprocess & format training JSON  
   - Apply LoRA adapters  
   - Fine-tune via TRL SFT  
   - Save checkpoints in `./outputs/`  
   - Save the final model to `./fine_tuned_model/`  
   - Run evaluation (`loss + predictions`)

---

## 🧰 Local Setup (Linux / Mac)

```bash
# Clone repository
git clone https://github.com/Vishnuratee/Fine-Tune-Invoice-Parser.git
cd Fine-Tune-Invoice-Parser

# Create environment
python3 -m venv venv
source venv/bin/activate

# Install dependencies
pip install --upgrade pip
pip install -r requirements.txt

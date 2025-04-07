# Cell Annotation using scGPT

Hey! This repo contains my implementation of **cell annotation using scGPT** — a transformer-based model designed for working with single-cell RNA sequencing (scRNA-seq) data.

I used the official [scGPT GitHub repo](https://github.com/bowang-lab/scGPT) and ran the code in the provided `.ipynb` notebook to explore how this model can help in predicting cell types based on gene expression data.

This was mainly an exploration project for learning, and I’m sharing the code + results here in case anyone else is trying to run this and wants a headstart.

---

## Files in This Repo

- `cell_annotation scgpt.ipynb` – Jupyter notebook where I ran the model and tested cell annotation on scRNA-seq data.
- `README.md` – You're reading it :)

---

## About scGPT

scGPT is like ChatGPT... but for cells. It’s a transformer-based model trained on single-cell data to understand gene patterns, batch effects, and even cell types. It's been trained using masked modeling (just like BERT), and fine-tuned to do tasks like:

- Cell type annotation
- Batch correction
- Gene imputation
- and more.

In this notebook, I focused on the **cell annotation** part — basically predicting what type of cell it is, based on its gene expression.

---

## How I Ran the Notebook

1. Cloned the original scGPT repo
2. Installed the dependencies (not as easy as I thought — see challenges below)
3. Downloaded preprocessed datasets and pretrained weights
4. Loaded the dataset using `scanpy`
5. Ran the model for cell type prediction
6. Visualized the UMAPs and confusion matrix to evaluate performance

---

## What Worked

- The pretrained model could predict cell types fairly accurately after loading the right dataset
- UMAP visualization showed clustering of cells by predicted labels
- The notebook helped me understand the structure of the model and where each part fits in

---

## Challenges I Faced

While running and testing the scGPT model from the given notebook, I faced quite a few issues, especially in terms of environment setup and actually getting the model to work properly. I didn’t build the model from scratch, but even running it had it’s own set of challenges . Here’s everything I faced:

---

### 1. Environment & Setup Issues

- The biggest problem was setting up the environment. So many libraries were outdated and not working properly with latest versions.
- `torchtext` was giving errors because it didn’t go well with the newer PyTorch. I had to find a specific old version of PyTorch that actually worked with it.
- I started with Python 3.12, but that totally broke things. The model and some packages just refused to work. Had to go back to Python 3.10 to fix it.
- Many modules like `transformers`, `anndata`, `scanpy` needed very specific versions. I had to match them manually or it would just crash.
- Few modules weren’t even pre-installed. I had to search and install `wandb`, `datasets`, and `pytorch_lightning` separately.

---

### 2. Data Handling & Preprocessing

- The data was in gene expression format — huge and super sparse. Took me some time to figure out how it's being processed.
- I didn’t write the preprocessing code, but understanding the steps like normalization (`log1p`) and filtering was not straight forward at first.
- Making sure my data format matches what the model expects was a little trial-and-error based.

---

### 3. Model Execution Challenges

- The model uses a lot of memory. My GPU kept running out of space, so I had to reduce batch size or try smaller datasets.
- Even though I wasn’t training from scratch, the execution was pretty slow, especially on CPU.
- When I tried finetuning, it got unstable sometimes — like loss wasn’t decreasing properly, or results looked random.

---

### 4. Evaluation Difficulties

- The notebook used some metrics like F1-score and confusion matrix. Took me some time to understand what they actually mean for cell types.
- It was hard to tell if the model was really wrong or just confusing between similar cell types like different T-cells.

---

### 5. Reproducibility & Maintenance

- Getting the whole thing to run required very specific setup. A small mismatch in version could break it all.
- I realised that I should’ve used a virtual env or Docker early on — that would’ve saved me so much time.
- Honestly, it made me realize how important clean documentation and proper requirements files are needed.

---

Even though I didn’t make the model, running it helped me learn a lot about handling big models, debugging environments, and figuring out how transformer-based models like scGPT are used in bio-related tasks. It wasn’t super easy but it was worth it!

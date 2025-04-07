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

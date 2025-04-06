# Cell Annotation using scGPT
This repository contains a Jupyter notebook I created to experiment with **scGPT** — a transformer-based model — for annotating cell types in single-cell RNA-seq data.

The notebook is called **`cell_annotation scgpt.ipynb`**, and in it, I try to apply the scGPT model to predict cell types from gene expression data. I’ve been curious about how transformer models can be applied to biological data, and this was a fun project to dive into that!

## What I Did in This Notebook.
### Here’s a quick breakdown of what I worked on:
  - Loaded and preprocessed a single-cell RNA-seq dataset
  - Used the scGPT model (either pretrained or fine-tuned) to make predictions on cell types
  - Visualized the results using dimensionality reduction techniques like UMAP
  - Compared the model predictions with actual labels (where available)
### This notebook is basically me exploring how scGPT performs on this kind of task — and learning as I go.
## Libraries I used
To run the notebook, you’ll need a few Python libraries:
- `torch`  
- `scanpy`  
- `anndata`  
- `scikit-learn`  
- `matplotlib`, `seaborn`  
- `scgpt` from the official [GitHub repo](https://github.com/bowang-lab/scGPT)
## What You'll See
If everything runs smoothly, you’ll see:
- Model outputs (i.e., predicted cell types)
- UMAP plots showing the cell embeddings and clusters
- Comparisons between predictions and actual cell types
## Challenges I Faced
Working with scGPT was super interesting, but not totally smooth. A few things I struggled with:
- **Module installation was tough**: Downloading and installing all the required modules took way more time than expected.
- **`torchtext` issues**: This library wasn’t compatible with my installed version of PyTorch, so I had to figure out the exact version of PyTorch it supports and install that manually.
- **Outdated dependencies**: Most of the required modules were older versions, and trying to match the correct versions without breaking anything else was a major headache.
- **Version mismatches everywhere**: I had to personally align versions of multiple libraries to get things working without conflict.
- **Python version compatibility**: The entire scGPT module doesn't work properly with Python 3.12 and above, so I had to set up a separate environment with an older Python version (e.g., 3.10) just to run the notebook.
- **GPU memory limitations**: Depending on the batch size and model config, I had to be careful not to overload the GPU.
- **Understanding the model's outputs**: While the predictions worked, it wasn’t always easy to interpret what the model was doing internally.

Despite all that, once I got it running, the rest of the process was really rewarding. It taught me a lot about managing dependencies and debugging deep learning environments.

## 📖 References

- [scGPT GitHub Repository](https://github.com/bowang-lab/scGPT)  


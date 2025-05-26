# PSL: Pairwise Subgraph Learning Framework for Technology Convergence Prediction

> **Status — Working Paper**  
> This repository accompanies the manuscript *“PSL: Pairwise Subgraph Learning Framework for Technology Convergence Prediction.”* The paper is currently under peer review; APIs, file names, and results may change before publication.

---

## About

PSL is a graph‑representation learning framework that improves early **technology‑convergence prediction** by (1) **pairwise subgraph labeling** and (2) **subgraph pooling**.  
Experimental results in the cancer‑drug patent domain show that PSL outperforms hand‑crafted similarity metrics and classical GNN baselines.

---

## Repository layout

```
.
├── Data/                       			
│   ├── test_data.pt
│   ├── train_data.pt
│   └── val_data.pt
├── GCN/                                 # Graph Convolutional Network variants		
│   ├── DRNL/                   			
│   │   ├── 00-DRNL.ipynb                # Double‑Radius Node Labeling（only subgraph labeling but no subgraph pooling）
│   │   ├── 10-DRNL+Sortpooling.ipynb    # DRNL+Sortpooling
│   │   ├── 11-DRNL+SAGPOOLING.ipynb     # DRNL+SAGPooling
│   │   └── 12-DRNL+SET2SET.ipynb        # DRNL+SET2SET
│   └── DE/                     			
│   │   ├── 00-DE.ipynb                  # Distance Encoding（only subgraph labeling but no subgraph pooling）
│   │   ├── 10-DE+Sortpooling.ipynb      # DE+Sortpooling		
│   │   ├── 11-DE+SAGPOOLING.ipynb       # DE+SAGPooling
│   │   └── 12-DE+SET2SET.ipynb          # DE+SET2SET
├── GAT/                                 # Graph Attention Network (same structure)
├── SAGE/                                # GraphSAGE (same structure)
├── Hand-craft/                          # Classical similarity‑index baselines
│   └── 05-baseline.ipynb
└── README.md                            # You are here
```

*Variant naming rule*   

- `DRNL` / `DE` = subgraph labeling only.  
- `*_pooling` = labeling **plus** subgraph‑level global pooling.

---

## Expected results (cancer‑drug patent dataset)

| Model                                                        | Accuracy  | Precision | Recall    | F1        |
| ------------------------------------------------------------ | --------- | --------- | --------- | --------- |
| Hand‑crafted (CN+JA+AA+PA+RA)                                | 0.667     | 0.764     | 0.482     | 0.591     |
| **PSL (SAGE + DE + Set2Set)**                                | **0.760** | **0.829** | **0.655** | **0.732** |
| *Complete tables are reported in Tab. 2–4 of the working paper.* |           |           |           |           |

---

## Reproducing the study

1. **Data** — The raw Cancer Moonshot patents (USPTO, 2022) are *not* included.
2. **Configuration** — Hyper‑parameters used in the paper are provided in the files.
3. **Determinism** — GNN training is inherently stochastic. Reported numbers are the mean of running results.

---

## Citing

If you use PSL or this codebase, please cite the working paper:

```bibtex
@misc{lu2025psl,
  title        = {PSL: Pairwise Subgraph Learning Framework for Technology Convergence Prediction},
  author       = {Xiaobin Lu and Jiaxin Xing and Guancan Yang and Yicong Yan},
  note         = {Working paper, 2025. Under review.},
  url          = {https://github.com/yycruc/PSL}
}
```

---

## License

This project is licensed under the **MIT License**.

## Contact

For questions, please open an issue or email **Guancan Yang** (<yanggc@ruc.edu.cn>).

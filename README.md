# Local Accuracy Is Not a Contract for Abstract Transformers: artifact

Wenrui Liang, Huijie Xu, Zhibo Jin, Zhiyu Zhu, Hongyang Chen, Biaoliang Chen, Jianlong Zhou
(University of Technology Sydney)

This repository holds the paper and its reproducibility package. Release
[v1.2](https://github.com/qichiovo/ifs2027-nier-artifact/releases/tag/v1.2), the address given in
the paper's data availability statement, carries the same two files. Releases v1.0 and v1.1 hold
earlier versions.

| File | Bytes | SHA-256 |
|---|---|---|
| `ifs2027-nier-paper-v1.2.pdf` | 534,424 | `6a231618b115a374c27616d10d68b6893d302494bf75a4fab43ff50c32148585` |
| `ifs2027-nier-artifact-v1.2.zip` | 18,903,397 | `81428b0035ec5a9562e39b18990d57037f27c4847b3541b547a6d44202e9f2b9` |

## What the package contains

The code, the trained models (219 checkpoints), the raw results, and the scripts that
regenerate every number, table and figure of the paper, together with the manuscript's LaTeX
sources. The `README.md` at the top of the ZIP describes the layout, how to rebuild the paper,
how to rerun the analysis behind Section 3, and how the records are organized.

## Rebuilding the paper

Requirements: Python 3.14 with NumPy, PyTorch (CPU) and matplotlib; a TeX distribution with
pdflatex and bibtex. After unpacking:

```
cd historical_experiment_artifact/revisions/ifs2027_nier_20261007
python -X utf8 -B scripts/generate.py
python -X utf8 -B scripts/generate_loop2.py
python -X utf8 -B scripts/generate_mechanisms.py
pdflatex main.tex && bibtex main && pdflatex main.tex && pdflatex main.tex
```

On an unpacked copy, the three generators reproduce the paper's generated tables and numbers
byte for byte, and the manuscript compiles to the same 16 pages as the PDF above. Retraining is
not needed: the saved checkpoints and records are included.

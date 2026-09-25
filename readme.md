# Domain Generalization & Adaptation Notebooks

This repository contains four Jupyter notebooks covering different
machine learning tasks related to inductive bias, domain adaptation,
domain generalization, and open-set recognition.

  -----------------------------------------------------------------------
  Course                  Assignment              Roll Number
  ----------------------- ----------------------- -----------------------
  Advanced Topics in      Programming Assignment  2025-03-0013
  Machine Learning (ATML) 1 (PA1)                 

  -----------------------------------------------------------------------

## Notebooks

1.  **Task 1 -- Inductive Bias**
2.  **Task 2 -- Domain Adaptation**
3.  **Task 3 -- Domain Generalization**
4.  **Task 4 -- Open Set Recognition**

The notebooks are designed to be run independently. After installing the
required dependencies, they can be executed from top to bottom.

## Installation

### 1. Clone the Repository

``` bash
git clone https://github.com/dahmad00/ATML-PA1-25030013.git
cd ATML-PA1-25030013
```

### 2. Install Python Dependencies

Install all required packages using:

``` bash
pip install -r requirements.txt
```

The `requirements.txt` contains the Python dependencies used by the
notebooks, including:

``` text
torch
torchvision
numpy
pandas
scikit-learn
matplotlib
Pillow
open-clip-torch
kagglehub
```

## Task 1 -- AdaIN Requirement

**Task 1 requires AdaIN (Adaptive Instance Normalization)** for neural
style transfer.

Unlike the other Python dependencies, the AdaIN implementation used by
the notebook is not installed through a pip package. Task 1 expects the
AdaIN implementation files and pretrained model weights to be available
locally.

In particular, the notebook uses:

``` python
from net import vgg, decoder
from function import adaptive_instance_normalization
```

Therefore, the repository must contain the corresponding AdaIN files:

``` text
net.py
function.py
```

### Download Pretrained AdaIN Weights

Download `decoder.pth` and `vgg_normalised.pth` from the [pytorch-AdaIN
release](https://github.com/naoto0804/pytorch-AdaIN/releases/tag/v0.0.0)
and place both files inside the `models/` directory.

The resulting structure should be:

``` text
models/
├── decoder.pth
└── vgg_normalised.pth
```

Make sure these files are present before running Task 1.

A typical repository structure for Task 1 should therefore look like:

``` text
.
├── Task1 - Indictive Bias.ipynb
├── net.py
├── function.py
├── models/
│   ├── decoder.pth
│   └── vgg_normalised.pth
└── ...
```

If the AdaIN implementation or pretrained weights are missing, Task 1
will fail when it reaches the style-transfer section.

## Running the Notebooks

Launch Jupyter Notebook:

``` bash
jupyter notebook
```

or JupyterLab:

``` bash
jupyter lab
```

Then open the required notebook and run its cells sequentially from top
to bottom.

You can also use **Run All** / **Restart & Run All** from the Jupyter
interface.

## Repository Structure

``` text
.
├── Task1 - Indictive Bias.ipynb
├── Task2 - Domain Adaptation.ipynb
├── Task3 - Domain Generalization.ipynb
├── Task4 - Open Set Recognition.ipynb
├── net.py                         # Required by Task 1 (AdaIN)
├── function.py                    # Required by Task 1 (AdaIN)
├── models/                        # Required by Task 1 (AdaIN)
│   ├── decoder.pth
│   └── vgg_normalised.pth
├── requirements.txt
└── README.md
```

## Quick Start

``` bash
git clone https://github.com/dahmad00/ATML-PA1-25030013.git
cd ATML-PA1-25030013
pip install -r requirements.txt
jupyter notebook
```

Then select the notebook you want to execute and run all cells from top
to bottom.

> **Note:** Before running Task 1, download `decoder.pth` and
> `vgg_normalised.pth` from the [pytorch-AdaIN
> release](https://github.com/naoto0804/pytorch-AdaIN/releases/tag/v0.0.0)
> and place them under `models/`.

## Notes

-   Install all dependencies from `requirements.txt` before running the
    notebooks.
-   **Task 1 additionally requires the local AdaIN implementation and
    pretrained weights described above.**
-   The notebooks may automatically download datasets or other resources
    during execution, so an internet connection may be required on the
    first run.
-   GPU acceleration is recommended for deep-learning workloads but is
    not required unless explicitly indicated by a notebook.
-   If you are using a virtual environment, make sure Jupyter uses the
    same Python environment in which `requirements.txt` was installed.

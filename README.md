# 🧠 Age-Structured Contact Network Controllability

<div align="center">

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![License](https://img.shields.io/badge/License-Educational-green.svg)
![Status](https://img.shields.io/badge/Status-Active-success.svg)
![NetworkX](https://img.shields.io/badge/NetworkX-2.5+-orange.svg)

</div>

📚 This repository contains the complete analysis code and dataset for the **ESE 5660 "Network Neuroscience"** course project at the University of Pennsylvania.

**📄 Associated Paper**: *"Linking Network Structure, Modularity, and Controllability in Age-Structured Contact Networks"*

---

## 🔍 Overview

This project investigates how network structure, community organization (modularity), and controllability interact in age-structured contact networks across different countries and social contexts. We analyze contact matrices from multiple locations to understand:

- 🕸️ **Network Structure**: Basic topological properties (clustering, path length, degree distribution)
- 🧩 **Modularity**: Community detection using Louvain algorithm with null-model comparisons
- 🎯 **Controllability**: Average/modal controllability and minimum control energy metrics

### ❓ Key Research Questions
- 🏠🏫💼 How does modularity vary across different social contexts (home, school, work)?
- 🔗 What is the relationship between network structure and controllability?
- 📊 How do age-structured contact networks differ from random network models?

---

## 🔄 Analysis Pipeline

The analysis follows a systematic pipeline:

```
┌─────────────────────┐
│  Contact Matrices   │  ← MUdata/*.xlsx (Prem et al.)
│  (Multiple Countries│     Age-structured contact data
│   & Social Contexts)│
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Network Construction│  ← Symmetrize, fix missing data
│  & Preprocessing    │     Build weighted graphs
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Structural Metrics  │  ← Clustering coefficient (C)
│    Computation      │     Path length (L)
│                     │     Global efficiency (Eglob)
│                     │     Degree & strength distributions
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Modularity Analysis │  ← Louvain community detection
│                     │     Null model generation (ER, WS, BA)
│                     │     Statistical comparison
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Controllability     │  ← Average controllability
│    Analysis         │     Modal controllability
│                     │     Minimum control energy
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Visualization &     │  ← Heatmaps, scatter plots
│  Statistical Tests  │     Correlation analysis
│                     │     Export figures to outputs/
└─────────────────────┘
```

---

## 📁 Repository Structure

```
age-structured-contact-controllability/
│
├── README.md                    # This file - project documentation
├── 5660_project.ipynb          # Main analysis notebook (Jupyter)
├── MUdata.zip                  # Compressed dataset folder
│
└── MUdata/                     # (Extracted from MUdata.zip)
    ├── MUestimates_all_locations_1.xlsx   # All contexts, Part 1
    ├── MUestimates_all_locations_2.xlsx   # All contexts, Part 2
    ├── MUestimates_home_1.xlsx            # Home contacts, Part 1
    ├── MUestimates_home_2.xlsx            # Home contacts, Part 2
    ├── MUestimates_school_1.xlsx          # School contacts, Part 1
    ├── MUestimates_school_2.xlsx          # School contacts, Part 2
    ├── MUestimates_work_1.xlsx            # Work contacts, Part 1
    ├── MUestimates_work_2.xlsx            # Work contacts, Part 2
    ├── MUestimates_other_locations_1.xlsx # Other contexts, Part 1
    └── MUestimates_other_locations_2.xlsx # Other contexts, Part 2
```

### 📝 File Descriptions

#### 💻 Core Files

- **`5660_project.ipynb`**: The main Jupyter notebook containing all analysis code organized into three projects:
  - **Project 1**: Code for 5660 project 1
  - **Project 2**: Code for 5660 project 2
  - **Project 3**: Code for 5660 project 3 Complete pipeline including:
    - Network structure analysis (clustering, path length, efficiency)
    - Modularity analysis with Louvain community detection
    - Controllability analysis (average/modal controllability, minimum control energy)
    - Visualization and statistical comparisons

- **`MUdata.zip`**: Compressed archive containing all contact matrix datasets

#### 📊 Dataset Files (in MUdata/)

All Excel files contain age-structured contact matrices from [Prem et al.](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005697) representing the average number of contacts between different age groups.

The datasets are split into two parts (1 and 2) due to the large number of countries:

- **`MUestimates_all_locations_*.xlsx`**: Contact matrices aggregated across all social contexts (home + school + work + other). Each sheet represents a different country.

- **`MUestimates_home_*.xlsx`**: Contact matrices for household/family interactions. Critical for understanding intergenerational contact patterns.

- **`MUestimates_school_*.xlsx`**: Contact matrices for educational settings. Shows strong age-assortative mixing among children and young adults.

- **`MUestimates_work_*.xlsx`**: Contact matrices for workplace interactions. Captures working-age population contact patterns.

- **`MUestimates_other_locations_*.xlsx`**: Contact matrices for other social contexts (e.g., public transport, leisure activities, community spaces).

Each Excel file contains multiple sheets, with each sheet representing a different country's contact matrix for that specific context.

---

## 📦 Dataset Description

### 🌍 Source
Contact matrices are from **Prem et al. (2017)**: ["Projecting social contact matrices in 152 countries using contact surveys and demographic data"](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005697), *PLOS Computational Biology*.

### 📋 Structure
- **Format**: Excel (.xlsx) files with multiple sheets (one per country)
- **Matrix dimensions**: 16×16 age groups (typically 5-year age bins: 0-4, 5-9, ..., 75+)
- **Values**: Expected number of daily contacts between age groups
- **Countries**: 152 countries across all continents

### 🏢 Social Contexts
1. 🌐 **All locations**: Combined contacts across all settings
2. 🏠 **Home**: Household and family contacts
3. 🏫 **School**: Educational institution contacts
4. 💼 **Work**: Workplace contacts
5. 🎪 **Other**: Community, transport, leisure, etc.

---

## 🚀 Getting Started

### ⚙️ Prerequisites

You need Python 3.7+ with the following packages:

```bash
# Core scientific computing
numpy
pandas
matplotlib
scipy

# Network analysis
networkx

# Community detection (Louvain)
python-louvain

# Excel file support
openpyxl

# Jupyter notebook
jupyter
```

### 📥 Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Junfei-Z/age-structured-contact-controllability.git
   cd age-structured-contact-controllability
   ```

2. **Install dependencies**:
   ```bash
   pip install numpy pandas matplotlib scipy networkx python-louvain openpyxl jupyter
   ```

   Or use a requirements file:
   ```bash
   pip install -r requirements.txt
   ```

3. **Extract the dataset**:
   ```bash
   unzip MUdata.zip
   ```
   This will create a `MUdata/` folder with all contact matrix files.

---

## ▶️ How to Run the Analysis

### 📋 Step-by-Step Instructions

1. **Open the Jupyter notebook**:
   ```bash
   jupyter notebook 5660_project.ipynb
   ```

2. **Run the cells sequentially**:

   - **Cell 1**: Extracts `MUdata.zip` (automatically unzips the dataset)

   - **Cells 2-3 (Project 1)**: Load and explore the contact matrices for different social contexts

   - **Cells 4-5 (Project 2)**: Preprocess data and set up network construction

   - **Cells 6+ (Project 3)**:
     - Construct weighted networks from contact matrices
     - Compute structural metrics (clustering, path length, efficiency, centrality)
     - Generate null model networks (Erdős-Rényi, Watts-Strogatz, Barabási-Albert)
     - Perform Louvain community detection
     - Calculate controllability metrics
     - Generate visualizations and export figures

3. **Outputs**:

   All figures and results are saved to the `outputs/` folder (created automatically), including:
   - Network structure heatmaps
   - Modularity comparison plots
   - Controllability metric distributions
   - Correlation analyses between structure and controllability

### ⚡ Quick Run (All at Once)

If you prefer to run everything without interaction:

```bash
jupyter nbconvert --to notebook --execute 5660_project.ipynb --output 5660_project_executed.ipynb
```

This will execute all cells and save the results to a new notebook.

---

## 🔬 Reproducing Paper Results

To reproduce the figures and results from the paper:

1. **Ensure dataset is extracted**: Run Cell 1 or manually `unzip MUdata.zip`

2. **Run Project 3 cells**: These contain the complete analysis pipeline:
   - Network structure analysis
   - Modularity computation with null models
   - Controllability metrics
   - Statistical comparisons

3. **Check outputs folder**: All figures will be saved in `outputs/` with descriptive filenames

4. **Key analyses**:
   - **Figure 1 (Network Structure)**: Generated from structural metrics cells
   - **Figure 2 (Modularity)**: From Louvain analysis and null model comparison
   - **Figure 3 (Controllability)**: From controllability metrics computation
   - **Figure 4 (Correlations)**: From combined structure-controllability analysis

---

## 🔬 Analysis Details

### 🕸️ Network Construction

Contact matrices are converted to weighted graphs where:
- **Nodes**: Age groups (16 nodes per network)
- **Edges**: Weighted by contact frequency
- **Preprocessing**: Symmetrization (since contacts are bidirectional) and handling missing data

### 📊 Structural Metrics

- **Clustering Coefficient (C)**: Measures local connectivity and transitivity
- **Average Path Length (L)**: Average shortest path between all node pairs
- **Global Efficiency (Eglob)**: Inverse of average path length, robust to disconnections
- **Degree & Strength**: Node connectivity and weighted connectivity distributions
- **Centrality**: Betweenness and eigenvector centrality

### 🧩 Modularity Analysis

- **Algorithm**: Louvain community detection (hierarchical, optimization-based)
- **Null Models**:
  - **Erdős-Rényi (ER)**: Random graphs with same edge probability
  - **Watts-Strogatz (WS)**: Small-world networks preserving degree
  - **Barabási-Albert (BA)**: Scale-free networks with preferential attachment
- **Comparison**: Statistical tests (z-scores, p-values) against null distributions

### 🎯 Controllability Metrics

Based on linear network control theory:

- **Average Controllability**: Ability to move the network to easy-to-reach states
- **Modal Controllability**: Ability to move the network to difficult-to-reach states
- **Minimum Control Energy**: Energy required to drive the network between states

These metrics are computed from the network adjacency matrix using eigenvalue decomposition.

---

## 💡 Key Findings

The analysis reveals:

1. 🏫🏠 **Context-dependent modularity**: School and home networks show higher modularity than work networks, reflecting age-assortative mixing patterns

2. 🔗 **Structure-controllability relationship**: Networks with higher clustering tend to have different controllability profiles

3. 📉 **Deviation from null models**: Real contact networks show distinct structural properties compared to random network models

4. 🌍 **Cross-country patterns**: Despite geographical differences, similar contexts show consistent structural and controllability properties

---

## 📋 Requirements

### 🐍 Python Packages

```
numpy>=1.19.0
pandas>=1.2.0
matplotlib>=3.3.0
scipy>=1.6.0
networkx>=2.5
python-louvain>=0.15
openpyxl>=3.0.0
jupyter>=1.0.0
```

### 💻 System Requirements

- **RAM**: 4GB+ recommended (for processing multiple large networks)
- **Storage**: ~500MB for dataset and outputs
- **Python**: 3.7 or higher

---

## 📚 Citation

If you use this code or dataset in your research, please cite:

```bibtex
@article{yourname2025controllability,
  title={Linking Network Structure, Modularity, and Controllability in Age-Structured Contact Networks},
  author={Your Name},
  journal={ESE 5660 Network Neuroscience Course Project},
  year={2025},
  institution={University of Pennsylvania}
}
```

### 📊 Dataset Citation

Please also cite the original contact matrix data:

```bibtex
@article{prem2017projecting,
  title={Projecting social contact matrices in 152 countries using contact surveys and demographic data},
  author={Prem, Kiesha and Cook, Alex R and Jit, Mark},
  journal={PLOS Computational Biology},
  volume={13},
  number={9},
  pages={e1005697},
  year={2017},
  publisher={Public Library of Science}
}
```

---

## 📖 Glossary (For Students New to Network Science)

### 🕸️ Basic Network Concepts

- **Network/Graph**: A collection of nodes (vertices) connected by edges (links)
- **Weighted Network**: Edges have numerical values representing connection strength
- **Degree**: Number of connections a node has
- **Clustering**: Tendency of nodes to form tightly connected groups

### 🧩 Modularity

- **Community**: A group of nodes more densely connected to each other than to the rest of the network
- **Modularity**: A metric (0 to 1) measuring how well a network divides into communities
- **Louvain Algorithm**: A fast method to detect communities by optimizing modularity

### 🎯 Controllability

- **Network Control Theory**: Mathematical framework for understanding how to drive a network from one state to another
- **Average Controllability**: How easily a network can be moved to nearby states
- **Modal Controllability**: How easily a network can be moved to distant, hard-to-reach states
- **Control Energy**: The "effort" required to change the network's state

### 🎲 Null Models

- **Null Model**: A random network used for comparison to determine if observed patterns are statistically significant
- **Erdős-Rényi (ER)**: Simplest random network where each possible edge exists with equal probability
- **Watts-Strogatz (WS)**: Random network with high clustering and short paths (small-world)
- **Barabási-Albert (BA)**: Random network where popular nodes get more connections (scale-free)

---

## 🔧 Troubleshooting

### ⚠️ Common Issues

1. **"No module named 'community'"**
   ```bash
   pip install python-louvain
   ```

2. **"openpyxl is required to read Excel files"**
   ```bash
   pip install openpyxl
   ```

3. **"MUdata folder not found"**
   - Make sure to run the first cell to unzip `MUdata.zip`
   - Or manually: `unzip MUdata.zip`

4. **Memory errors with large networks**
   - Process countries one at a time instead of all at once
   - Reduce the number of null model iterations

5. **Figures not saving**
   - The notebook creates an `outputs/` folder automatically
   - Check write permissions in your directory

---

## 🤝 Contributing

This is a course project repository. If you find issues or have suggestions:
1. Open an issue describing the problem
2. For code improvements, feel free to fork and submit pull requests

---

## 📜 License

This project is for educational purposes as part of ESE 5660 at the University of Pennsylvania.

The contact matrix data is from Prem et al. (2017) and subject to their original licensing terms.

---

## 📬 Contact

For questions about this project:
- **Course**: ESE 5660 - Network Neuroscience
- **Institution**: University of Pennsylvania
- **Repository**: https://github.com/Junfei-Z/age-structured-contact-controllability

---

## 🙏 Acknowledgments

- **Data source**: Prem et al. (2017) for providing comprehensive contact matrices
- **Course instruction**: ESE 5660 teaching staff
- **Tools**: NetworkX, python-louvain community detection, and the Python scientific computing ecosystem

# Spatial Topic Modeling for IMC Data Analysis

A comprehensive workflow for applying Latent Dirichlet Allocation (LDA) topic modeling to Imaging Mass Cytometry (IMC) data to discover spatial cellular organization patterns.

##  Overview

This repository demonstrates how to use **coherence analysis** to determine the optimal number of topics for spatial LDA, solving the critical problem of arbitrary topic selection in scimap's `spatial_lda` function.

### Key Innovation

Instead of guessing how many spatial motifs to discover, this workflow:
- Tests multiple topic numbers using coherence metrics
- Selects the optimal number based on data properties
- Ensures reproducible, interpretable, and biologically meaningful results

## Features

- **Data-driven topic selection** via coherence analysis
- **Spatial motif discovery** using LDA topic modeling
- **Integration with scimap** for spatial analysis
- **Comprehensive visualizations** of discovered patterns
- **Sample data generation** for testing the workflow
- **Plug-and-play** structure with clear documentation

##  Quick Start

### Prerequisites

```bash
pip install scimap anndata scanpy pandas numpy matplotlib seaborn scikit-learn gensim pyLDAvis
```

### Usage

1. Open `spatial_lda_topic_modeling.ipynb` in Jupyter
2. Run cells sequentially
3. For testing: Use the built-in sample data generation
4. For your data: Update file paths and column names in Section 2

##  Workflow

1. **Load Data**: Expression matrix + metadata with spatial coordinates
2. **Extract Neighborhoods**: Identify spatial neighborhoods around each cell
3. **Coherence Analysis**: Determine optimal number of topics
4. **Topic Modeling**: Apply LDA with optimal topics
5. **Spatial LDA**: Use scimap with data-driven topic number
6. **Visualization**: Explore discovered spatial patterns

## Files

- `spatial_lda_topic_modeling.ipynb`: Main analysis notebook
- `README.md`: This file

##  Customization

### Required Column Names
Update these in the notebook to match your metadata:
- `Location_Center_X`: X coordinates
- `Location_Center_Y`: Y coordinates  
- `major_celltype`: Cell type labels
- `ImageNumber`: Image identifiers

### Adjustable Parameters
- `radius`: Neighborhood size in pixels (default: 30)
- `start`, `limit`, `step`: Topic number range for coherence analysis
- `n_clusters`: Number of spatial clusters (default: 6)

##  References

- **Scimap**: https://scimap.readthedocs.io/
- **LDA Topic Modeling**: Blei et al. (2003) JMLR
- **Coherence Metrics**: Röder et al. (2015) EMNLP

##  Citation

If you use this workflow, please cite:
- The scimap package
- This repository (if helpful)

##  Contributing

Contributions welcome! Please feel free to submit issues or pull requests.

##  License

This notebook is provided as-is for educational and research purposes.

---

**Note**: This workflow solves a common problem in spatial LDA analysis by providing a data-driven method for topic selection, making results more reproducible and interpretable.

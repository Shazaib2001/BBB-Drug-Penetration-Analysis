# Assessing the Penetrability of Therapeutic Agents Across the Blood-Brain Barrier

## Project Overview

This project applies machine learning techniques to predict the ability of therapeutic compounds to cross the blood-brain barrier (BBB). Using molecular descriptors derived from SMILES strings, we explore the relationship between chemical structure and BBB permeability. The aim is to support early-stage drug development for central nervous system (CNS) disorders by identifying potential candidates with high BBB penetrability.

## Data Source and Description

The dataset includes small molecules with known BBB permeability classifications (BBB+ or BBB-). Molecular descriptors were generated using RDKit from SMILES strings. These features numerically describe the chemical properties of each compound and serve as input for machine learning models.

Key columns:
- **SMILES**: Encodes molecular structure  
- **Class**: Binary label indicating BBB permeability  

Over 200 descriptors were computed, including topological, electronic, and surface area properties.

## Analysis Techniques

- **Feature Generation**: RDKit was used to compute molecular descriptors from SMILES.  
- **Exploratory Data Analysis (EDA)**: Included histograms, box plots, and a correlation heatmap to examine descriptor distributions and relationships.  
- **Machine Learning Models**:  
  - **Random Forest**  
  - **Logistic Regression**  
  - **Support Vector Machine (SVM)**  
  Models were evaluated using accuracy, precision, recall, F1-score, ROC curves, and confusion matrices.

## Results

- **Random Forest** achieved the highest accuracy at ~84.3%, with strong recall for BBB+ compounds.  
- **Logistic Regression** performed well overall (~80.9% accuracy) but showed slightly more class imbalance.  
- **SVM** showed decent performance, with a confusion matrix indicating good predictive balance.  
- **AUC issues** noted in ROC analysis (AUC = 0.13) suggest problems with class imbalance or evaluation setup.

## Installation

Install the required Python libraries using:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn rdkit bootstrapped
```

## Usage

Run the Jupyter notebook provided in the repository to reproduce the analysis. Ensure your dataset includes SMILES strings and a BBB permeability label.

## Contributing

Contributions are welcome. Please fork the repository and submit pull requests with your suggested improvements.

## License

This project is licensed under the MIT License.

## Contact

For queries, please contact **Shazaib Rehman**.  
Connect with me on [LinkedIn](https://www.linkedin.com).

# Quick Start Guide
## Diabetes Genomics Project - Pakistani Population

### 🚀 Getting Started

#### 1. Clone or Download the Project
```bash
git clone https://github.com/YOUR-USERNAME/diabetes-genomics-pakistan.git
cd diabetes-genomics-pakistan
```

#### 2. Set Up Python Environment
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

#### 3. Run Example Scripts

**Test Data Processing:**
```bash
python scripts/data_processing.py
```

**Create Visualizations:**
```bash
python scripts/visualization_tools.py
```

**Calculate Risk Scores:**
```bash
python scripts/risk_calculator.py
```

### 📊 Using the Tools

#### Calculate Genetic Risk for a Patient

```python
from scripts.risk_calculator import GeneticRiskCalculator

# Initialize calculator
calculator = GeneticRiskCalculator()

# Define patient genotypes
# 0 = no risk alleles, 1 = one risk allele, 2 = two risk alleles
genotypes = {
    'rs7903146': 1,  # TCF7L2
    'rs5219': 2,     # KCNJ11
    'rs9939609': 1,  # FTO
}

# Calculate risk
weighted_score = calculator.calculate_weighted_risk_score(genotypes)
risk_assessment = calculator.estimate_absolute_risk(weighted_score)

print(f"Absolute Risk: {risk_assessment['risk_percentage']:.1f}%")
print(f"Category: {risk_assessment['category']}")
```

#### Create Visualizations

```python
from scripts.visualization_tools import DiabetesGenomicsVisualizer

visualizer = DiabetesGenomicsVisualizer()

# Compare allele frequencies
variants = ['TCF7L2\nrs7903146', 'PPARG\nrs1801282', 'KCNJ11\nrs5219']
south_asian = [0.35, 0.12, 0.45]
european = [0.26, 0.11, 0.38]

visualizer.plot_allele_frequency_comparison(
    variants, 
    south_asian, 
    european,
    save_path='results/frequency_comparison.png'
)
```

#### Process Variant Data

```python
from scripts.data_processing import GenomicDataProcessor
import pandas as pd

processor = GenomicDataProcessor()

# Load data
df = pd.read_csv('data/sample_data.csv')

# Filter by population
south_asian_variants = processor.filter_by_population(df, 'South Asian')

# Prioritize significant variants
prioritized = processor.prioritize_variants(
    south_asian_variants,
    min_pvalue=5e-8,
    min_effect_size=1.1
)

# Export results
processor.export_processed_data(prioritized, 'results/prioritized_variants.csv')
```

### 📁 Project Structure

```
diabetes-genomics-pakistan/
├── README.md                      # Main documentation
├── requirements.txt               # Python dependencies
├── QUICK_START.md                # This file
│
├── data/
│   └── sample_data.csv           # Example variant data
│
├── scripts/
│   ├── data_processing.py        # Data manipulation tools
│   ├── visualization_tools.py    # Plotting functions
│   └── risk_calculator.py        # Risk score calculations
│
└── results/                      # Output directory
    ├── figures/
    └── reports/
```

### 🎯 Common Tasks

#### Task 1: Analyze Your Own Variant Data

1. Prepare CSV file with columns:
   - rsID, gene, chromosome, position
   - risk_allele, odds_ratio, p_value
   - population-specific allele frequencies

2. Load and process:
```python
df = pd.read_csv('your_data.csv')
processor = GenomicDataProcessor()
results = processor.prioritize_variants(df)
```

#### Task 2: Calculate Risk for Multiple Patients

```python
patients = [
    {'id': 'P001', 'genotypes': {'rs7903146': 1, 'rs5219': 2}},
    {'id': 'P002', 'genotypes': {'rs7903146': 0, 'rs5219': 1}},
]

calculator = GeneticRiskCalculator()

for patient in patients:
    score = calculator.calculate_weighted_risk_score(patient['genotypes'])
    risk = calculator.estimate_absolute_risk(score)
    print(f"{patient['id']}: {risk['risk_percentage']:.1f}% - {risk['category']}")
```

#### Task 3: Create Publication Figures

```python
visualizer = DiabetesGenomicsVisualizer()

# Create all standard figures
visualizer.plot_allele_frequency_comparison(...)
visualizer.plot_effect_size_forest(...)
visualizer.plot_risk_score_distribution(...)
visualizer.plot_diabetes_statistics_pakistan()
```

### 📚 Learning Resources

**Understanding the Code:**
- `data_processing.py` - Start here to understand data structures
- `risk_calculator.py` - Learn about genetic risk scores
- `visualization_tools.py` - See how to create figures

**Key Concepts:**
- **SNP (Single Nucleotide Polymorphism)**: Single base pair variation
- **Odds Ratio**: Measure of association between variant and disease
- **Allele Frequency**: How common an allele is in a population
- **Polygenic Risk Score**: Combined effect of multiple variants
- **GWAS**: Genome-Wide Association Study

### 🔬 Next Steps

1. **Collect Real Data**: 
   - Access public databases (1000 Genomes, gnomAD)
   - Search GWAS Catalog for T2D studies
   - Focus on South Asian populations

2. **Expand Analysis**:
   - Add more variants
   - Include gene-environment interactions
   - Develop machine learning models

3. **Validation**:
   - Compare with published studies
   - Test on independent datasets
   - Collaborate with clinicians

4. **Share Your Work**:
   - Present at conferences
   - Publish on GitHub
   - Write blog posts explaining findings

### 🤝 Contributing

This is an educational project. Suggestions and improvements welcome!

**Ideas for contributions:**
- Add more variants to database
- Improve risk calculation algorithms
- Create interactive web interface
- Add literature mining tools
- Develop educational materials

### 📧 Contact

**Author**: Rimsha Kanwal  
**Email**: rimshakanwal391@gmail.com  
**Institution**: The University of Lahore, Pakistan

### ⚠️ Important Disclaimer

This project is for educational and research purposes only. 

**DO NOT USE FOR CLINICAL DECISIONS**

Genetic risk scores should be:
- Validated in large clinical studies
- Interpreted by qualified healthcare providers
- Combined with clinical factors (BMI, diet, family history)
- Used as part of comprehensive risk assessment

High genetic risk does NOT mean disease is inevitable. Lifestyle modifications can significantly reduce diabetes risk regardless of genetic predisposition.

### 📝 Citation

If you use this work, please cite:

```
Kanwal, R. (2026). Genomic Analysis of Type 2 Diabetes Susceptibility 
in Pakistani Population: An Introductory Bioinformatics Study. 
GitHub repository: https://github.com/YOUR-USERNAME/diabetes-genomics-pakistan
```

---

**"Understanding the genetic code of disease is the first step toward writing a healthier future for my people."**

*- Rimsha Kanwal*

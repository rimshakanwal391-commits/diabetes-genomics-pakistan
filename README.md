# Genomic Analysis of Type 2 Diabetes Susceptibility in Pakistani Population
## An Introductory Bioinformatics Study

### Author: Rimsha Kanwal
### Institution: The University of Lahore, Pakistan
### Contact: rimshakanwal391@gmail.com

---

## Project Overview

This project represents an undergraduate-level investigation into the genetic variants associated with Type 2 Diabetes (T2D) susceptibility in the Pakistani population. With Pakistan facing one of the world's highest diabetes prevalence rates (~30% of adults), understanding population-specific genetic risk factors is critical for developing targeted prevention and intervention strategies.

## Research Motivation

Pakistan is experiencing a diabetes epidemic:
- **Current Prevalence**: ~30% of adult population
- **Global Ranking**: 3rd highest number of diabetics worldwide
- **Projected Growth**: Expected to reach 37 million cases by 2045
- **Research Gap**: Pakistani populations remain understudied in genomic research

This project aims to bridge the gap between global diabetes genomics research and the urgent needs of the Pakistani population.

## Project Objectives

1. **Literature Analysis**: Comprehensive review of genetic variants associated with T2D in South Asian populations
2. **Variant Prioritization**: Identify key SNPs (Single Nucleotide Polymorphisms) relevant to Pakistani genomes
3. **Data Visualization**: Create informative visualizations of genetic risk factors
4. **Frequency Analysis**: Compare allele frequencies between populations
5. **Risk Score Development**: Propose a basic genetic risk scoring system
6. **Educational Resource**: Develop accessible materials explaining diabetes genetics

## 🧬 Key Genes Under Investigation

### Primary Candidate Genes:
1. **TCF7L2** (Transcription Factor 7 Like 2)
   - Most strongly associated with T2D risk globally
   - rs7903146 variant increases risk by 37% per allele
   
2. **PPARG** (Peroxisome Proliferator-Activated Receptor Gamma)
   - Involved in adipocyte differentiation and insulin sensitivity
   - Pro12Ala variant shows protective effects
   
3. **KCNJ11** (Potassium Inwardly Rectifying Channel Subfamily J Member 11)
   - Regulates insulin secretion
   - E23K variant associated with T2D risk
   
4. **FTO** (Fat Mass and Obesity Associated)
   - Links obesity and diabetes risk
   - Shows population-specific effects
   
5. **IGF2BP2** (Insulin-Like Growth Factor 2 mRNA Binding Protein 2)
   - Associated with impaired insulin secretion

### South Asian-Specific Variants:
- **SLC16A11**: Strong association in South Asian populations
- **GRB14**: Glucose and insulin metabolism
- **HMG20A**: Implicated in South Asian T2D studies

##  Project Structure

```
diabetes-genomics-pakistan/
│
├── README.md
├── LICENSE
│
├── data/
│   ├── literature_review/
│   │   ├── gwas_studies_south_asian.csv
│   │   ├── pakistani_population_studies.csv
│   │   └── variant_databases.md
│   │
│   ├── allele_frequencies/
│   │   ├── 1000_genomes_south_asian.csv
│   │   ├── gnomad_south_asian.csv
│   │   └── comparison_european_vs_south_asian.csv
│   │
│   └── public_datasets/
│       └── dataset_sources.md
│
├── analysis/
│   ├── 01_literature_analysis.ipynb
│   ├── 02_variant_prioritization.ipynb
│   ├── 03_allele_frequency_comparison.ipynb
│   ├── 04_risk_score_development.ipynb
│   └── 05_visualization_and_interpretation.ipynb
│
├── scripts/
│   ├── data_processing.py
│   ├── visualization_tools.py
│   ├── risk_calculator.py
│   └── population_comparison.py
│
├── results/
│   ├── figures/
│   ├── tables/
│   └── summary_report.md
│
├── docs/
│   ├── methodology.md
│   ├── genetic_background.md
│   ├── population_context.md
│   └── references.bib
│
└── resources/
    ├── educational_materials/
    └── presentation_slides/
```

##  Technical Approach

### 1. Data Collection
- **Literature Mining**: PubMed, Google Scholar for South Asian diabetes GWAS
- **Public Databases**: 
  - 1000 Genomes Project (South Asian populations)
  - gnomAD (Genome Aggregation Database)
  - GWAS Catalog
  - ClinVar
  - dbSNP

### 2. Bioinformatics Tools
- **Python Libraries**:
  - `pandas` - Data manipulation
  - `numpy` - Numerical computations
  - `matplotlib`, `seaborn` - Data visualization
  - `biopython` - Sequence analysis
  - `scikit-learn` - Basic machine learning
  
- **R Packages**:
  - `ggplot2` - Advanced visualization
  - `dplyr` - Data wrangling
  - `genetics` - Genetic data analysis

### 3. Analysis Pipeline

```python
# Simplified workflow

# Step 1: Load variant data
variants = load_gwas_catalog()
south_asian_variants = filter_by_population(variants, "South Asian")

# Step 2: Prioritize variants
high_priority = prioritize_by_effect_size(south_asian_variants)
pakistani_relevant = filter_by_dietary_interaction(high_priority)

# Step 3: Compare allele frequencies
freq_comparison = compare_allele_frequencies(
    populations=["South Asian", "European", "East Asian"]
)

# Step 4: Calculate genetic risk score
def calculate_genetic_risk(genotype_data):
    risk_score = 0
    for variant in prioritized_variants:
        risk_score += variant.effect_size * genotype_data[variant.id]
    return risk_score

# Step 5: Visualize results
plot_risk_distribution()
plot_population_comparison()
plot_gene_interaction_network()
```

##  Expected Outcomes

1. **Comprehensive Variant Database**
   - Curated list of 50+ T2D-associated variants
   - Population-specific allele frequencies
   - Effect sizes and odds ratios

2. **Visual Analytics**
   - Manhattan plots of GWAS significance
   - Allele frequency comparison charts
   - Gene pathway interaction networks
   - Risk distribution visualizations

3. **Genetic Risk Score Model**
   - Basic polygenic risk score framework
   - Population-stratified risk categories
   - Integration with environmental factors

4. **Educational Resources**
   - Infographics explaining diabetes genetics
   - Simplified explanations for Pakistani healthcare providers
   - Policy recommendations document

## 🔍 Key Research Questions

1. **Variant Prevalence**: Which T2D-associated variants show higher frequencies in Pakistani/South Asian populations?
2. **Effect Size Differences**: Do known variants show different effect sizes in Pakistani populations?
3. **Gene-Environment Interaction**: How do genetic variants interact with traditional Pakistani diet (high refined carbs, ghee, etc.)?
4. **Novel Variants**: Are there population-specific variants not captured in European GWAS?
5. **Predictive Power**: Can we develop a genetic risk score optimized for Pakistani populations?

## 🌍 Population Context

### Pakistani Population Characteristics:
- **Genetic Diversity**: Mix of Middle Eastern, Central Asian, and South Asian ancestry
- **Dietary Patterns**: High refined carbohydrates, traditional cooking with ghee
- **Lifestyle Factors**: Increasing sedentary behavior, urbanization effects
- **Consanguinity**: High rates of cousin marriages affecting genetic disease patterns
- **Healthcare Access**: Limited genetic screening and personalized medicine

### Why This Matters:
Most diabetes genetic research uses European cohorts. However:
- Genetic variants may have different frequencies across populations
- Effect sizes can vary due to gene-environment interactions
- Linkage disequilibrium patterns differ between populations
- Risk prediction models need population-specific calibration

## 📚 Methodology

### Phase 1: Literature Review & Data Collection
**Duration**: 2-3 weeks
- Systematic search of diabetes genomics literature
- Focus on South Asian and Pakistani studies
- Extract variant information (rsID, chromosome, position, effect size)
- Compile allele frequency data from public databases

### Phase 2: Data Analysis
**Duration**: 3-4 weeks
- Quality control of collected data
- Statistical analysis of allele frequencies
- Comparison across populations
- Identification of high-priority variants
- Pathway and network analysis

### Phase 3: Risk Score Development
**Duration**: 2 weeks
- Design polygenic risk score algorithm
- Weight variants by effect size
- Test on simulated genotype data
- Validate against published models

### Phase 4: Visualization & Reporting
**Duration**: 2 weeks
- Create comprehensive visualizations
- Write detailed methodology
- Prepare summary report
- Develop educational materials

## 🎓 Educational Value

This project serves as:
- **Learning Tool**: Hands-on bioinformatics for undergraduates
- **Research Foundation**: Basis for future wet-lab validation studies
- **Public Health Resource**: Information for healthcare providers
- **Advocacy Tool**: Evidence for funding Pakistani genomic research

## 🚀 Future Directions

### Short-term (6-12 months):
1. Collaborate with Pakistani hospitals for sample collection
2. Conduct small-scale genotyping study
3. Validate in silico findings with real patient data
4. Present at national bioinformatics conferences

### Long-term (2-5 years):
1. Large-scale GWAS in Pakistani T2D patients
2. Integration with electronic health records
3. Development of clinical genetic testing panel
4. Implementation of genetic risk screening programs

## 🤝 Collaboration Opportunities

Seeking collaboration with:
- Pakistani hospitals and diabetes clinics
- Genomics research centers
- Bioinformatics researchers
- Public health organizations
- Genetic counselors
- Data scientists and AI/ML experts

## References

### Key Papers:
1. Diabetes genetics in South Asian populations (Review papers)
2. TCF7L2 variants in Pakistani population studies
3. 1000 Genomes Project South Asian data
4. GWAS Catalog diabetes entries
5. Polygenic risk score methodologies

### Databases:
- **1000 Genomes Project**: http://www.internationalgenome.org/
- **gnomAD**: https://gnomad.broadinstitute.org/
- **GWAS Catalog**: https://www.ebi.ac.uk/gwas/
- **ClinVar**: https://www.ncbi.nlm.nih.gov/clinvar/
- **T2D Knowledge Portal**: http://www.type2diabetesgenetics.org/

## 💡 Impact Statement

This project represents more than academic exercise—it's a step toward health equity. By focusing computational power on an understudied population bearing a disproportionate disease burden, we demonstrate that bioinformatics can be a tool for social justice. Every analysis brings us closer to understanding why diabetes affects Pakistanis so severely, and every insight could inform interventions that save lives in my community.

## 📄 License

This project is licensed under MIT License - see LICENSE file for details.

## 🙏 Acknowledgments

- The University of Lahore, Bioinformatics Department
- Center for Applied Molecular Biology (CAMB), Punjab University
- Global genomics databases making data publicly accessible
- The Pakistani families affected by diabetes who inspire this work

---

**Note**: This is an educational and research project. Genetic risk scores developed here should not be used for clinical decision-making without proper validation and consultation with healthcare providers.

**Citation**: If you use this work, please cite:
```
Kanwal, R. (2026). Genomic Analysis of Type 2 Diabetes Susceptibility in Pakistani Population: 
An Introductory Bioinformatics Study. GitHub repository: [URL]
```

---

*"Understanding the genetic code of disease is the first step toward writing a healthier future for my people."* - Rimsha Kanwal

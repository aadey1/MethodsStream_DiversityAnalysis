**Stream Macroinvertebrate Diversity Analysis**

This code and lesson accompanies the **Methods in Stream Ecology Textbook** chapter on benthic invertebrates. It provides a comprehensive workflow for calculating and interpreting alpha (α), beta (β), and gamma (γ) diversity metrics for stream macroinvertebrate communities.

📊 **What This Analysis Does**
This repository calculates three types of diversity metrics:

1. **Alpha Diversity (α)**: Within-site diversity
     Species richness (Hill q=0)
     Shannon diversity (Hill q=1)
     Simpson diversity (Hill q=2)

2. **Beta Diversity (β)**: Between-site diversity using three methods:
     Hill numbers approach (β = γ/α)
     Jaccard dissimilarity (presence/absence)
     Bray-Curtis dissimilarity (abundance-based)

3. **Gamma Diversity (γ)**: Total regional diversity across all sites


📁 **Repository Structure**

MethodsStream_DiversityAnalysis/
├── README.md                          # This file
├── Code/
│   └── DiversityAnalyses.Rmd          # Main R Markdown analysis script
├── Data/
│   ├── Raw/                           # Input data files
│   │   ├── masterTaxaGenus.csv        # Taxonomic reference data
│   │   ├── stationBenthicsTESTSITE.csv      # Benthic sample data
│   │   └── stationInfoBenSampsTESTSITE.csv  # Station metadata
│   └── ProcessedOutput/               # Analysis results
│       ├── alpha_diversity_results.csv      # Site-level diversity
│       ├── diversity_summary_by_year.csv    # Annual summary
│       ├── jaccard_by_year.csv              # Jaccard results
│       └── braycurtis_by_year.csv           # Bray-Curtis results
└── InstructionDocuments/
    ├── Instructions-DiversityAnalysis.docx           # Step-by-step guide
    ├── QuickReferenceGuide.docx                      # Quick reference
    └── DiversityAnalysisResultsInterpretation.docx  # How to interpret results

🚀 **Quick Start**
Prerequisites:
Install required R packaces
  install.packages(c("vegan", "iNEXT", "betapart", "dplyr", "tidyr"))

Running the Analysis:
  1. Clone or download this repository
  2. Open Code/DiversityAnalyses.Rmd in RStudio
  3. Update file paths in the code to point to your data location:
    master_taxa <- read.csv("Data/Raw/masterTaxaGenus.csv")
    benthics <- read.csv("Data/Raw/stationBenthicsTESTSITE.csv")
    station_info <- read.csv("Data/Raw/stationInfoBenSampsTESTSITE.csv")
  5. Run all chunks (or knit document)

Expected Run Time
  Small datasets (< 50 sites): ~1-2 minutes
  Medium datasets (50-200 sites): ~2-5 minutes
  Large datasets (> 200 sites): ~5-10 minutes

📖 **Documentation**
This repository includes three comprehensive instruction documents:
  1. **Instructions-DiversityAnalysis.docx**
     Detailed explanation of what each diversity metric measures
     Step-by-step walkthrough of the R code
     Understanding the three beta diversity methods
     How to customize the analysis for your needs
     
  3. **QuickReferenceGuide.docx**
       For quick lookups, this includes:
           Copy-paste ready code snippets
           Visual examples of diversity calculations
           Formula references
           Troubleshooting checklist
           Common error solutions
     
  4. **DiversityAnalysisResultsInterpretation.docx**
      Learn how to interpret your results:
           What do the numbers mean?
           Example interpretations with real data
           How to report results in publications
           Statistical testing suggestions
           Visualization examples

🔬 **Methods Background**
    **The Dataset**
      This analysis uses the same benthic macroinvertebrate dataset as the IBI (Index of Biotic Integrity) assessment module. The data includes:

        141 unique sampling sites
        182 taxa (primarily family-level identifications)
        23 years of monitoring data (1994-2022)
        Multiple habitat types and seasons

  **Diversity Metrics**
    Why use Hill numbers? Hill numbers (q = 0, 1, 2) provide a unified framework for measuring diversity:

      All metrics are in units of "effective number of species"
      Different q values emphasize different aspects of diversity
      Mathematically related through β = γ/α

  **Why multiple beta diversity methods?**
    Hill numbers (β = γ/α): Intuitive interpretation ("how many times composition changes")
      Jaccard: Classic metric, good for presence/absence
      Bray-Curtis: Accounts for abundance, sensitive to dominant taxa
    
    Each method answers slightly different questions, providing complementary insights into community structure.

🎯 **Learning Objectives**
  After completing this module, you will be able to:

  1. ✅ Calculate alpha, beta, and gamma diversity for stream communities
  2. ✅ Understand the differences between Hill numbers (q=0, 1, 2)
  3. ✅ Compare and interpret multiple beta diversity metrics
  4. ✅ Identify which taxa drive community differences
  5. ✅ Assess temporal patterns in diversity
  6. ✅ Report diversity results in publications

🐛 **Troubleshooting**
  Common Issues
    Error: "argument is of length zero"
      Cause: Years with only one site cannot calculate beta diversity
      Solution: Analysis automatically skips these years and reports them

    Error: Date parsing fails
      Cause: Date format doesn't match expected format
      Solution: Check your date format and adjust the as.POSIXct() format string

    Warning: "Unknown or uninitialised column"
      Cause: Columns not pre-initialized
      Solution: Already fixed in the current version of code

    Results show NA for Jaccard/Bray-Curtis
      Cause: Years with < 2 sites (need pairwise comparisons)
      Check: Look at console output - it reports which years are skipped

    See QuickReferenceGuide.docx for more detailed troubleshooting.

📚 **Citation**
  If you use this code in your research, please cite:
       Methods in Stream Ecology Textbook: [INSERT BOOK CITATION}
       
       For Hill numbers methodology:
            Chao, A., Chiu, C.H., and Jost, L. 2014. Unifying species diversity, phylogenetic diversity, functional diversity, and related similarity and differentiation measures through Hill numbers. Annual Review of Ecology, Evolution, and Systematics 45:297-324.
       For beta diversity interpretation:
            Jost, L. 2007. Partitioning diversity into independent alpha and beta components. Ecology 88(10):2427-2439.

🤝 **Contributing**
  This is an educational resource. If you find errors or have suggestions for improvement, please:
    1. Open an issue describing the problem or suggestion
    2. For code fixes, submit a pull request
    3. For documentation improvements, submit suggested edits

📧 **Contact**
  For questions about this module:
    **Content questions**: Refer to the Methods in Stream Ecology textbook
    **Technical issues**: Check the troubleshooting section in QuickReferenceGuide.docx
    **Bug reports**: Open an issue in this repository

📜 **License**
  This educational material is provided for use with the Methods in Stream Ecology textbook. Please use responsibly and cite appropriately.

**Happy analyzing!** 🐛📊🌊






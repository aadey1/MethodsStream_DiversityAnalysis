Stream Macroinvertebrate Diversity Analysis
This code and lesson accompanies the Methods in Stream Ecology Textbook chapter on benthic invertebrates. It provides a comprehensive workflow for calculating and interpreting alpha (α), beta (β), and gamma (γ) diversity metrics for stream macroinvertebrate communities.
📊 What This Analysis Does
This repository calculates three types of diversity metrics:
1. Alpha Diversity (α): Within-site diversity

Species richness (Hill q=0)
Shannon diversity (Hill q=1)
Simpson diversity (Hill q=2)

2. Beta Diversity (β): Between-site diversity using three methods

Hill numbers approach (β = γ/α)
Jaccard dissimilarity (presence/absence)
Bray-Curtis dissimilarity (abundance-based)

3. Gamma Diversity (γ): Total regional diversity across all sites
🚀 Quick Start
Prerequisites
Install required R packages:
install.packages(c("vegan", "iNEXT", "betapart", "dplyr", "tidyr"))
Running the Analysis

Clone or download this repository
Open Code/DiversityAnalyses.Rmd in RStudio
Update file paths in the code to point to your data location
Run all chunks or knit the document

Expected Runtime

Small datasets (< 50 sites): ~1-2 minutes
Medium datasets (50-200 sites): ~2-5 minutes
Large datasets (> 200 sites): ~5-10 minutes

📖 Documentation
This repository includes three comprehensive instruction documents:
1. Instructions-DiversityAnalysis.docx

Detailed explanation of what each diversity metric measures
Step-by-step walkthrough of the R code
Understanding the three beta diversity methods
How to customize the analysis for your needs

2. QuickReferenceGuide.docx
For quick lookups, this includes:

Copy-paste ready code snippets
Visual examples of diversity calculations
Formula references
Troubleshooting checklist
Common error solutions

3. DiversityAnalysisResultsInterpretation.docx
Learn how to interpret your results:

What do the numbers mean?
Example interpretations with real data
How to report results in publications
Statistical testing suggestions
Visualization examples

🔬 Methods Background
The Dataset
This analysis uses the same benthic macroinvertebrate dataset as the IBI (Index of Biotic Integrity) assessment module. The data includes:

141 unique sampling sites
182 taxa (primarily family-level identifications)
23 years of monitoring data (1994-2022)
Multiple habitat types and seasons

Diversity Metrics
Why use Hill numbers? Hill numbers (q = 0, 1, 2) provide a unified framework for measuring diversity:

All metrics are in units of "effective number of species"
Different q values emphasize different aspects of diversity
Mathematically related through β = γ/α

Why multiple beta diversity methods?

Hill numbers (β = γ/α) - Intuitive interpretation ("how many times composition changes")
Jaccard - Classic metric, good for presence/absence
Bray-Curtis - Accounts for abundance, sensitive to dominant taxa

Each method answers slightly different questions, providing complementary insights into community structure.
🎯 Learning Objectives
After completing this module, you will be able to:

Calculate alpha, beta, and gamma diversity for stream communities
Understand the differences between Hill numbers (q=0, 1, 2)
Compare and interpret multiple beta diversity metrics
Identify which taxa drive community differences
Assess temporal patterns in diversity
Report diversity results in publications

🐛 Troubleshooting
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
📚 Citation
If you use this code in your research, please cite:
Methods in Stream Ecology Textbook:
[update]
For Hill numbers methodology:
Chao, A., Chiu, C.H., and Jost, L. 2014. Unifying species diversity, phylogenetic diversity, functional diversity, and related similarity and differentiation measures through Hill numbers. Annual Review of Ecology, Evolution, and Systematics 45:297-324.
For beta diversity interpretation:
Jost, L. 2007. Partitioning diversity into independent alpha and beta components. Ecology 88(10):2427-2439.
🤝 Contributing
This is an educational resource. If you find errors or have suggestions for improvement, please:

Open an issue describing the problem or suggestion
For code fixes, submit a pull request
For documentation improvements, submit suggested edits

📧 Contact
For questions about this module:

Content questions: Refer to the Methods in Stream Ecology textbook
Technical issues: Check the troubleshooting section in QuickReferenceGuide.docx
Bug reports: Open an issue in this repository

📜 License
This educational material is provided for use with the Methods in Stream Ecology textbook. Please use responsibly and cite appropriately.

Happy analyzing! 🐛📊🌊

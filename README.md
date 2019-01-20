# GMMAT (Generalized linear Mixed Model Association Tests)
## Description
GMMAT is an R package for performing association tests using generalized linear mixed models (GLMMs, see <a href="https://doi.org/10.1080/01621459.1993.10594284">Breslow and Clayton (1993)</a>) in genome-wide association studies (GWAS) and sequencing association studies. First, GMMAT fits a GLMM with covariate adjustment and random effects to account for population structure and familial or cryptic relatedness. For GWAS, GMMAT performs score tests for each genetic variant as proposed in <a href="https://doi.org/10.1016/j.ajhg.2016.02.012">Chen et al. (2016)</a>. For candidate gene studies, GMMAT can also perform Wald tests to get the effect size estimate for each genetic variant. For rare variant analysis from sequencing association studies, GMMAT performs the variant Set Mixed Model Association Tests (SMMAT) as proposed in <a href="https://doi.org/10.1016/j.ajhg.2018.12.012">Chen et al. (2019)</a>, including the burden test, the sequence kernel association test (SKAT), SKAT-O and an efficient hybrid test of the burden test and SKAT, based on user-defined variant sets. See the vignette <a href="https://github.com/hanchenphd/GMMAT/blob/master/inst/doc/GMMAT.pdf">here</a>.
## Installing
GMMAT links to R packages <a href="https://cran.r-project.org/web/packages/Rcpp/index.html">Rcpp</a> and <a href="https://cran.r-project.org/web/packages/RcppArmadillo/index.html">RcppArmadillo</a>, and also imports R packages <a href="https://cran.r-project.org/web/packages/Rcpp/index.html">Rcpp</a>, <a href="https://cran.r-project.org/web/packages/CompQuadForm/index.html">CompQuadForm</a>, <a href="https://cran.r-project.org/web/packages/foreach/index.html">foreach</a>, <a href="https://cran.r-project.org/web/views/HighPerformanceComputing.html">parallel</a>, Bioconductor packages <a href="http://bioconductor.org/packages/release/bioc/html/SeqArray.html">SeqArray</a> and <a href="http://bioconductor.org/packages/release/bioc/html/SeqVarTools.html">SeqVarTools</a>. In addition, GMMAT requires <a href="https://cran.r-project.org/web/packages/testthat/index.html">testthat</a> to run code checks during development, and <a href="https://cran.r-project.org/web/packages/doMC/index.html">doMC</a> to run parallel computing in glmm.score and SMMAT functions for genotype files in the GDS format (however, <a href="https://cran.r-project.org/web/packages/doMC/index.html">doMC</a> is not available on Windows and these functions will switch to a single thread). These dependencies should be installed before installing GMMAT. See Section 3.2 of the <a href="https://github.com/hanchenphd/GMMAT/blob/master/inst/doc/GMMAT.pdf">vignette</a>.

For optimal computational performance, it is recommended to use an R version configured with the Intel Math Kernel Library (or other fast BLAS/LAPACK libraries). See the <a href="https://software.intel.com/en-us/articles/using-intel-mkl-with-r">instructions</a> on building R with Intel MKL.
## Version
The current version is 1.0.3 (January 14, 2019).
## License
This software is licensed under GPL-3.
## Contact
Please refer to the R help document of GMMAT for specific questions about each function. For comments, suggestions, bug reports and questions, please contact Han Chen (Han.Chen.2 AT uth.tmc.edu). For bug reports, please include an example to reproduce the problem without having to access your confidential data.
## Acknowledgments
We would like to thank Dr. Chaolong Wang and Dr. Brian Cade for comments and suggestions on GMMAT and the user manual. We would also like to thank Dr. Matthew Conomos for help with the Average Information REML algorithm, Dr. Stephanie Gogarten for help with the GDS genotype format, and Jennifer Brody for help with parallel computing and App development in <a href="http://analysiscommons.com/">Analysis Commons</a>, a cloud computing platform. The GMMAT implementation is supported by NIH grant R00 HL130593, and the analysis pipeline implementation (the gmmat App) in <a href="http://analysiscommons.com/">Analysis Commons</a> is supported by NIH grant U01 HL120393.
## References
<p>If you use the single-variant test in GMMAT, please cite
<li>Chen H, Wang C, Conomos MP, Stilp AM, Li Z, Sofer T, Szpiro AA, Chen W, Brehm JM, Celed&oacute;n JC, Redline S, Papanicolaou GJ, Thornton TA, Laurie CC, Rice K and Lin X. (2016) Control for Population Structure and Relatedness for Binary Traits in Genetic Association Studies via Logistic Mixed Models. <em>The American Journal of Human Genetics</em> <b>98(4):</b> 653-666. PMID: <a href="https://www.ncbi.nlm.nih.gov/pubmed/27018471">27018471</a>. PMCID: <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4833218/">PMC4833218</a>. DOI: <a href="https://doi.org/10.1016/j.ajhg.2016.02.012">10.1016/j.ajhg.2016.02.012</a>.</li></p>
<p>If you use the variant set tests SMMAT, please cite
<li>Chen H, Huffman JE, Brody JA, Wang C, Lee S, Li Z, Gogarten SM, Sofer T, Bielak LF, Bis JC, Blangero J, Bowler RP, Cade BE, Cho MH, Correa A, Curran JE, de Vries PS, Glahn DC, Guo X, Johnson AD, Kardia S, Kooperberg C, Lewis JP, Liu X, Mathias RA, Mitchell BD, O'Connell JR, Peyser PA, Post WS, Reiner AP, Rich SS, Rotter JI, Silverman EK, Smith JA, Vasan RS, Wilson JG, Yanek LR, NHLBI Trans-Omics for Precision Medicine (TOPMed) Consortium, TOPMed Hematology and Hemostasis Working Group, Redline S, Smith NL, Boerwinkle E, Borecki IB, Cupples LA, Laurie CC, Morrison AC, Rice KM, Lin X. (2019) Efficient Variant Set Mixed Model Association Tests for Continuous and Binary Traits in Large-Scale Whole-Genome Sequencing Studies.<em>The American Journal of Human Genetics</em> 2018 Dec 31 [Epub ahead of print]. PMID: <a href="https://www.ncbi.nlm.nih.gov/pubmed/30639324">30639324</a>. PMCID: In Process. DOI: <a href="https://doi.org/10.1016/j.ajhg.2018.12.012">10.1016/j.ajhg.2018.12.012</a>.</li></p>

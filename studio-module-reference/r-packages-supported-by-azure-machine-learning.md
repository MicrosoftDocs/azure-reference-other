---
title: "ML Studio (classic): Supported R Packages - Azure"
description: This article lists the R packages included by default in Machine Learning Studio (classic). 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs

---
# R Packages supported by Machine Learning Studio (classic)

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article lists the packages included by default in Machine Learning Studio (classic). To use one of the preloaded packages in your R code, you simply import the package using standard R syntax.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

> [!IMPORTANT]
> Packages available in Studio (classic) can be updated, or the version refreshed, without warning. To get the latest and most complete list of the R packages that are in the Machine Learning Studio (classic) environment, we recommend that you use [this script](#bkmk_code).

## Unsupported packages  

A number of packages (not listed here) are included in the Machine Learning environment but cannot be called from R code because of the following issues:

- The package has a Java dependency.
- The package binaries are not compatible with the sandboxed Azure environment.
- The package requires direct Internet access, or network access.

## <a name="bkmk_code"></a> Use R code to return package list as dataset

To get a list of the R packages in the current environment, add the following code to an instance of the [Execute R Script](execute-r-script.md):

```R
data.set <- data.frame(installed.packages())
maml.mapOutputPort("data.set")
```

## <a name="bkmk_List"></a> List of supported packages

Over 650 R packages are preloaded in the Machine Learning environment. This section lists the packages from CRAN and Microsoft R Open that are supported as of the date of this update (10/2018). 

**Index**

 [A](#bkmk_A) –      [B](#bkmk_B) – [C](#bkmk_C) – [D](#bkmk_D) – [E](#bkmk_E) – [F](#bkmk_F) – [G](#bkmk_G) – [H](#bkmk_H) – [I](#bkmk_I) – [J](#bkmk_J) – [K](#bkmk_K) – [L](#bkmk_L) – [M](#bkmk_M) – [N](#bkmk_N) – [O](#bkmk_O) – [P](#bkmk_P) – [Q](#bkmk_Q) – [R](#bkmk_R) – [S](#bkmk_S) – [T](#bkmk_T) – [U](#bkmk_U) – [V](#bkmk_V) – [W](#bkmk_W) – [X](#bkmk_X) – [Y](#bkmk_Y) – [Z](#bkmk_Z)  

The **Compatibility** column indicates whether the package is included with CRAN R 3.1 or  Microsoft R Open (MRO; currently 3.2.2 and 3.4.4). If not otherwise marked, the package is included with both.

> [!NOTE]
> Many new packages are now available from Microsoft R Open. This means that you can easily use the same R code in Azure ML Studio (classic), Microsoft R Server, and in SQL Server Machine Learning Services. 

###  <a name="bkmk_A"></a> A  

|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|abc|x|x|x| 
|abc.data||x|x|  
|abind|x|x|x|  
|acepack||x|x|  
|actuar|x|x|x|  
|ade4|x|x|x|  
|AdMit|x|x|x|  
|aod||x|x|
|ape|x|x|x|  
|aplpack|x|x|x|  
|approximator|x|x|x|  
|arm|x|x|x|
|arules|x|x|x|  
|arulesViz|x|x|x|  
|ash|x|x|x|  
|assertthat|x|x|x|  
|AtelieR |x|x|x|
|AzureML||x|x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_B"></a> B  

|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|BaBooN|x|x|x|  
|BACCO|x|x|x|
|backports| ||x|
|BaM|x|x|x|  
|bark|x|||  
|BAS|x|x|x|  
|base|x|x|x|  
|base64enc||x|x|  
|BayesDA|x|x|x|  
|bayesGARCH|x|x|x|  
|bayesm|x|x|x|  
|bayesmix|x|x|x|
|bayesQR|x|x|x|  
|bayesSurv|x|x|x|  
|Bayesthresh|x|x|x|  
|BayesTree|x|x|x|  
|BayesValidate|x|x|x|  
|BayesX|x|x|x|  
|BayHaz|x|x|x|  
|bbemkr|x|x|x|  
|BCBCSF|x|x|x|  
|BCE|x|x|x|  
|bclust|x|x|x|  
|bcp|x|x|x|  
|BenfordTests|x|x|x|  
|bfp|x|x|x|  
|BH|x|x|x|  
|bindr|||x|
|bindrcpp|||x|
|bisoreg|x|x|x|  
|bit|x|x|x|  
|bit64|x|x|x|  
|bitops|x|x|x|
|blob|||x|
|BLR|x|x|x|  
|BMA|x|x|x|  
|Bmix|x|x|x|  
|BMS|x|x|x|  
|bnlearn|x|x|x|  
|boa|x|x|x|  
|Bolstad|x|||  
|boot|x|x|x|  
|bootstrap|x|x|x|  
|bqtl|x|x|x|  
|BradleyTerry2|x|x|x|  
|brew|x|x|x|  
|brglm|x|x|x| 
|broom|||x|
|bspec|x|x|x|  
|bspmma|x|x|x| 
|BVS||x|x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_C"></a> C  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|C50|x|x|x|  
|cairoDevice|x|x|x| 
|calibrator|x|x|x|  
|car|x|x|x|  
|carData|||x|
|caret|x|x|x|  
|catnet|x|x|x|  
|caTools|x|x|x|  
|cclust||x|x| 
|cellranger|||x|
|checkmate|||x|
|checkpoint|||x|
|chron|x|x|x|  
|class|x|x|x| 
|classInt|||x|
|cli|||x|
|clue|x|x|x|  
|cluster|x|x|x|  
|clusterSim|x|x|x| 
|clv||x|x| 
|coda|x|x|x|  
|codetools|x|x|x|  
|coin|x|x|x|  
|colorspace|x|x|x|  
|combinat|x|x|x| 
|commonmark|||x|
|compiler|x|x|x|  
|CORElearn|x|x|x|  
|corpcor|x|x|x|  
|corrplot|x|x|x|  
|crayon||x|x|
|crosstalk|||x|
|cslogistic|x|x|x|  
|ctv|x|x|x|  
|cubature|x|x|x|  
|Cubist|||x|
|curl||x|x|
|CVST|||x|
|cvTools||x|x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_D"></a> D  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|data.table|x|x|x|  
|datasets|x|x|x|  
|date|x|x|x|  
|DBI|x|x|x|  
|dclone|x|x|x| 
|ddalpha|||x|
|deal|x|x|x|  
|Deducer|x|x|x|  
|DeducerExtras|x|x|x|  
|deepnet|x|x|x|  
|Defaults|x||| 
|deldir|x|x|x|  
|dendextend||x|x| 
|DEoptimR|x|x|x|  
|Deriv|||x|
|desc|||x|
|deSolve|x|x|x|  
|devtools|x|x|x|  
|DiagrammeR||x|x|
|dichromat|x|x|x|  
|digest|x|x|x|  
|dimRed|||x|
|diptest|||x|
|distrom|x|x|x|  
|dlm|x|x|x|  
|DMwR||x|x|
|doParallel||x|x|
|doRSR||x|x|
|doSNOW|x|x|x|  
|dotCall64|||x|
|downloader|||x|
|dplyr|x|x|x|  
|DPpackage|x|x|x|  
|DRR|||x|
|dse|x|x|x|  
|DT|||x|
|dtw||x|x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_E"></a> E  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|e1071|x|x|x|  
|earth|x|x|x|  
|EbayesThresh|x|x|x|  
|ebdbNet|x|x|x|  
|effects|x|x|x|  
|ellipse|x|x|x|  
|emulator|x|x|x|  
|ensembleBMA|x|x|x|  
|entropy|x|x|x| 
|estimability|||x|
|EvalEst|x|x|x|  
|evaluate|x|x|x|  
|evdbayes|x|x|x|  
|exactLoglinTest|x|x|x|  
|expint|||x|
|expm|x|x|x|  
|extremevalues|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_F"></a> F  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|FactoMineR|x|x|x|  
|factorQR|x|x|x|  
|faoutlier|x|x|x|  
|fBasics|x|x|x|  
|fields||x|x|  
|filehash|x|x|x|  
|fitdistrplus|x|x|x|  
|flashClust|x|x|x|  
|flexmix|||x|
|FME|x|x|x|  
|FNN|||x|
|forcats|||x|
|foreach|x|x|x|  
|forecast|x|x|x|
|foreign|x|x|x|  
|formatR|x|x|x|  
|Formula|x|x|x|
|fpc|||x|  
|fracdiff|x|x|x|  
|fTrading|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_G"></a> G  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|gam|x|x|x|  
|gamlr|x|x|x|  
|gbm|x|x|x|  
|gclus|x|x|x|  
|gdata|x|x|x|  
|gee|x|x|x|  
|gender||x|x|
|genetics|x|x|x|  
|geoR|x|x|x|  
|geoRglm|x|x|x|  
|geosphere|x|x|x|  
|GGally|x|x|x|  
|ggdendro|x|x|x| 
|ggformula|||x|
|ggmap|x|x|x|  
|ggmcmc|x|x|x|  
|ggplot2|x|x|x|  
|ggthemes|x|x|x|  
|git2r||x|x|
|glmmBUGS|x|x|x|  
|glmnet|x|x|x|  
|glue|||x|
|gmodels|x|x|x|  
|gmp|x|x|x|  
|gnm|x|x|x|  
|googlePublicData|x|x|x| 
|googleVis|x|x|x|  
|gower|||x|
|GPArotation|x|x|x|  
|gplots|x|x|x|  
|graphics|x|x|x|  
|grDevices|x|x|x|  
|gregmisc|x|||
|grid|x|x|x|  
|gridBase||x|x| 
|gridExtra|x|x|x|  
|growcurves|x|x|x|  
|grpreg|x|x|x|  
|gss|x|x|x|  
|gsubfn|x|x|x|  
|gtable|x|x|x|  
|gtools|x|x|x|
|gWidgets|x|x|x|  
|gWidgetsRGtk2|x|x|x|    
|gWidgetstcltk||x|x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_H"></a> H  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|haplo.stats|x|x|x|  
|hash|x|x|x|  
|haven|||x|
|hbsae|x|x|x|  
|hdrcde|x|x|x|  
|heavy|x|x|x|  
|hexbin|x|x|x|
|hflights|x|x|x|  
|HH|x|x|x|  
|HI|x|x|x|  
|highr|x|x|x|  
|HistData|x|x|x|  
|Hmisc|x|x|x|
|hms|||x|
|HSAUR|x|x|x|  
|htmlTable|||x|
|htmltools|x|x|x|  
|htmlwidgets||x|x|
|httpuv|x|x|x|  
|httr|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_I"></a> I  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|IBrokers|x|x|x|  
|ifultools||x|x|
|igraph|x|x|x| 
|influenceR|||x|
|inline|x|x|x|  
|intervals|x|x|x| 
|inum|||x|
|iplots||x|x|
|ipred|x|x|x|  
|irlba||x|x|
|irr|x|x|x|  
|iterators|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_J"></a> J  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|JavaGD|x|x|x|
|JGR|x|x|x| 
|jpeg|x|x|x|  
|jsonlite|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_K"></a> K  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|kernlab|x|x|x|  
|KernSmooth|x|x|x|  
|KFKSDS|x|x|x|  
|kinship2|x|x|x|  
|kknn|x|x|x|  
|klaR|x|x|x|  
|knitr|x|x|x|  
|ks|x|x|x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_L"></a> L  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|labeling|x|x|x|  
|labelled|||x|
|laeken|||x|
|Lahman|x|x|x|  
|lars|x|x|x|  
|lattice|x|x|x|  
|latticeExtra|x|x|x|  
|lava|x|x|x|  
|lavaan|x|x|x|  
|lazyeval|x|x|x|  
|leaps|x|x|x|  
|LearnBayes|x|x|x|  
|libcoin|||x|
|LiblineaR|x|x|x|  
|limSolve|x|x|x|  
|lme4|x|x|x|  
|lmm|x|x|x|  
|lmPerm|x||
|lmtest|x|x|x|  
|locfit|x|x|x|  
|locpol||x|x|
|LogicReg|x|x|x|
|longitudinalData||x|x|
|lpSolve|x|x|x|  
|lsa|x|x|x| 
|LSAfun||x|x|
|lubridate|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_M"></a> M  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|magic|x|x|x|  
|magrittr|x|x|x|  
|manipulateWidget|||x|
|mapdata|x|x|x|  
|mapproj|x|x|x|  
|maps|x|x|x|  
|maptools|x|x|x|  
|maptree|x|x|x|  
|markdown|x|x|x|  
|MASS|x|x|x|  
|MasterBayes|x|x|x|  
|Matrix|x|x|x|  
|matrixcalc|x|x|x|  
|MatrixModels|x|x|x|  
|maxent|x|x|x|  
|maxLik|x|x|x|  
|mboost|x|x|x|  
|mclust|||x|
|mcmc|x|x|x|  
|MCMCglmm|x|x|x|  
|MCMCpack|x|x|x| 
|mda|x|x|x|  
|memoise|x|x|x|  
|methods|x|x|x|  
|mgcv|x|x|x|
|mi||x|x|
|mice|x|x|x|  
|microbenchmark|x|x|x|  
|mime|x|x|x|  
|miniCRAN||x|x|
|miniUI|||x|
|minpack.lm|x|x|x|  
|minqa|x|x|x|  
|mirt||x|x| 
|misc3d|x|x|x|  
|miscF|x|x|x| 
|miscTools|x|x|x|  
|mixtools|x|x|x|  
|mlbench|x|x|x|  
|mlogitBMA|x|x|x|  
|mnormt|x|x|x|  
|MNP|x|x|x|  
|modeest|||x|
|ModelMetrics|||x|
|modeltools|x|x|x|  
|mombf|x|x|x|  
|monomvn|x|x|x|  
|monreg|x|x|x|  
|mosaic|x|x|x|  
|mosaicCore|||x|
|mosaicData|x|x|x|  
|MSBVAR|x|x|x|  
|msm|x|x|x|  
|multcomp|x|x|x|  
|multicool|x|x|x|  
|munsell|x|x|x|  
|mvoutlier|x|x|x|  
|mvtnorm|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_N"></a> N  

|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|ncvreg|x|x|x| 
|network|||x|
|nlme|x|x|x|  
|nloptr|x|x|x|  
|NLP|x|x|x|  
|NMF||x|x|
|nnet|x|x|x|  
|nnls|x|x|x|  
|numbers|x|x|x|  
|numDeriv|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_O"></a> O  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|   
|OceanView|||x|
|openNLP|x|x|x|
|openNLPdata|x|x|x|
|openssl||x|x| 
|OutlierDC|x|x|x|  
|OutlierDM|x|x|x|  
|outliers|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_P"></a> P  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|pacbpred|x|x|x|  
|parallel|x|x|x|  
|partitions|x|x|x|  
|party|x|x|x|  
|partykit||x|x|  
|PAWL|x|x|x|  
|pbapply|||x|
|pbivnorm|x|x|x| 
|pbkrtest|||x|
|pcaPP|x|x|x|  
|pdc||x|x|  
|PerformanceAnalytics|x|x|x|  
|permute|x|x|x|  
|pillar|||x|
|pkgconfig|||x|
|pkgmaker||x|x| 
|pkgXMLBuilder||x|x|
|plogr|||x|
|plot3D|||x|
|plot3Drgl|||x|
|plotly|||x|
|plotmo|x|x|x|  
|plotrix|x|x|x|  
|pls|x|x|x|  
|plyr|x|x|x|  
|png|x|x|x|  
|polspline|x|x|x|  
|polynom|x|x|x|  
|PottsUtils|x|x|x|  
|prablclus|||x|
|praise||x|x| 
|predmixcor|x|x|x|  
|PresenceAbsence|x|x|x|  
|prettyunits|||x|
|pROC|x|x|x|  
|prodlim|x|x|x|  
|profdpm|x|x|x|  
|profileModel|x|x|x|  
|progress|||x|
|proto|x|x|x|  
|proxy||x|x| 
|pryr|x|x|x|  
|pscl|x|x|x|  
|psych|x|x|x|  
|purr|||x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_Q"></a> Q  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|qap||x|x|
|qdap||x|x|
|qdapDictionaries|x|x|x|  
|qdapRegex|x|x|x|  
|qdapTools|x|x|x|  
|quadprog|x|x|x|  
|quantmod|x|x|x|  
|quantreg|x|x|x| 
|questionr|||x|
|qvcalc|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_R"></a> R  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|R.matlab|x|x|x|  
|R.methodsS3|x|x|x|  
|R.oo|x|x|x|  
|R.utils|x|x|x|  
|R2HTML|x|x|x| 
|R2jags|x|x|x| 
|R2OpenBUGS|x|x|x|  
|R2WinBUGS|x|x|x|  
|R6|x|x|x|  
|ramps|x|x|x|  
|RandomFields|x|x|x|  
|RandomFieldsUtils||x|x| 
|randomForest|x|x|x|  
|RArcInfo|x|x|x|  
|raster|x|x|x|  
|rattle|x|x|x|
|rbenchmark|x|x|x|  
|rbugs|x|x|x|  
|RColorBrewer|x|x|x|  
|Rcpp|x|x|x|  
|RcppArmadillo|x|x|x|  
|rcppbugs|x|x|x|  
|RcppEigen|x|x|x|  
|RcppExamples|x|x|x| 
|RcppRoll|||x|
|RCurl|x|x|x|  
|readr||x|x|
|readxl|||x|
|recipes|||x|
|registry||x|x|  
|relimp|x|x|x|  
|rematch|||x|
|reports|x|x|x|  
|reshape|x|x|x|  
|reshape2|x|x|x|  
|RevoIOQ||x|x| 
|revoIpe||x|x|
|RevoMods||x|x| 
|RevoPemaR||x|x| 
|RevoRpeConnector||x|x|
|RevoRsrConnector||x|x|
|RevoTreeView||x|x| 
|RevoUtils||x|x| 
|RevoUtilsMath||x|x|
|rgdal|x|x|x|  
|rgeos|x|x|x|  
|regx|||x|
|rgl||x|x|
|RgoogleMaps|x|x|x|  
|RGraphics|x|x|x|  
|RGtk2|x|x|x|
|RINside||x|x|
|RJaCGH|x|x|x|  
|rjags||x|x|
|Rjava|x|x|x|
|rjson|x|x|x|  
|RJSONIO|x|x|x|  
|rlang|||x|
|rlecuyer||x|x| 
|Rmpfr||x|x| 
|rms||x|x| 
|RMySQL||x|x|
|rngtools||x|x|  
|robCompositions|x|x|x| 
|robustbase|x|x|x|  
|ROCR|x|x|x|  
|RODBC|x|x|x|  
|Rook|||x|
|rootSolve|x|x|x|  
|roxygen|x|||  
|roxygen2|x|x|x|  
|rpart|x|x|x|  
|rpart.plot|x|x|x|  
|rprojroot|||x|
|rrcov|x|x|x|  
|rscproxy|x|x|x|  
|RSGHB|x|x|x|  
|RSNNS|x|x|x|  
|RSQLite|x|x|x|  
|rstudioapi||x|x| 
|RTextTools|x|x|x|  
|RUnit|x|x|x|  
|runjags|x|x|x|  
|Runuran|x|x|x|  
|RWekajars|x|x|x|
|rworldmap|x|x|x|  
|rworldxtra|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_S"></a> S  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|SampleSizeMeans|x|x|x|  
|SampleSizeProportions|x|x|x|  
|sandwich|x|x|x|  
|sbgcop|x|x|x|  
|scales|x|x|x|  
|scapeMCMC|x|||  
|scatterplot3d|x|x|x|  
|sciplot|x|x|x|  
|segmented|x|x|x|  
|sem|x|x|x|  
|seriation|x|x|x|  
|setRNG|x|x|x|  
|sfsmisc||x|x|
|sgeostat|x|x|x|  
|shape|||x|
|shapefiles|x|x|x|  
|shiny|x|x|x|  
|SimpleTable|x|x|x|  
|SIS|x|x|x|  
|skmeans|x|x|x|  
|slam|x|x|x|  
|smoothSurv|x|x|x|  
|sna|x|x|x|  
|snow|x|x|x|  
|SnowballC|x|x|x|  
|snowFT|x|x|x|  
|sourcetools|||x|
|sp|x|x|x|  
|spacetime|x|x|x|  
|spam||x|x| 
|SparseM|x|x|x|  
|spatial|x|x|x|  
|spBayes|x|x|x|
|spData|||x| 
|spdep|x|x|x|  
|spikeslab|x|x|x|  
|splancs|x|x|x|  
|splines|x|x|x|  
|spls|x|x|x|  
|splus2R||x|x| 
|spTimer|x|x|x|
|SQUAREM|||x|
|sqldf|x|x|x|
|sROC||x|x| 
|stabledist|x|x|x|  
|stabs|x|x|x| 
|statnet.common|||x|
|stats|x|x|x|  
|stats4|x|x|x|  
|stepPlr|x|x|x|  
|stochvol|x|x|x|  
|stringdist|x|x|x|  
|stringi|x|x|x|  
|stringr|x|x|x|  
|strucchange|x|x|x|  
|stsm|x|x|x|  
|stsm.class|x|x|x|  
|SuppDists|x|x|x|  
|survey|||x|
|survival|x|x|x|  
|svmpath|x|x|x|  
|svUnit|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_T"></a> T  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|tau|x|x|x|  
|tcltk|x|x|x|  
|tcltk2|x|x|x|  
|TeachingDemos|x|x|x|  
|tensorA|x|x|x|  
|testthat|x|x|x|  
|textcat|x|x|x|  
|textir|x|x|x|  
|tfplot|x|x|x|  
|tframe|x|x|x|  
|tgp|x|x|x|  
|TH.data|x|x|x| 
|tibble|||x|
|tidyr|x|x|x| 
|tidyselect|||x|
|timeDate|x|x|x|  
|timeSeries|x|x|x|  
|tm|x|x|x|  
|tools|x|x|x|  
|topicmodels|x|x|x|  
|tree|x|x|x|  
|trimcluster|||x|
|TSclust||x|x|
|tseries|x|x|x|  
|tsfa|x|x|x|  
|tsoutliers|x|x|x|  
|TSP|x|x|x|  
|TTR|x|x|x|  
|twitteR|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_U"></a> U  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|UsingR|x|x|x| 
|utf8|||x|
|utils|x|x|x|  
|uuid||x|x| 
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_V"></a> V  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|   
|varSelectIP|x|||  
|vcd|x|x|x|  
|vegan|x|x|x|
|venneuler|x|x|x|  
|VGAM|x|x|x|  
|VIF|x|x|x|  
|VIM||x|x|
|viridis|||x|
|viridisLite|||x|
|visNetwork||x|x|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_W"></a> W  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|  
|wavethresh|||x|
|whisker|x|x|x|  
|withr||x|x| 
|wmtsa||x|x| 
|wordcloud|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_X"></a> X  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|xgboost||x|x|
|XLConnect|x|x|x|
|XLConnectJars|x|x|x|  
|xlsx|x|x|x|
|xlsxjars|x|x|x|
|XML|x|x|x| 
|xml2|||x|
|xtable|x|x|x|  
|xts|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_Y"></a> Y  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-| 
|yaml|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_Z"></a> Z  
  
|**Package name**|**CRAN R 3.1**|**MRO 3.2.2**|**MRO 3.4.4**| 
|-|-|-|-|   
|zic|x|x|x|  
|zipfR|x|x|x|  
|zoo|x|x|x|  
  
 [List of supported packages](#bkmk_List)  
  
## See also

 [R Language Modules](r-language-modules.md)

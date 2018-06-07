---
title: "R Packages Supported by Azure Machine Learning | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/24/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 309a7f30-0da4-43b3-8a41-6203dcd78710
caps.latest.revision: 10
author: rastala
ms.author: roastala
manager: cgronlun
---
# R Packages supported by Azure Machine Learning Studio

This article lists the packages included by default in Azure Machine Learning Studio. Approximately 400 R packages are preloaded in the Azure Machine Learning environment. To use one of the preloaded packages in your R code, you simply import the package using standard R syntax.

> [!IMPORTANT]
> Packages available in Studio can be updated, or the version refreshed, without warning. To get the latest and most complete list of the R packages that are in the Azure Machine Learning Studio environment, we recommend that you use [this script](#bkmk_code).

## Unsupported packages  

A number of packages (not listed here) are included in the Azure Machine Learning environment but cannot be called from R code because of the following issues:

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

This section lists the packages from CRAN and Microsoft R Open that are supported as of the date of this update (4/2017).

**Index**

 [A](#bkmk_A) –      [B](#bkmk_B) – [C](#bkmk_C) – [D](#bkmk_D) – [E](#bkmk_E) – [F](#bkmk_F) – [G](#bkmk_G) – [H](#bkmk_H) – [I](#bkmk_I) – [J](#bkmk_J) – [K](#bkmk_K) – [L](#bkmk_L) – [M](#bkmk_M) – [N](#bkmk_N) – [O](#bkmk_O) – [P](#bkmk_P) – [Q](#bkmk_Q) – [R](#bkmk_R) – [S](#bkmk_S) – [T](#bkmk_T) – [U](#bkmk_U) – [V](#bkmk_V) – [W](#bkmk_W) – [X](#bkmk_X) – [Y](#bkmk_Y) – [Z](#bkmk_Z)  

The **Compatibility** column indicates whether the package is included with CRAN R 3.1 or  Microsoft R Open (MRO; currently 3.2.2). If not otherwise marked, the package is included with both.

> [!NOTE]
> Many new packages are now available from Microsoft R Open. This means that you can easily use the same R code in Azure ML Studio, Microsoft R Server, and in SQL Server Machine Learning Services. 

###  <a name="bkmk_A"></a> A  

|**Package name**|**Compatibility**|  
|-|-|  
|abc||  
|abc.data|MRO only|  
|abind||  
|acepack|MRO only|  
|actuar||  
|ade4||  
|AdMit||  
|aplpack||  
|ape||  
|aplpack||  
|approximator||  
|arm||
|arules||  
|arulesViz||  
|ash||  
|assertthat||  
|AtelieR ||
|AzureML|MRO only|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_B"></a> B  

|**Package name**|**Compatibility**|  
|-|-|  
|BaBooN||  
|BACCO||  
|BaM||  
|bark|CRAN R only|  
|BAS||  
|base||  
|base4enc|MRO only|  
|BayesDA||  
|bayesGARCH||  
|bayesm||  
|bayesmix||
|bayesQR||  
|bayesSurv||  
|Bayesthresh||  
|BayesTree||  
|BayesValidate||  
|BayesX||  
|BayHaz||  
|bbemkr||  
|BCBCSF||  
|BCE||  
|bclust||  
|bcp||  
|BenfordTests||  
|bfp||  
|BH||  
|bisoreg||  
|bit||  
|bit64||  
|bitops||  
|BLR||  
|BMA||  
|Bmix||  
|BMS||  
|bnlearn||  
|boa||  
|Bolstad|CRAN R only|  
|boot||  
|bootstrap||  
|bqtl||  
|BradleyTerry2||  
|brew||  
|brglm||  
|bspec||  
|bspmma||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_C"></a> C  
  
|||  
|-|-|  
|**Package name**|**Compatibility**|  
|C50||  
|cairoDevice|| 
|calibrator||  
|car|CRAN R only|  
|caret|CRAN R only|  
|catnet||  
|caTools||  
|cclust|MRO only|  
|chron||  
|class||  
|clue||  
|cluster||  
|clusterSim|| 
|clv|MRO only|  
|coda||  
|codetools||  
|coin||  
|colorspace||  
|combinat||  
|compiler||  
|CORElearn||  
|corpcor||  
|corrplot||  
|crayon|MRO only|  
|cslogistic||  
|ctv||  
|cubature||  
|curl|MRO only| 
|cvTools|MRO only|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_D"></a> D  
  
|**Package name**|**Compatibility**|  
|-|-|  
|data.table||  
|datasets||  
|date||  
|DBI||  
|dclone|CRAN R only|  
|deal||  
|Deducer||  
|DeducerExtras||  
|deepnet||  
|Defaults|CRAN R only|  
|deldir||  
|dendextend|MRO only|  
|DEoptimR||  
|deSolve||  
|devtools||  
|DiagrammeR|MRO only|  
|dichromat||  
|digest||  
|distrom||  
|dlm||  
|DMwR|MRO only|  
|doParallel|MRO only|  
|doRSR|MRO only|
|doSNOW||  
|dplyr||  
|DPpackage||  
|dse||  
|dtw|MRO only|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_E"></a> E  
  
|**Package name**|**Compatibility**| 
|-|-|   
|e1071||  
|earth||  
|EbayesThresh||  
|ebdbNet||  
|effects||  
|ellipse||  
|emulator||  
|ensembleBMA||  
|entropy||  
|EvalEst||  
|evaluate||  
|evdbayes||  
|exactLoglinTest||  
|expm||  
|extremevalues||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_F"></a> F  
  
|||  
|-|-|  
|**Package name**|**Compatibility**|  
|FactoMineR||  
|factorQR||  
|faoutlier||  
|fBasics||  
|fields|MRO only|  
|filehash||  
|fitdistrplus||  
|flashClust||  
|FME||  
|foreach||  
|forecast||  
|foreign||  
|formatR||  
|Formula||  
|fracdiff||  
|fTrading||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_G"></a> G  
  
|**Package name**|**Compatibility**|  
|-|-|  
|gam||  
|gamlr||  
|gbm||  
|gclus||  
|gdata||  
|gee||  
|gender|MRO only|  
|genetics||  
|geoR||  
|geoRglm||  
|geosphere||  
|GGally||  
|ggdendro||  
|ggmap||  
|ggmcmc||  
|ggplot2||  
|ggthemes||  
|git2r|MRO only|  
|glmmBUGS||  
|glmnet||  
|gmodels||  
|gmp||  
|gnm||  
|googlePublicData|| 
|googleVis||  
|GPArotation||  
|gplots||  
|graphics||  
|grDevices||  
|gregmisc|CRAN R only|  
|grid||  
|gribBase|MRO only|  
|gridExtra||  
|growcurves||  
|grpreg||  
|gss||  
|gsubfn||  
|gtable||  
|gtools||
|gWidgets||  
|gWidgetsRGtk2||    
|gWidgetstcltk|MRO only|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_H"></a> H  
  
|**Package name**|**Compatibility**|  
|-|-|  
|haplo.stats||  
|hash||  
|hbsae||  
|hdrcde||  
|heavy||  
|hflights||  
|HH||  
|HI||  
|highr||  
|HistData||  
|Hmisc||  
|HSAUR||  
|htmltools||  
|htmlwidgets|MRO only|  
|httpuv||  
|httr||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_I"></a> I  
  
|**Package name**|**Compatibility**|  
|-|-|  
|IBrokers||  
|ifultools|MRO only|  
|igraph||  
|inline||  
|intervals||  
|ipred||  
|irlba|MRO only|  
|irr||  
|iterators||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_J"></a> J  
  
|**Package name**|**Compatibility**|  
|-|-| 
|JavaGD||
|JGR|| 
|jpeg||  
|jsonlite||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_K"></a> K  
  
|**Package name**|**Compatibility**|  
|-|-|  
|kernlab||  
|KernSmooth||  
|KFKSDS||  
|kinship2||  
|kknn||  
|klaR||  
|knitr||  
|ks||
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_L"></a> L  
  
|**Package name**|**Compatibility**|  
|-|-|  
|labeling||  
|Lahman||  
|lars||  
|lattice||  
|latticeExtra||  
|lava||  
|lavaan||  
|lazyeval||  
|leaps||  
|LearnBayes||  
|LiblineaR||  
|limSolve||  
|lme4||  
|lmm||  
|lmPerm|CRAN R only|  
|lmtest||  
|locfit||  
|logpol|MRO only|  
|LogicReg||
|longitudinalData|MRO only|  
|lpSolve||  
|lsa||  
|LSAfun||
|lubridate||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_M"></a> M  
  
|**Package name**|**Compatibility**|  
|-|-|  
|magic||  
|magrittr||  
|mapdata||  
|mapproj||  
|maps||  
|maptools||  
|maptree||  
|markdown||  
|MASS||  
|MasterBayes||  
|Matrix||  
|matrixcalc||  
|MatrixModels||  
|maxent||  
|maxLik||  
|mboost||  
|mcmc||  
|MCMCglmm||  
|MCMCpack|CRAN R only|  
|mda||  
|memoise||  
|methods||  
|mgcv|CRAN R only|  
|mi|MRO only|  
|mice||  
|microbenchmark||  
|mime||  
|miniCRAN|MRO only|  
|minpack.lm||  
|minqa||  
|mirt|MRO only|  
|misc3d||  
|miscF|CRAN R only|  
|miscTools||  
|mixtools||  
|mlbench||  
|mlogitBMA||  
|mnormt||  
|MNP||  
|modeltools||  
|mombf||  
|monomvn||  
|monreg||  
|mosaic|CRAN R only|  
|mosaicData||  
|MSBVAR||  
|msm||  
|multcomp||  
|multicool||  
|munsell||  
|mvoutlier|CRAN R only|  
|mvtnorm||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_N"></a> N  

|**Package name**|**Compatibility**|  
|-|-|  
|ncvreg||  
|nlme||  
|nloptr||  
|NLP||  
|NMF|MRO only|  
|nnet||  
|nnls||  
|numbers||  
|numDeriv||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_O"></a> O  
  
|**Package name**|**Compatibility**|  
|-|-|  
|openNLP||
|openNLPdata|
|openssl|MRO only|  
|OutlierDC||  
|OutlierDM||  
|outliers||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_P"></a> P  
  
|**Package name**|**Compatibility**|  
|-|-|  
|pacbpred||  
|parallel||  
|partitions||  
|party||  
|partykit|MRO only|  
|PAWL||  
|pbivnorm||  
|pcaPP||  
|pdc|MRO only|  
|PerformanceAnalytics||  
|permute||  
|pkgmaker|MRO only|  
|pkgXMLBuilder|MRO only|  
|plotmo||  
|plotrix||  
|pls||  
|plyr||  
|png||  
|polspline||  
|polynom||  
|PottsUtils||  
|praise|MRO only|  
|predmixcor||  
|PresenceAbsence||  
|pROC||  
|prodlim||  
|profdpm||  
|profileModel||  
|proto||  
|proxy|MRO only|  
|pryr||  
|pscl||  
|psych||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_Q"></a> Q  
  
|**Package name**|**Compatibility**|  
|-|-|  
|qap|MRO only|  
|qdapDictionaries||  
|qdapRegex||  
|qdapTools|CRAN R only|  
|quadprog||  
|quantmod||  
|quantreg||  
|qvcalc||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_R"></a> R  
  
|**Package name**|**Compatibility**|  
|-|-|  
|R.matlab||  
|R.methodsS3||  
|R.oo||  
|R.utils||  
|R2HTML|| 
|R2jags|| 
|R2OpenBUGS||  
|R2WinBUGS||  
|R6||  
|ramps||  
|RandomFields||  
|RandomFieldsUtils|MRO only|  
|randomForest||  
|RArcInfo||  
|raster||  
|rattle||
|rbenchmark||  
|rbugs||  
|RColorBrewer||  
|Rcpp||  
|RcppArmadillo||  
|rcppbugs||  
|RcppEigen||  
|RcppExamples||  
|RCurl||  
|readr|MRO only|  
|registry|MRO only|  
|relimp||  
|reports||  
|reshape||  
|reshape2||  
|RevoIOQ|MRO only|  
|revoIpe|MRO only|
|RevoMods|MRO only|  
|RevoPemaR|MRO only| 
|RevoRpeConnector|MRO only| 
|RevoRsrConnector|MRO only| 
|RevoTreeView|MRO only| 
|RevoUtils|MRO only|   
|RevoUtilsMath|MRO only|
|rgdal||  
|rgeos||  
|RgoogleMaps||  
|RGraphics||  
|RGtk2||
|RINside|MRO only|  
|RJaCGH||  
|Rjava||
|rjson||  
|RJSONIO||  
|rlecuyer|MRO only|  
|Rmpfr|MRO only|  
|rms|MRO only|  
|RMySQL|MRO only|
|rngtools|MRO only|  
|robCompositions|CRAN R only| 
|robustbase||  
|ROCR||  
|RODBC||  
|rootSolve||  
|roxygen|CRAN R only|  
|roxygen2||  
|rpart||  
|rpart.plot||  
|rrcov||  
|rscproxy||  
|RSGHB||  
|RSNNS||  
|RSQLite||  
|rstudioapi|MRO only|  
|RTextTools||  
|RUnit||  
|runjags||  
|Runuran||  
|Rekajars||
|rworldmap||  
|rworldxtra||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_S"></a> S  
  
|**Package name**|**Compatibility**|  
|-|-|  
|SampleSizeMeans||  
|SampleSizeProportions||  
|sandwich||  
|sbgcop||  
|scales||  
|scapeMCMC|CRAN R only|  
|scatterplot3d||  
|sciplot||  
|segmented||  
|sem||  
|seriation||  
|setRNG||  
|sfsmisc|MRO only|  
|sgeostat||  
|shapefiles||  
|shiny||  
|SimpleTable||  
|SIS||  
|skmeans||  
|slam||  
|smoothSurv||  
|sna||  
|snow||  
|SnowballC||  
|snowFT||  
|sp||  
|spacetime||  
|spam|MRO only|  
|SparseM||  
|spatial||  
|spBayes||  
|spdep||  
|spikeslab||  
|splancs||  
|splines||  
|spls||  
|splus2R|MRO only|  
|spTimer||  
|sqldf||  
|sROC|MRO only|  
|stabledist||  
|stabs||  
|stats||  
|stats4||  
|stepPlr||  
|stochvol||  
|stringdist||  
|stringi||  
|stringr||  
|strucchange||  
|stsm||  
|stsm.class||  
|SuppDists||  
|survival||  
|svmpath||  
|svUnit||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_T"></a> T  
  
|**Package name**|**Compatibility**|  
|-|-|  
|tau||  
|tcltk||  
|tcltk2||  
|TeachingDemos||  
|tensorA||  
|testthat||  
|textcat||  
|textir||  
|tfplot||  
|tframe||  
|tgp||  
|TH.data||  
|tidyr||  
|timeDate||  
|timeSeries||  
|tm||  
|tools||  
|topicmodels||  
|tree||  
|TSclust|MRO only|
|tseries||  
|tsfa||  
|tsoutliers||  
|TSP||  
|TTR||  
|twitteR||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_U"></a> U  
  
|**Package name**|**Compatibility**|  
|-|-|  
|UsingR||  
|utils||  
|uuid|MRO only|  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_V"></a> V  
  
|**Package name**|**Compatibility**|  
|-|-|  
|varSelectIP|CRAN R only|  
|vcd||  
|vegan||
|venneuler||  
|VGAM||  
|VIF||  
|VIM|MRO only|
|visNetwork|MRO only|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_W"></a> W  
  
|**Package name**|**Compatibility**|  
|-|-|  
|whisker||  
|withr|MRO only|  
|wmtsa|MRO only|  
|wordcloud||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_X"></a> X  
  
|**Package name**|**Compatibility**|  
|-|-|  
|xgboost|MRO only|
|XLConnect||
|XLConnectJars||  
|xlsx||
|xlsxjars||
|XML||  
|xtable||  
|xts||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_Y"></a> Y  
  
|**Package name**|**Compatibility**|  
|-|-|  
|yaml||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_Z"></a> Z  
  
|**Package name**|**Compatibility**|  
|-|-|  
|zic||  
|zipfR||  
|zoo||  
  
 [List of supported packages](#bkmk_List)  
  
## See also

 [R Language Modules](r-language-modules.md)

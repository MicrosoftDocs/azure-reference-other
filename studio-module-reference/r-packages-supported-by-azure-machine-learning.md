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
|aod|MRO 3.4.4 only|
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
|backports| MRO 3.4.4. only|
|BaM||  
|bark|CRAN R only|  
|BAS||  
|base||  
|base64enc|MRO only|  
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
|bindr|MRO 3.4.4 only|
|bindrcpp|MRO 3.4.4 only|
|bisoreg||  
|bit||  
|bit64||  
|bitops||
|blob|MRO 3.4.4 only|
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
|broom|MRO 3.4.4 only|
|bspec||  
|bspmma|| 
|BVS|MRO 3.4.4 only|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_C"></a> C  
  
|||  
|-|-|  
|**Package name**|**Compatibility**|  
|C50||  
|cairoDevice|| 
|calibrator||  
|car|CRAN R only|  
|carData|MRO 3.4.4 only|
|caret|CRAN R only|  
|catnet||  
|caTools||  
|cclust|MRO only|  
|cellranger|MRO 3.4.4 only|
|checkmate|MRO 3.4.4 only|
|checkpoint|MRO 3.4.4 only|
|chron||  
|class|| 
|classInt|MRO 3.4.4 only|
|cli|MRO 3.4.4 only|
|clue||  
|cluster||  
|clusterSim|| 
|clv|MRO only|  
|coda||  
|codetools||  
|coin||  
|colorspace||  
|combinat|| 
|commonmark|MRO 3.4.4 only|
|compiler||  
|CORElearn||  
|corpcor||  
|corrplot||  
|crayon|MRO only|  
|crosstalk|MRO 3.4.4 only|
|cslogistic||  
|ctv||  
|cubature||  
|Cubist|MRO 3.4.4 only|
|curl|MRO only| 
|CVST|MRO 3.4.4 only|
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
|ddalpha|MRO 3.4.4 only|
|deal||  
|Deducer||  
|DeducerExtras||  
|deepnet||  
|Defaults|CRAN R only|  
|deldir||  
|dendextend|MRO only|  
|DEoptimR||  
|Deriv|MRO 3.4.4 only|
|desc|MRO 3.4.4 only|
|deSolve||  
|devtools||  
|DiagrammeR|MRO only|  
|dichromat||  
|digest||  
|dimRed|MRO 3.4.4 only|
|diptest|MRO 3.4.4 only|
|distrom||  
|dlm||  
|DMwR|MRO only|  
|doParallel|MRO only|  
|doRSR|MRO only|
|doSNOW||  
|dotCall64|MRO 3.4.4 only|
|downloader|MRO 3.4.4 only|
|dplyr||  
|DPpackage||  
|DRR|MRO 3.4.4 only|
|dse||  
|DT|MRO 3.4.4 only|
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
|estimability|MRO 3.4.4 only|
|EvalEst||  
|evaluate||  
|evdbayes||  
|exactLoglinTest||  
|expint|MRO 3.4.4 only|
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
|flexmix|MRO 3.4.4 only|
|FME||  
|FNN|MRO 3.4.4 only|
|forcats|MRO 3.4.4 only|
|foreach||  
|forecast||
|foreign||  
|formatR||  
|Formula||
|fpc|MRO 3.4.4 only|  
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
|ggformula|MRO 3.4.4 only|
|ggmap||  
|ggmcmc||  
|ggplot2||  
|ggthemes||  
|git2r|MRO only|  
|glmmBUGS||  
|glmnet||  
|glue|MRO 3.4.4 only|
|gmodels||  
|gmp||  
|gnm||  
|googlePublicData|| 
|googleVis||  
|gower|MRO 3.4.4 only|
|GPArotation||  
|gplots||  
|graphics||  
|grDevices||  
|gregmisc|CRAN R only|  
|grid||  
|gridBase|MRO only|  
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
|haven|MRO 3.4.4 only|
|hbsae||  
|hdrcde||  
|heavy||  
|hexbin|
|hflights||  
|HH||  
|HI||  
|highr||  
|HistData||  
|Hmisc||  
|hms|MRO 3.4.4 only|
|HSAUR||  
|htmlTable|MRO 3.4.4 only|
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
|influenceR|MRO 3.4.4 only|
|inline||  
|intervals|| 
|inum|MRO 3.4.4 only|
|iplots|MRO 3.4.4 only|
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
|labelled|MRO 3.4.4 only|
|laeken|MRO 3.4.4 only|
|Lahman||  
|lars||  
|lattice||  
|latticeExtra||  
|lava||  
|lavaan||  
|lazyeval||  
|leaps||  
|LearnBayes||  
|libcoin|MRO 3.4.4 only|
|LiblineaR||  
|limSolve||  
|lme4||  
|lmm||  
|lmPerm|CRAN R only|  
|lmtest||  
|locfit||  
|locpol|MRO only|  
|LogicReg||
|longitudinalData|MRO only|  
|lpSolve||  
|lsa|| 
|LSAfun|MRO 3.4.4 only|
|lubridate||  
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_M"></a> M  
  
|**Package name**|**Compatibility**|  
|-|-|  
|magic||  
|magrittr||  
|manipulateWidget|MRO 3.4.4 only|
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
|mclust|MRO 3.4.4 only|
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
|miniUI|MRO 3.4.4 only|
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
|modeest|MRO 3.4.4 only|
|ModelMetrics|MRO 3.4.4 only|
|modeltools||  
|mombf||  
|monomvn||  
|monreg||  
|mosaic|CRAN R only|  
|mosaicCore|MRO 3.4.4 only|
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
|network|MRO 3.4.4 only|
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
|OceanView|MRO 3.4.4 only|
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
|pbapply|MRO 3.4.4 only|
|pbivnorm|| 
|pbkrtest|MRO 3.4.4 only|
|pcaPP||  
|pdc|MRO only|  
|PerformanceAnalytics||  
|permute||  
|pillar|MRO 3.4.4 only|
|pkgconfig|MRO 3.4.4 only|
|pkgmaker|MRO only|  
|pkgXMLBuilder|MRO only|  
|plogr|MRO 3.4.4 only|
|plot3D|MRO 3.4.4 only|
|plot3Drgl|MRO 3.4.4 only|
|plotly|MRO 3.4.4 only|
|plotmo||  
|plotrix||  
|pls||  
|plyr||  
|png||  
|polspline||  
|polynom||  
|PottsUtils||  
|prablclus|MRO 3.4.4 only|
|praise|MRO only|  
|predmixcor||  
|PresenceAbsence||  
|prettyunits|MRO 3.4.4 only|
|pROC||  
|prodlim||  
|profdpm||  
|profileModel||  
|progress|MRO 3.4.4 only|
|proto||  
|proxy|MRO only|  
|pryr||  
|pscl||  
|psych||  
|purr|MRO 3.4.4 only|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_Q"></a> Q  
  
|**Package name**|**Compatibility**|  
|-|-|  
|qap|MRO only|  
|qdap|MRO 3.4.4 only|
|qdapDictionaries||  
|qdapRegex||  
|qdapTools|CRAN R only|  
|quadprog||  
|quantmod||  
|quantreg|| 
|questionr|MRO 3.4.4 only|
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
|RcppRoll|MRO 3.4.4 only|
|RCurl||  
|readr|MRO only|  
|readxl|MRO 3.4.4 only|
|recipes|MRO 3.4.4 only|
|registry|MRO only|  
|relimp||  
|rematch|MRO 3.4.4 only|
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
|regx|MRO 3.4.4 only|
|rgl|MRO 3.4.4 only|
|RgoogleMaps||  
|RGraphics||  
|RGtk2||
|RINside|MRO only|  
|RJaCGH||  
|rjags|MRO 3.4.4 only|
|Rjava||
|rjson||  
|RJSONIO||  
|rlang|MRO 3.4.4 only|
|rlecuyer|MRO only|  
|Rmpfr|MRO only|  
|rms|MRO only|  
|RMySQL|MRO only|
|rngtools|MRO only|  
|robCompositions|CRAN R only| 
|robustbase||  
|ROCR||  
|RODBC||  
|Rook|MRO 3.4.4 only|
|rootSolve||  
|roxygen|CRAN R only|  
|roxygen2||  
|rpart||  
|rpart.plot||  
|rprojroot|MRO 3.4.4 only|
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
|RWekajars||
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
|shape|MRO 3.4.4 only|
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
|sourcetools|MRO 3.4.4 only|
|sp||  
|spacetime||  
|spam|MRO only|  
|SparseM||  
|spatial||  
|spBayes||
|spData|MRO 3.4.4 only|  
|spdep||  
|spikeslab||  
|splancs||  
|splines||  
|spls||  
|splus2R|MRO only|  
|spTimer||
|SQUAREM|MRO 3.4.4 only|
|sqldf||
|sROC|MRO only|  
|stabledist||  
|stabs|| 
|statnet.common|MRO 3.4.4 only|
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
|survey|MRO 3.4.4 only|
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
|tibble|MRO 3.4.4 only|
|tidyr|| 
|tidyselect|MRO 3.4.4 only|
|timeDate||  
|timeSeries||  
|tm||  
|tools||  
|topicmodels||  
|translations|MRO 3.4.4 only|
|tree||  
|trimcluster|MRO 3.4.4 only|
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
|utf8|MRO 3.4.4 only|
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
|viridis|MRO 3.4.4 only|
|viridisLite|MRO 3.4.4 only|
|visNetwork|MRO only|
  
 [List of supported packages](#bkmk_List)  
  
###  <a name="bkmk_W"></a> W  
  
|**Package name**|**Compatibility**|  
|-|-|  
|wavethresh|MRO 3.4.4 only|
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
|xml2|MRO 3.4.4 only|
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

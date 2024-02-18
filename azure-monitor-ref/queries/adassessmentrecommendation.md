---
title: Example log table queries for ADAssessmentRecommendation
description:  Example queries for ADAssessmentRecommendation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADAssessmentRecommendation table


### AD Recommendations by Focus Area  


Count all AD reccomendations by focus area.  

```query
ADAssessmentRecommendation 
| summarize AggregatedValue = count() by FocusArea  
```



### AD Recommendations by Computer  


Count AD recommendations with failed result by computer.  

```query
ADAssessmentRecommendation 
| where RecommendationResult == "Failed" 
| summarize AggregatedValue = count() by Computer
```



### AD Recommendations by Forest  


Count AD recommendations with failed result by forest.  

```query
ADAssessmentRecommendation 
| where RecommendationResult == "Failed" 
| summarize AggregatedValue = count() by Forest
```



### AD Recommendations by Domain  


Count AD recommendations with failed result by domain.  

```query
ADAssessmentRecommendation 
| where RecommendationResult == "Failed" 
| summarize AggregatedValue = count() by Domain
```



### AD Recommendations by DomainController  


Count AD recommendations with failed result by domain controller.  

```query
ADAssessmentRecommendation 
| where RecommendationResult == "Failed" 
| summarize AggregatedValue = count() by DomainController
```



### AD Recommendations by AffectedObjectType  


Count AD recommendations with failed result by affected object type.  

```query
ADAssessmentRecommendation 
| where RecommendationResult == "Failed" 
| summarize AggregatedValue = count() by AffectedObjectType
```



### How many times did each unique AD Recommendation trigger?  


Count AD recommendations with failed result by recommendation.  

```query
ADAssessmentRecommendation 
| where RecommendationResult == "Failed" 
| summarize AggregatedValue = count() by Recommendation
```



### High priority AD Assessment security recommendations  


Latest high priority security recommendation with result failed by recommendation Id.  

```query
ADAssessmentRecommendation
| where FocusArea == 'Security and Compliance' and RecommendationResult == 'Failed' and RecommendationScore>=35
| summarize arg_max(TimeGenerated, *) by RecommendationId
```


--- 
 
# required metadata 
title: "rxSetComputeContext function (RevoScaleR) " 
description: " Get or set the active compute context for RevoScaleR computations " 
keywords: "(RevoScaleR), rxSetComputeContext, rxGetComputeContext, IO" 
author: "heidisteen" 
manager: "jhubbard" 
ms.date: "09/07/2017" 
ms.topic: "reference" 
ms.prod: "microsoft-r" 
ms.service: "" 
ms.assetid: "" 
 
# optional metadata 
ROBOTS: "" 
audience: "" 
ms.devlang: "" 
ms.reviewer: "" 
ms.suite: "" 
ms.tgt_pltfrm: "" 
ms.technology: "r-server" 
ms.custom: "" 
 
--- 
 
 
 
 #rxSetComputeContext: Get and Set the compute context 
 ##Description
 
Get or set the active compute context for RevoScaleR computations
 
 
 ##Usage

```   
  
  rxSetComputeContext(computeContext, ...) 
               
  rxGetComputeContext() 
 
```
 
 ##Arguments

   
    
 ### `computeContext`
 character string specifying class name or description of the specific  class to instantiate, or an existing `RxComputeContext` object.  Choices include: `"RxLocalSeq"` or `"local"`, `"RxLocalParallel"` or `"localpar"`,  `"RxSpark"` or `"spark"`,  `"RxHadoopMR"` or `"hadoopmr"`,    and `"RxForeachDoPar"` or `"dopar"`. 
  
  
    
 ### ` ...`
 any other arguments are passed to the class generator determined from `computeContext`. 
  
 
 
 
 ##Value
 
`rxSetComputeContext` returns the previously active compute context invisibly.
`rxGetComputeContext` returns the active compute context.
 
 
 

 
 
 
 ##See Also
 
[RxComputeContext](RxComputeContext.md),
[rxOptions](rxOptions.md),
[rxGetOption](rxOptions.md)
[rxExec](rxExec.md).
   
 ##Examples

 ```
   
  ## Not run:
 
origComputeContext <- rxSetComputeContext("localpar")
x <- 1:10
rxExec(print, x, elemType = "cores", timesToRun = 10)
rxSetComputeContext( origComputeContext )
 ## End(Not run) 
  
  
 
```
 
 
 

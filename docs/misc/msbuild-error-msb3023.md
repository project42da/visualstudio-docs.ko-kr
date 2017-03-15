---
title: "MSBuild 오류 MSB3023 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.Copy.NeedsDestination"
helpviewer_keywords: 
  - "MSB3023"
ms.assetid: 3505ad1e-d54f-4cb4-a299-ac03684cb391
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3023
**Copy 작업의 대상을 지정하지 않았습니다.  "'\<attribute\>'" 또는 "'\<attribute\>'"을\(를\) 지정하십시오.**  
  
 `Copy` 작업의 대상은 작업 특성 `DestinationFiles` 및`DestinationDirectory` 중 하나를 사용하여 지정해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   `Copy` 작업에 대해 `DestinationFiles`또는`DestinationDirectory`를 지정합니다.  
  
## 참고 항목  
 [Copy Task](../msbuild/copy-task.md)   
 [작업](../msbuild/msbuild-tasks.md)
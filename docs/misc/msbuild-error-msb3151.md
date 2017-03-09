---
title: "MSBuild 오류 MSB3151 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.IncludedProductIncluded"
helpviewer_keywords: 
  - "MSB3151"
ms.assetid: e4766734-2e90-436e-850b-a8a9da535dee
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3151
**MSB3151: '\<package\>' 항목에 '\<package\>'이\(가\) 이미 포함되어 있습니다.**  
  
 이 경고는 부트스트래퍼 패키지 두 개를 선택했지만 패키지 하나가 다른 패키지에 포함된 경우 발생합니다. 예를 들어, 포함된 패키지는 중복하여 선택할 필요가 없습니다.  
  
### 이 오류를 해결하려면  
  
-   중복 포함된 패키지의 확인란을 선택 취소합니다.
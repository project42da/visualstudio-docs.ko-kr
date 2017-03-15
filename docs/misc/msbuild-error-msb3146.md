---
title: "MSBuild 오류 MSB3146 | Microsoft Docs"
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
  - "MSBuild.GenerateBootstrapper.MissingDependency"
helpviewer_keywords: 
  - "MSB3146"
ms.assetid: 717fd649-3024-427d-a068-cff8034ffc0a
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3146
**MSB3146: '\<package\>'에 필요한 '\<package\>' 항목이 포함되어 있지 않습니다.**  
  
 이 오류는 부트스트래퍼 패키지가 다른 패키지에 종속되어 있지만 종속된 패키지만 설치하도록 선택한 경우 발생합니다.  패키지 B가 패키지 A에 종속되어 있지만 패키지 B만 설치하는 경우를 예로 들 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   필요한 패키지를 포함합니다.
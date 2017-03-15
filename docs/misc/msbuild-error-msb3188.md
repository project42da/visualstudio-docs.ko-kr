---
title: "MSBuild 오류 MSB3188 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.PrerequisiteNotSigned"
helpviewer_keywords: 
  - "MSB3188"
ms.assetid: 8520e960-3b31-4e25-9fce-b9092b869bd0
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3188
**MSB3188: 어셈블리 '\<assembly\>'이\(가\) 필수 구성 요소로 표시되려면 강력하게 서명되어야 합니다.**  
  
 이 오류는 필수 구성 요소 어셈블리가 강력하게 서명되지 않은 경우 발생합니다.  이는 응용 프로그램 매니페스트에만 해당합니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트에 사용되는 모든 어셈블리가 강력하게 서명되었는지 확인합니다.
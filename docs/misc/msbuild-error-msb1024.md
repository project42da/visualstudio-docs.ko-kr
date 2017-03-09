---
title: "MSBuild 오류 MSB1024 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.MultipleSchemasError"
helpviewer_keywords: 
  - "MSB1024"
ms.assetid: dff30870-da1a-479f-998b-03d0f5e16088
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1024
**프로젝트의 유효성을 검사하는 데 사용할 스키마를 하나만 지정할 수 있습니다.**  
  
 **\/validate** 스위치에 하나의 스키마만 지정할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  `/validate:<schema>` 형식을 사용하여 프로젝트의 유효성 검사에 사용할 스키마를 하나만 지정합니다\(예: `/validate:MyExtendedBuildSchema.xsd`\).  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
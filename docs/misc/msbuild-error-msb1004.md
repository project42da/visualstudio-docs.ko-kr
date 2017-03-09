---
title: "MSBuild 오류 MSB1004 | Microsoft Docs"
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
  - "MSBuild.MissingTargetError"
helpviewer_keywords: 
  - "MSB1004"
ms.assetid: aed36761-ab07-486c-b5eb-48ccb1c387dd
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1004
**대상의 이름을 지정하십시오.**  
  
 **\/target** 스위치를 사용하여 대상을 적어도 한 개는 지정해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  대상을 지정합니다.  쉼표나 세미콜론을 사용하여 대상 목록을 구분하거나\(예: `/target:Clean;Compile`\),  스위치를 반복할 수도 있습니다\(예: `/t:Clean /t:` `Compile`\).  
  
## 참고 항목  
 [대상](../msbuild/msbuild-targets.md)   
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
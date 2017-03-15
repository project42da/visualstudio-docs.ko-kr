---
title: "MSBuild 오류 MSB1002 | Microsoft Docs"
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
  - "MSBuild.UnexpectedParametersError"
helpviewer_keywords: 
  - "MSB1002"
ms.assetid: 798c9690-6d99-4f21-a491-ab44d3f3c552
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1002
**이 스위치에는 매개 변수를 지정할 수 없습니다.**  
  
 이 스위치에 대해 매개 변수를 정의할 수 없습니다.  스위치의 이름만 지정해야 하며 뒤에 콜론이 나오지 않아야 합니다.  
  
### 이 오류를 해결하려면  
  
-   이 스위치에서는 매개 변수 없이 명령을 입력합니다. 즉, `msbuild /<switch>:<parameters>` 대신 `msbuild /<switch>`를 입력합니다.  
  
-   스위치 이름 뒤에 있는 콜론을 제거합니다. 즉, `msbuild /<switch>:` 대신 `msbuild /<switch>`를 입력합니다.  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
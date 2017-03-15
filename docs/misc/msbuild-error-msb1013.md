---
title: "MSBuild 오류 MSB1013 | Microsoft Docs"
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
  - "MSBuild.RepeatedResponseFileError"
helpviewer_keywords: 
  - "MSB1013"
ms.assetid: 3e85c710-99e6-4141-b058-63a144a06454
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1013
**지시 파일을 두 번 지정했습니다.  지시 파일은 한 번만 지정할 수 있습니다.**  
  
 여러 지시 파일에 대한 참조가 명령줄에 포함되어 있습니다.  `msbuild @response.rsp @response.rsp`와 같은 경우를 예로 들 수 있습니다.  
  
 이 오류는 원래 지시 파일에 대한 참조를 포함하고 있는 다른 지시 파일에 대한 참조가 지정된 지시 파일에 포함된 경우에도 발생할 수 있습니다.  컴파일할 때마다 지시 파일은 한 번만 지정할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   지시 파일에 대한 중복된 참조를 제거합니다.  예를 들어, `msbuild @response.rsp @response.rsp` 대신 `msbuild @response.rsp`를 사용합니다.  
  
-   원래 지시 파일이 참조하는 지시 파일에서 원래 지시 파일에 대한 참조를 제거합니다.  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
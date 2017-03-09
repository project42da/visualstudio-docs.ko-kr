---
title: "MSBuild 오류 MSB3072 | Microsoft Docs"
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
  - "MSBuild.Exec.MissingCommandError"
helpviewer_keywords: 
  - "MSB3072"
ms.assetid: c8468e1c-d8c7-441c-b274-123ac856f147
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3072
**"Exec" 작업에서 실행할 명령이 필요합니다.**  
  
 `Command` 특성은 `Exec` 작업의 필수 특성입니다.  
  
### 이 오류를 해결하려면  
  
1.  프로젝트 파일에서 `Exec` 작업에 대해 `Command` 특성을 지정합니다.  
  
## 참고 항목  
 [Exec Task](../msbuild/exec-task.md)   
 [작업](../msbuild/msbuild-tasks.md)
---
title: "MSBuild 오류 MSB1018 | Microsoft Docs"
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
  - "MSBuild.InvalidVerbosityError"
helpviewer_keywords: 
  - "MSB1018"
ms.assetid: fb4deacc-a799-44e8-8980-d70d9da4caa1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1018
**자세한 정도가 잘못되었습니다.**  
  
 지정된 자세한 정도가 사용 가능한 자세한 정도 중 하나가 아닙니다.  
  
### 이 오류를 해결하려면  
  
1.  자세한 정도의 철자를 확인합니다.  사용할 수 있는 자세한 정도는 q\[uiet\], m\[inimal\], n\[ormal\], d\[etailed\], diag\[nostic\] 등이 있습니다. 예를 들어, `/verbosity:quiet`, `/verbosity:q` 또는  `/v:q`입니다.  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)   
 [빌드 로거](../msbuild/build-loggers.md)
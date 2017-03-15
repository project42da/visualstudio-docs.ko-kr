---
title: "MSBuild 오류 MSB1016 | Microsoft Docs"
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
  - "MSBuild.MissingVerbosityError"
helpviewer_keywords: 
  - "MSB1016"
ms.assetid: 967a9757-0513-48ae-bf1d-b1b019993c70
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1016
**자세한 정도를 지정하십시오l.**  
  
 자세한 정도는 **\/verbosity** 스위치에 지정해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  `/verbosity:<level>` 형식을 사용하여 자세한 정도를 지정합니다.  사용할 수 있는 자세한 정도는 q\[uiet\], m\[inimal\], n\[ormal\], d\[etailed\], diag\[nostic\] 등이 있습니다. 예를 들어, `/verbosity:quiet`, `/verbosity:q` 또는  `/v:q`입니다.  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
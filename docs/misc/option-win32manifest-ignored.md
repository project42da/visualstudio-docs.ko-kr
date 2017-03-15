---
title: "/win32manifest 옵션이 무시됩니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc2034"
  - "bc2034"
helpviewer_keywords: 
  - "BC2034"
ms.assetid: 8009553a-f6ba-4d2b-8ddd-8a9357bc928e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /win32manifest 옵션이 무시됩니다.
\/win32manifest 옵션이 무시됩니다. 이 옵션은 대상이 어셈블리일 때만 지정할 수 있습니다.  
  
 `/target` 옵션이 `module`로 설정되었을 때 Visual Basic 컴파일러에 `/win32manifest` 컴파일러 옵션이 전달되었습니다.  
  
 **오류 ID:** BC2034  
  
### 이 오류를 해결하려면  
  
1.  `/win32manifest` 컴파일러 옵션을 제거하거나 `/target` 옵션을 `exe`, `winexe` 또는 `library`로 설정합니다.  
  
## 참고 항목  
 [\/target](/dotnet/visual-basic/reference/command-line-compiler/target)   
 [\/win32manifest](/dotnet/visual-basic/reference/command-line-compiler/win32manifest)   
 [Visual Basic Command\-Line Compiler](/dotnet/visual-basic/reference/command-line-compiler/index)
---
title: "Option Strict Custom은 명령줄 컴파일러(vbc.exe)에 대한 옵션으로만 사용할 수 있습니다. | Microsoft Docs"
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
  - "vbc31141"
  - "bc31141"
helpviewer_keywords: 
  - "BC31141"
ms.assetid: c32ae8ff-aacc-40b4-960a-6f2d5d246671
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Option Strict Custom은 명령줄 컴파일러(vbc.exe)에 대한 옵션으로만 사용할 수 있습니다.
`Option Strict` 문은 인수로 `On` 및 `Off`만 사용합니다. `Option Strict Custom`은 사용하지 않습니다.  
  
 `/optionstrict:custom` 컴파일러 옵션을 사용하여 엄격한 언어 의미 체계를 준수하지 않을 경우 경고합니다.  
  
 **오류 ID:** BC31141  
  
### 이 오류를 해결하려면  
  
1.  소스 코드에서 `Option Strict Custom`을 제거합니다.  
  
2.  `/optionstrict:custom` 옵션을 지정합니다. 자세한 내용은 [\/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict)을 참조하세요.  
  
## 참고 항목  
 [Option \<keyword\> Statement](../Topic/Option%20%3Ckeyword%3E%20Statement.md)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [\/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict)
---
title: "컴파일러 경고(수준 2) CS1927 | Microsoft Docs"
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
  - "CS1927"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1927"
ms.assetid: 32b4e58f-668c-4596-9529-7f3a293ff4ac
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS1927
\/win32manifest는 어셈블리에만 적용되므로 모듈의 경우 무시합니다.  
  
 win32 매니페스트는 어셈블리 수준에서만 적용됩니다. 모듈은 컴파일되지만 매니페스트가 포함되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  **\/win32manifest option**을 제거합니다.  
  
2.  코드를 어셈블리로 컴파일합니다.  
  
## 예제  
 **\/target:module** 및 **\/win32manifest** 컴파일러 옵션 둘 다로 컴파일할 경우 다음 예제에서는 CS1927을 생성합니다.  
  
```  
// cs1927.cs // Compile with: /target:module /win32manifest using System; class ManifestWithModule { static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [\/win32manifest \(Import a Custom Win32 Manifest File\)](/dotnet/csharp/language-reference/compiler-options/win32manifest-compiler-option)   
 [\/target:module \(Create Module to Add to Assembly\)](../Topic/-target:module%20\(C%23%20Compiler%20Options\).md)
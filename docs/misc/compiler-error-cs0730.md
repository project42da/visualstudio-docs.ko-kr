---
title: "컴파일러 오류 CS0730 | Microsoft Docs"
ms.custom: ""
ms.date: "10/01/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0730"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0730"
ms.assetid: bf291285-dc1e-4c8d-a449-119004adc088
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0730
'type' 형식은 'type'의 중첩 형식이므로 전달할 수 없습니다.  
  
 이 오류는 중첩된 클래스를 전달하려고 할 때 발생합니다.  
  
## 예제  
 다음 샘플에서는 CS0730을 생성합니다. 이는 두 개의 원본 파일로 구성됩니다. 먼저, `CS0730a.cs` 라이브러리 파일을 컴파일하고, 해당 라이브러리 파일을 참조하는 `CS0730.cs` 파일을 컴파일합니다.  
  
```  
// CS0730a.cs // compile with: /t:library public class Outer { public class Nested {} }  
```  
  
```  
// CS0730.cs // compile with: /t:library /r:CS0730a.dll using System.Runtime.CompilerServices; [assembly:TypeForwardedToAttribute(typeof(Outer.Nested))]   // CS0730 [assembly:TypeForwardedToAttribute(typeof(Outer))]   // OK  
```
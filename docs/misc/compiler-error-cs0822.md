---
title: "컴파일러 오류 CS0822 | Microsoft Docs"
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
  - "CS0822"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0822"
ms.assetid: 519091be-2332-4df4-acd9-e3b633966b3d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0822
암시적 형식 지역 변수는 const일 수 없습니다.  
  
 암시적 형식 지역 변수는 무명 형식을 저장하는 경우에만 필요합니다. 다른 모든 경우에는 편의를 위해서만 제공됩니다. 변수 값이 변경되지 않는 경우 명시적 형식을 지정합니다.`readonly` 한정자를 암시적 형식 지역 변수와 함께 사용하려고 하면 CS0106이 생성됩니다.  
  
### 이 오류를 해결하려면  
  
1.  상수 또는 `readonly`인 변수가 필요한 경우 명시적 형식을 지정합니다.  
  
## 예제  
 다음 코드에서는 CS0822를 생성합니다.  
  
```  
// cs0822.cs class A { public static int Main() { const var x = 0; // CS0822.cs return -1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)
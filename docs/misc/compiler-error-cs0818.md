---
title: "컴파일러 오류 CS0818 | Microsoft Docs"
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
  - "CS0818"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0818"
ms.assetid: e4941018-a10a-4636-98ea-aade29e45728
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0818
암시적 형식 지역 변수는 초기화해야 합니다.  
  
 암시적 형식 지역 변수는 선언과 동시에 값으로 초기화되어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  변수에 값을 할당하거나 명시적 형식을 제공합니다.  
  
## 예제  
 다음 코드에서는 CS0818을 생성합니다.  
  
```  
// cs0818.cs class A { public static int Main() { var a; // CS0818 return -1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)
---
title: "컴파일러 오류 CS0819 | Microsoft Docs"
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
  - "CS0819"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0819"
ms.assetid: a5369e03-eb7d-4c88-b390-51304bd8d1ae
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0819
암시적 형식 지역 변수에는 선언자를 여러 개 사용할 수 없습니다.  
  
 명시적 형식 선언에서는 선언자를 여러 개 사용할 수 있지만 암시적으로 형식화된 변수에는 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  암시적 형식 지역 변수에 대한 값을 각각 별도의 줄에서 선언 및 할당합니다.  
  
## 예제  
 다음 코드에서는 CS0819를 생성합니다.  
  
```  
// cs0819.cs class A { public static int Main() { var a = 3, b = 2; // CS0819 return -1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)
---
title: "컴파일러 오류 CS0815 | Microsoft Docs"
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
  - "CS0815"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0815"
ms.assetid: 8f055d34-9ee4-482e-9e79-8b3698c55cb4
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0815
암시적 형식 지역 변수에는 'expression'을 할당할 수 없습니다.  
  
 암시적으로 형식화된 변수에 대한 이니셜라이저로 사용되는 식에는 형식이 있어야 합니다. 익명 함수 식, 메서드 그룹 식 및 null 리터럴 식에는 형식이 없으므로 적절한 이니셜라이저가 아닙니다. 나중에 null 값을 지정할 수는 있어도 해당 선언에서 암시적으로 형식화된 변수를 null 값으로 초기화할 수는 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  변수에 대한 명시적 형식을 제공합니다.  
  
## 예제  
 다음 코드에서는 CS0815를 생성합니다.  
  
```  
// cs0815.cs class Test { public static int Main() { var d = s => -1; // CS0815 var e = (string s) => 0; // CS0815 var p = null;//CS0815 var del = delegate(string a) { return -1; };// CS0815 return -1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)
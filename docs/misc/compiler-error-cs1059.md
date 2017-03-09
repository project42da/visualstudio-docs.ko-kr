---
title: "컴파일러 오류 CS1059 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1059"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1059"
ms.assetid: 3ebd02ab-e40d-4aad-b901-a0cb6e2eace7
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1059
증가 연산자 또는 감소 연산자의 피연산자는 변수, 속성 또는 인덱서여야 합니다.  
  
 이 오류는 상수 값을 증가하거나 감소하려고 할 때 발생합니다.`(a+b)++` 등의 식을 증가하려고 하는 경우에도 발생할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   변수를 const가 아니도록 설정합니다.  
  
-   증가 또는 감소 연산자를 제거합니다.  
  
-   식을 변수에 저장하고 변수를 증가합니다.  
  
## 예제  
 다음 예제에서는 `i`가 변수가 아니라 상수이고 `E`가 해당 요소도 상수 값인 `Enum` 형식이기 때문에 CS1059를 생성합니다.  
  
```  
// CS1059.cs class Program { public enum E : sbyte { a = 1, b = 2 } static void Main(string[] args) { const int i = 0; i++;            // CS1059 E test = E.a++; // CS1059 } }  
```  
  
## 참고 항목  
 [상수](/dotnet/csharp/programming-guide/classes-and-structs/constants)
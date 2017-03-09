---
title: "컴파일러 오류 CS0131 | Microsoft Docs"
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
  - "CS0131"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0131"
ms.assetid: 822852cc-a426-4b7d-b2ff-0026a0c0a0e7
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0131
할당식의 왼쪽은 변수, 속성 또는 인덱서여야 합니다.  
  
 대입문에서 오른쪽의 값이 왼쪽에 할당됩니다. 왼쪽은 변수, 속성 또는 인덱서여야 합니다.  
  
 이 오류를 해결하려면 모든 연산자가 오른쪽에 있고 변수, 속성 또는 인덱서가 왼쪽에 있는지 확인합니다. 자세한 내용은 [문, 식, 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/index)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0131을 생성합니다.  
  
```  
// CS0131.cs public class MyClass { public int i = 0; public void MyMethod() { i++ = 1;   // CS0131 // try the following line instead // i = 1; } public static void Main() { } }  
```  
  
## 예제  
 다음 예제와 같이 대입 연산자의 왼쪽에서 산술 연산을 수행하려는 경우에도 이 오류가 발생할 수 있습니다.  
  
```  
// CS0131b.cs public class C { public static int Main() { int a = 1, b = 2, c = 3; if (a + b = c) // CS0131 // try this instead // if (a + b == c) return 0; return 1; } }  
```
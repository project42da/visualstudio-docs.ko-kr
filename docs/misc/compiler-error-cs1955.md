---
title: "컴파일러 오류 CS1955 | Microsoft Docs"
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
  - "CS1955"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1955"
ms.assetid: 38a8542d-da53-4739-b807-46c8c077363c
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1955
호출할 수 없는 멤버인 'name'은 메서드처럼 사용할 수 없습니다.  
  
 메서드 및 대리자만 호출할 수 있습니다. 이 오류는 빈 괄호를 사용하여 메서드 또는 대리자 이외의 항목을 호출하려는 경우에 생성됩니다.  
  
### 이 오류를 해결하려면  
  
1.  식에서 괄호를 제거합니다.  
  
## 예제  
 다음 코드에서는 메서드 호출 연산자 [\(\)](/dotnet/csharp/language-reference/operators/invocation-operator)를 사용하여 필드 및 속성을 호출하려고 하기 때문에 CS1955를 생성합니다. 필드 또는 속성을 호출할 수는 없지만 멤버 액세스 연산자\([.](/dotnet/csharp/language-reference/operators/member-access-operator)\)를 사용하여 저장하는 값에 액세스할 수 있습니다.  
  
```  
// cs1955.cs class A { public int x = 0; public int X { get { return x; } set { x = value; } } } class Test { static int Main() { A a = new A(); a.x(); // CS1955 a.X(); // CS1955 // Try this line instead: // int num = a.x; } }  
```
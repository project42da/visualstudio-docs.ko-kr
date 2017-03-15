---
title: "컴파일러 오류 CS0736 | Microsoft Docs"
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
  - "CS0736"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0736"
ms.assetid: 06b14feb-81d5-495f-ab2d-6dc3f5e7216f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0736
'type name'은 'member name' 인터페이스 멤버를 구현하지 않습니다. 'method name'은\(는\) static이므로 인터페이스 멤버를 구현할 수 없습니다.  
  
 이 오류는 정적 메서드가 인터페이스 멤버 구현으로 암시적 또는 명시적으로 선언된 경우에 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   메서드 선언에서 [static](/dotnet/csharp/language-reference/keywords/static) 한정자를 제거합니다.  
  
-   인터페이스 메서드의 이름을 변경합니다.  
  
-   인터페이스에서 상속하지 않도록 포함하는 형식을 다시 정의합니다.  
  
## 예제  
 `Program.testMethod`가 static으로 선언되었기 때문에 다음 코드에서는 CS0736을 생성합니다.  
  
```  
// cs0736.cs namespace CS0736 { interface ITest { int testMethod(int x); } class Program : ITest // CS0736 { public static int testMethod(int x) { return 0; } // Try the following line instead. // public int testMethod(int x) { return 0; } public static void Main() { } } }  
```  
  
## 참고 항목  
 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)
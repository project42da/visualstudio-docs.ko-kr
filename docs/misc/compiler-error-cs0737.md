---
title: "컴파일러 오류 CS0737 | Microsoft Docs"
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
  - "CS0737"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0737"
ms.assetid: d2247770-5546-46f2-a01d-8e2ebfcbb859
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0737
'type name'은 'member name' 인터페이스 멤버를 구현하지 않습니다. 'method name'은\(는\) public이 아니므로 인터페이스 멤버를 구현할 수 없습니다.  
  
 인터페이스 멤버를 구현하는 메서드에는 public 접근성이 있어야 합니다. 모든 인터페이스 멤버는 `public`입니다.  
  
### 이 오류를 해결하려면  
  
1.  [public](/dotnet/csharp/language-reference/keywords/public) 액세스 한정자를 메서드에 추가합니다.  
  
## 예제  
 다음 코드에서는 CS0737을 생성합니다.  
  
```  
// cs0737.cs interface ITest { // Default access of private with no modifier. int Return42(); // Try the following line instead. // public int Return42(); } struct Struct1 : ITest // CS0737 { int Return42() { return (42); } } public class Test { public static int Main(string[] args) { Struct1 s1 = new Struct1(); return (1); } }  
```  
  
## 참고 항목  
 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index)
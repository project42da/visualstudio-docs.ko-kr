---
title: "컴파일러 오류 CS0562 | Microsoft Docs"
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
  - "CS0562"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0562"
ms.assetid: dceecce5-90ce-4554-820c-f4c06b2b8258
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0562
단항 연산자의 매개 변수는 포함하는 형식이어야 합니다.  
  
 연산자 오버로드에 대한 메서드 선언은 다음의 특정 지침을 따라야 합니다. 자세한 내용은 [오버로드할 수 있는 연산자](/dotnet/csharp/programming-guide/statements-expressions-operators/overloadable-operators) 및 [Operator Overloading Sample](http://msdn.microsoft.com/ko-kr/1c6b4610-0a49-4532-8fa7-f694cfc65743)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0562를 생성합니다.  
  
```  
// CS0562.cs public class iii { public static implicit operator int(iii x) { return 0; } public static implicit operator iii(int x) { return null; } public static iii operator +(int aa)   // CS0562 // try the following line instead // public static iii operator +(iii aa) { return (iii)0; } public static void Main() { } }  
```
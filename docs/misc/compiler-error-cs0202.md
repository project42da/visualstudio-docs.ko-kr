---
title: "컴파일러 오류 CS0202 | Microsoft Docs"
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
  - "CS0202"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0202"
ms.assetid: 7088850f-c206-4b95-9586-a0fa3d876c0c
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0202
foreach의 반환 형식 'type'\('type.GetEnumerator\(\)'\)에는 적절한 공용 MoveNext 메서드 및 공용 Current 속성이 있어야 합니다.  
  
 foreach 문을 사용할 수 있도록 하는 데 사용되는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 함수는 포인터 또는 배열을 반환할 수 없습니다. 열거자 역할을 할 수 있는 클래스의 인스턴스를 반환해야 합니다. 열거자 역할을 하기 위한 요구 사항에는 공용 Current 속성 및 공용 MoveNext 메서드가 포함됩니다.  
  
> [!NOTE]
>  C\# 2.0에서는 컴파일러가 Current 및 MoveNext를 자동으로 생성합니다. 자세한 내용은 [제네릭 인터페이스](/dotnet/csharp/programming-guide/generics/generic-interfaces)의 코드 예제를 참조하세요.  
  
 다음 샘플에서는 CS0202를 생성합니다.  
  
```  
// CS0202.cs public class C1 { public int Current { get { return 0; } } public bool MoveNext () { return false; } public static implicit operator C1 (int c1) { return 0; } } public class C2 { public int Current { get { return 0; } } public bool MoveNext () { return false; } public C1[] GetEnumerator () // try the following line instead // public C1 GetEnumerator () { return null; } } public class MainClass { public static void Main () { C2 c2 = new C2(); foreach (C1 x in c2)   // CS0202 { System.Console.WriteLine(x.Current); } } }  
```
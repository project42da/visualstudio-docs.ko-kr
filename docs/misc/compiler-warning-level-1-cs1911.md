---
title: "컴파일러 경고(수준 1) CS1911 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1911"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1911"
ms.assetid: 95e8a7a0-1c19-4930-a7e9-3ae4060e97d3
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1911
무명 메서드, 람다 식, 쿼리 식 또는 반복기에서 'base' 키워드를 통해 'name' 멤버에 액세스하면 확인할 수 없는 코드가 만들어집니다. 포함하는 형식의 도우미 메서드로 액세스를 이동하는 것이 좋습니다.  
  
 반복기 또는 무명 메서드의 메서드 본문 내에서 `base` 키워드를 사용하여 가상 함수를 호출하면 확인할 수 없는 코드가 만들어집니다. 확인할 수 없는 코드는 부분 신뢰 환경에서 실행되지 못합니다.  
  
 CS1911에 대한 하나의 해결책은 가상 함수 호출을 도우미 함수로 옮기는 것입니다.  
  
## 예제  
 다음 샘플에서는 CS1911을 생성합니다.  
  
```  
// CS1911.cs // compile with: /W:1 using System; delegate void D(); delegate D RetD(); class B { protected virtual void M() { Console.WriteLine("B.M"); } } class Der : B { protected override void M() { Console.WriteLine("D.M"); } void Test() { base.M(); } D Test2() { return new D(base.M); } public D CallBaseM() { return delegate () { base.M(); };   // CS1911 // try the following line instead // return delegate () { Test(); }; } public RetD DelToBaseM() { return delegate () { return new D(base.M); };   // CS1911 // try the following line instead // return delegate () { return Test2(); }; } } class Program { public static void Main() { Der der = new Der(); D d = der.CallBaseM(); d(); RetD rd = der.DelToBaseM(); rd()(); } }  
```
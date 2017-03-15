---
title: "컴파일러 오류 CS0447 | Microsoft Docs"
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
  - "CS0447"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0447"
ms.assetid: a25486c5-e9bf-4528-8533-c1aaab22ace0
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0447
특성은 형식 인수에 사용할 수 없고 형식 매개 변수에만 사용할 수 있습니다.  
  
 이 오류는 호출 문에서 사용된 형식 인수에 특성을 적용하는 경우에 발생합니다. 다음과 같은 클래스 또는 메서드 선언문의 형식 매개 변수에 특성을 적용할 수 있습니다.  
  
```  
class C<[some attribute] T> {…}  
```  
  
 다음 코드 줄에서 이 오류가 발생합니다. 이전 코드 줄에서 정의된 `C` 클래스에 `MyStaticMethod`라는 정적 메서드가 있다고 가정합니다.  
  
```  
C<[some attribute] T>.MyStaticMethod();  
```  
  
## 예제  
 다음 코드에서는 CS0447 오류를 생성합니다.  
  
```  
// CS0447.cs using System; namespace Test41 { public interface I<A> { void Meth<B>(); } public class B : I<int> { void I<[Test] int>.Meth<X>() { }  // CS0447 } }  
```
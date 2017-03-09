---
title: "컴파일러 오류 CS0540 | Microsoft Docs"
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
  - "CS0540"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0540"
ms.assetid: 2da2cd4a-0ff1-45ea-bb72-ea078bc95dea
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0540
'interface member': 포함하는 형식이 'interface' 인터페이스를 구현하지 않습니다.  
  
 [인터페이스](/dotnet/csharp/language-reference/keywords/interface)에서 파생되지 않는 [클래스](/dotnet/csharp/language-reference/keywords/class)에 인터페이스 멤버를 구현하려고 했습니다. 인터페이스 멤버의 구현을 삭제하거나 클래스의 기본 클래스 목록에 인터페이스를 추가해야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0540을 생성합니다.  
  
```  
// CS0540.cs interface I { void m(); } public class Clx { void I.m() {}   // CS0540 } // OK public class Cly : I { void I.m() {} public static void Main() {} }  
```  
  
## 예제  
 다음 샘플에서는 CS0540을 생성합니다.  
  
```  
// CS0540_b.cs using System; class C { void IDisposable.Dispose() {}   // CS0540 } class D : IDisposable { void IDisposable.Dispose() {} public void Dispose() {} static void Main() { using (D d = new D()) {} } }  
```
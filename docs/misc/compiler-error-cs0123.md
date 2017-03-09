---
title: "컴파일러 오류 CS0123 | Microsoft Docs"
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
  - "CS0123"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0123"
ms.assetid: 57be2c58-6d87-40af-9376-cd7f91023044
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0123
'delegate' 대리자와 일치하는 'method'에 대한 오버로드가 없습니다.  
  
 올바른 서명을 사용하지 않아 대리자를 만들려는 시도가 실패했습니다. 대리자 선언과 동일한 서명을 사용하여 대리자의 인스턴스를 선언해야 합니다.  
  
 이 오류를 해결하려면 메서드 또는 대리자 서명을 조정합니다. 자세한 내용은 [대리자](/dotnet/csharp/programming-guide/delegates/index)을 참조하세요.  
  
 다음 샘플에서는 CS0123을 생성합니다.  
  
```  
// CS0123.cs delegate void D(); delegate void D2(int i); public class C { public static void f(int i) {} public static void Main() { D d = new D(f);   // CS0123 D2 d2 = new D2(f);   // OK } }  
```
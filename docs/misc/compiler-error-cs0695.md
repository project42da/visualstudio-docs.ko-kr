---
title: "컴파일러 오류 CS0695 | Microsoft Docs"
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
  - "CS0695"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0695"
ms.assetid: 05f6c8cf-6147-4ac7-84ea-e1f34f8ef9f7
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0695
'generic interface'와 'generic interface'는 일부 형식 매개 변수를 대체할 때 통합될 수 있으므로 'generic type'에서 둘 다 구현할 수는 없습니다.  
  
 이 오류는 제네릭 클래스가 동일한 제네릭 인터페이스의 매개 변수화를 둘 이상 구현하며, 두 인터페이스를 동일하게 만드는 형식 매개 변수 대체가 있는 경우에 발생합니다. 이 오류를 방지하려면 인터페이스 중 하나만 구현하거나 충돌하지 않도록 형식 매개 변수를 변경합니다.  
  
 다음 샘플에서는 CS0695를 생성합니다.  
  
```  
// CS0695.cs // compile with: /target:library interface I<T> { } class G<T1, T2> : I<T1>, I<T2>  // CS0695 { }  
```
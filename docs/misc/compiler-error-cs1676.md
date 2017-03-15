---
title: "컴파일러 오류 CS1676 | Microsoft Docs"
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
  - "CS1676"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1676"
ms.assetid: 5ac83d98-5baa-49fd-b76a-d8ef0865b9dd
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1676
'number' 매개 변수는 'keyword' 키워드를 사용하여 선언해야 합니다.  
  
 이 오류는 무명 메서드의 매개 변수 형식 한정자가 메서드를 캐스팅하는 대리자의 선언에서 사용되는 것과 다른 경우 발생합니다.  
  
 다음 샘플에서는 CS1676을 생성합니다.  
  
```  
// CS1676.cs delegate void E(ref int i); class Errors { static void Main() { E e = delegate(out int i) { };   // CS1676 // To resolve, use the following line instead: // E e = delegate(ref int i) { }; } }  
```
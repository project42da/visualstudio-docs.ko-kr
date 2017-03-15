---
title: "컴파일러 오류 CS1615 | Microsoft Docs"
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
  - "CS1615"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1615"
ms.assetid: 518bb07f-0e3a-4761-9931-66845eb5df1a
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1615
'number' 인수는 'keyword' 키워드와 함께 전달할 수 없습니다.  
  
 함수에서 해당 인수에 대해 `ref` 또는 **out** 매개 변수를 사용하지 않는데 `ref` 또는 **out** 키워드 중 하나가 사용되었습니다. 이 오류를 해결하려면 잘못된 키워드를 제거하고 함수 선언에 맞는 적절한 키워드\(있는 경우\)를 사용합니다.  
  
 다음 샘플에서는 CS1615를 생성합니다.  
  
```  
// CS1615.cs class C { public void f(int i) {} public static void Main() { int i = 1; f(ref i);  // CS1615 } }  
```
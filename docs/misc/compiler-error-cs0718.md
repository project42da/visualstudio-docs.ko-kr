---
title: "컴파일러 오류 CS0718 | Microsoft Docs"
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
  - "CS0718"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0718"
ms.assetid: f18ea7b7-7495-4039-9876-409e9fe98ba1
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0718
'type': 정적 형식은 형식 인수로 사용할 수 없습니다.  
  
 정적 형식은 인스턴스화할 수 없기 때문에 제네릭 인수로 사용할 수 없습니다. 이 오류를 해결하려면 정적 형식을 제네릭 인수에서 제거합니다.  
  
## 예제  
 다음 샘플에서는 CS0718을 생성합니다.  
  
```  
// CS0718.cs public static class SC { public static void F() { } } public class G<T> { } public class CMain { public static void Main() { G<SC> gsc = new G<SC>();  // CS0718 } }  
```
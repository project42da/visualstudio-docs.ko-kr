---
title: "컴파일러 오류 CS0699 | Microsoft Docs"
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
  - "CS0699"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0699"
ms.assetid: 1dff310b-6b8d-46b4-a649-bbf23282ff1f
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0699
'generic'이 'identifier' 형식 매개 변수를 정의하지 않습니다.  
  
 형식 매개 변수가 해당 제네릭에 대한 형식 매개 변수의 선언 목록에 없는 제네릭 선언에서 사용되었습니다. 이는 형식 매개 변수가 사용되는 이름이 일관되지 않은 경우 발생할 수 있습니다.  
  
 다음 샘플에서는 CS0699를 생성합니다.  
  
```  
// CS0699.cs class C<T> where U : I   // CS0699 – U is not a valid type parameter { }  
```
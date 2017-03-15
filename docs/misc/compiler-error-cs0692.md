---
title: "컴파일러 오류 CS0692 | Microsoft Docs"
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
  - "CS0692"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0692"
ms.assetid: d2fd650b-1f84-44b1-8c7e-471cad92a85e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0692
'identifier' 형식 매개 변수가 중복되었습니다.  
  
 동일한 이름을 형식 매개 변수 목록에 두 번 이상 사용할 수 없습니다. 중복된 형식 매개 변수의 이름을 바꾸거나 제거합니다.  
  
## 예제  
 다음 샘플에서는 CS0692를 생성합니다.  
  
```  
// CS0692.cs // compile with: /target:library class C <T, A, T>   // CS0692 { } class D <T, T>   // CS0692 { }  
```
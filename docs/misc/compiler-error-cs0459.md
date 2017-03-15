---
title: "컴파일러 오류 CS0459 | Microsoft Docs"
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
  - "CS0459"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0459"
ms.assetid: 01b058dd-8d65-4e9d-9de1-d47f9488d22a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0459
읽기 전용 지역 변수의 주소를 가져올 수 없습니다.  
  
 읽기 전용 지역 변수를 생성하는 C\# 언어의 세 가지 일반적인 시나리오는 `foreach`, `using` 및 `fixed`입니다. 각각의 경우에서 읽기 전용 지역 변수에 쓰거나 해당 주소를 가져올 수 없습니다. 이 오류는 컴파일러가 읽기 전용 지역 변수의 주소를 가져오려는 것을 확인할 때 발생합니다.  
  
## 예제  
 다음 예제에서는 `foreach` 루프 및 `fixed` 문 블록에서 읽기 전용 지역 변수의 주소를 가져오려고 할 때 CS0459를 생성합니다.  
  
```  
// CS0459.cs // compile with: /unsafe class A { public unsafe void M1() { int[] ints = new int[] { 1, 2, 3 }; foreach (int i in ints) { int *j = &i;  // CS0459 } fixed (int *i = &_i) { int **j = &i;  // CS0459 } } private int _i = 0; }  
```
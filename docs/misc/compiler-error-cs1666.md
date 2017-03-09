---
title: "컴파일러 오류 CS1666 | Microsoft Docs"
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
  - "CS1666"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1666"
ms.assetid: 4d62aa9c-71b9-4c6e-8141-2426d20ac243
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1666
고정되지 않은 식에 포함된 고정 크기 버퍼는 사용할 수 없습니다. fixed 문을 사용하세요.  
  
 이 오류는 그 자체가 고정되지 않은 클래스를 포함하는 식에서 고정 크기 버퍼를 사용하는 경우에 발생합니다. 고정되지 않은 클래스는 런타임에 메모리 액세스를 최적화하기 위해 자유롭게 이동될 수 있으므로 고정 크기 버퍼를 사용하는 경우 오류가 발생할 수 있습니다. 이 오류를 방지하려면 문에서 `fixed` 키워드를 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS1666을 생성합니다.  
  
```  
// CS1666.cs // compile with: /unsafe /target:library unsafe struct S { public fixed int buffer[1]; } unsafe class Test { S field = new S(); private bool example1() { return (field.buffer[0] == 0);   // CS1666 error } private bool example2() { // OK fixed (S* p = &field) { return (p->buffer[0] == 0); } } private bool example3() { S local = new S(); return (local.buffer[0] == 0); } }  
```
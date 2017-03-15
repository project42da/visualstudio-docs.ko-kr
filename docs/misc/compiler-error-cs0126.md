---
title: "컴파일러 오류 CS0126 | Microsoft Docs"
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
  - "CS0126"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0126"
ms.assetid: 15fb0f38-ac9d-4c09-a69f-398a4903d790
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0126
'type'으로 변환할 수 있는 형식의 개체가 필요합니다.  
  
 return 문이 있지만 문에서 예상되는 형식의 값을 반환하지 않습니다. 자세한 내용은 [속성](/dotnet/csharp/programming-guide/classes-and-structs/properties)을 참조하세요.  
  
 다음 샘플에서는 CS0126을 생성합니다.  
  
```  
// CS0126.cs public class a { public int i { set { } get { return;   // CS0126, specify a value to return } } }  
```
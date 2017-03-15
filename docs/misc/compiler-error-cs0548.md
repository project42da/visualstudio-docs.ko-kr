---
title: "컴파일러 오류 CS0548 | Microsoft Docs"
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
  - "CS0548"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0548"
ms.assetid: c4d34da7-0b4a-4312-ac7f-46db100e43c7
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0548
'property': 속성이나 인덱서에는 적어도 하나의 접근자가 있어야 합니다.  
  
 속성에는 적어도 하나의 접근자\(get 또는 set\) 메서드가 있어야 합니다.  
  
 자세한 내용은 [속성 사용](/dotnet/csharp/programming-guide/classes-and-structs/using-properties)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0548을 생성합니다.  
  
```  
// CS0548.cs // compile with: /target:library public class b { public int MyProp {}   // CS0548 public int MyProp2   // OK { get { return 0; } set {} } }  
```
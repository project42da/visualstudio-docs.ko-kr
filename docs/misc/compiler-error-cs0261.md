---
title: "컴파일러 오류 CS0261 | Microsoft Docs"
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
  - "CS0261"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0261"
ms.assetid: c2af7b31-4a48-457a-8d9b-0956dd0d46f9
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0261
'type'의 partial 선언은 모두 클래스, 구조체 또는 인터페이스여야 합니다.  
  
 이 오류는 부분 형식\(Partial Type\)이 다양한 위치에서 다른 구문 형식으로 선언되는 경우 발생합니다. 자세한 내용은 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)을 참조하세요.  
  
 다음 샘플에서는 CS0261을 생성합니다.  
  
```  
// CS0261.cs partial class A  // CS0261 – A declared as a class here, but as a struct below { } partial struct A { }  
```
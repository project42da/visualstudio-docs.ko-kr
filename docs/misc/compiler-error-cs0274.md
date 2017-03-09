---
title: "컴파일러 오류 CS0274 | Microsoft Docs"
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
  - "CS0274"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0274"
ms.assetid: bbd2d64e-a756-4713-b9ed-711d50b65e00
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0274
'property\/indexer' 속성 또는 인덱서의 두 접근자에 대해 접근성 한정자를 지정할 수 없습니다.  
  
 이 오류는 접근자 둘 다에서 액세스 한정자를 사용하는 속성 또는 인덱서를 선언하는 경우에 발생합니다. 이 오류를 해결하려면 두 접근자 중 하나에서만 액세스 한정자를 사용합니다. 자세한 내용은 [접근자 접근성](/dotnet/csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility)을 참조하세요.  
  
 다음 예제에서는 CS0274를 생성합니다.  
  
```  
// CS0274.cs public class MyClass { public int Property   // CS0274 { public get { return 0; } protected set { } } }  
```
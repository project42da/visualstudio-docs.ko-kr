---
title: "컴파일러 오류 CS0061 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0061"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0061"
ms.assetid: 8dfc57a9-653d-4902-a88c-92032ba64024
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0061
일관성 없는 접근성: 'interface 1' 기본 인터페이스가 'interface 2' 인터페이스보다 액세스하기 어렵습니다.  
  
 [공용](/dotnet/csharp/language-reference/keywords/public) 구문은 공개적으로 액세스 가능한 개체를 반환해야 합니다.  
  
 파생된 인터페이스에서는 인터페이스 접근성을 축소할 수 없습니다. 자세한 내용은 [인터페이스](/dotnet/csharp/programming-guide/interfaces/index) 및 [액세스 한정자](/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)를 참조하세요.  
  
 다음 샘플에서는 CS0061을 생성합니다.  
  
```  
// CS0061.cs // compile with: /target:library internal interface A {} public interface AA : A {}  // CS0061 // OK public interface B {} internal interface BB : B {} internal interface C {} internal interface CC : C {}  
```
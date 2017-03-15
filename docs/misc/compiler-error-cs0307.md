---
title: "컴파일러 오류 CS0307 | Microsoft Docs"
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
  - "CS0307"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0307"
ms.assetid: 202a9985-ed7a-4e0a-9573-5624e066d314
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0307
'construct' 'identifier'는 제네릭 메서드가 아닙니다. 식 목록을 사용하려면 \< 식 주위에 괄호를 사용하세요.  
  
 이름이 지정된 구문이 형식 또는 메서드가 아니라 제네릭 인수를 사용할 수 있는 유일한 구문입니다. 꺾쇠 괄호에서 형식 인수를 제거합니다. 제네릭이 필요한 경우 제네릭 구문을 제네릭 형식 또는 메서드로 선언합니다.  
  
 다음 샘플에서는 CS0307을 생성합니다.  
  
```  
// CS0307.cs class C { public int P { get { return 1; } } public static void Main() { C c = new C(); int p = c.P<int>();  // CS0307 – C.P is a property // Try this instead // int p = c.P; } }  
```
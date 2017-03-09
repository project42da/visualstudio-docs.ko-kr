---
title: "컴파일러 오류 CS0275 | Microsoft Docs"
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
  - "CS0275"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0275"
ms.assetid: 4d59f11c-b0ea-4c91-b2cb-cbe3be9a9ba2
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0275
'accessor': 접근성 한정자는 인터페이스의 접근자에 사용할 수 없습니다.  
  
 이 오류는 인터페이스의 속성 또는 인덱서 접근자 중 하나에서 액세스 한정자를 사용하는 경우에 발생합니다. 해결하려면 액세스 한정자를 제거합니다.  
  
## 예제  
 다음 예제에서는 CS0275를 생성합니다.  
  
```  
// CS0275.cs public interface MyInterface { int Property { get; internal set;   // CS0275 } }  
```
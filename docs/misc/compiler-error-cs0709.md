---
title: "컴파일러 오류 CS0709 | Microsoft Docs"
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
  - "CS0709"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0709"
ms.assetid: 91040f55-a060-4cc3-b830-f6b771af28d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0709
'derived class': 정적 클래스 'base class'에서 파생될 수 없습니다.  
  
 정적 클래스는 인스턴스화되거나 파생될 수 없습니다. 즉, 정적 클래스는 다른 클래스의 기본 클래스가 될 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0709를 생성합니다.  
  
```  
// CS0709.cs // compile with: /target:library public static class Base {} public class Derived : Base {}   // CS0709  
```
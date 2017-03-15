---
title: "컴파일러 경고(수준 1) CS3000 | Microsoft Docs"
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
  - "CS3000"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3000"
ms.assetid: 37cdd3dc-8481-4e29-b78c-281baeca2d64
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3000
가변 인수가 있는 메서드가 CLS 규격이 아닙니다.  
  
 메서드에서 사용된 인수가 CLS\(공용 언어 사양\)에 없는 기능을 노출합니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)을 참조하세요.  
  
 다음 예제에서는 CS3000 경고를 생성합니다.  
  
```  
// CS3000.cs // compile with: /target:library // CS3000 expected [assembly:System.CLSCompliant(true)] public class Test { public void AddABunchOfInts( __arglist ) {}   // CS3000 }  
```
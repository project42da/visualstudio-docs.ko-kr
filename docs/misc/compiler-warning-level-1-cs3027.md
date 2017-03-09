---
title: "컴파일러 경고(수준 1) CS3027 | Microsoft Docs"
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
  - "CS3027"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3027"
ms.assetid: c515e623-3f5a-49fa-a878-f1d8e90fdc24
caps.latest.revision: 3
caps.handback.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3027
기본 인터페이스 'type\_2'가 CLS 규격이 아니므로 'type\_1'은 CLS 규격이 아닙니다.  
  
 CLS 규격이 아닌 형식은 CLS 규격인 형식의 기본 형식이 될 수 없습니다.  
  
## 예제  
 다음 샘플은 CLS 규격이 아닌 형식을 서명에 사용하여 형식을 CLS 규격으로 만드는 메서드가 있는 인터페이스를 포함합니다.  
  
```  
// CS3027.cs // compile with: /target:library public interface IBase { void IMethod(uint i); }  
```  
  
## 예제  
 다음 샘플에서는 CS3027을 생성합니다.  
  
```  
// CS3027_b.cs // compile with: /reference:CS3027.dll /target:library /W:1 [assembly:System.CLSCompliant(true)] public interface IDerived : IBase {}  
```
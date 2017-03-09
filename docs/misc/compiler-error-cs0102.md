---
title: "컴파일러 오류 CS0102 | Microsoft Docs"
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
  - "CS0102"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0102"
ms.assetid: c9419779-649f-4c24-b0f3-f0a1be46659e
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0102
'type name' 형식에 이미 'identifier'에 대한 정의가 포함되어 있습니다.  
  
 동일한 범위에서 식별자의 여러 선언이 동일한 이름으로 클래스에 포함되어 있습니다. 오류를 해결하려면 중복 식별자의 이름을 바꿉니다.  
  
## 예제  
 다음 샘플에서는 CS0102를 생성합니다.  
  
```  
// CS0102.cs // compile with: /target:library namespace MyApp { public class MyClass { string s = "Hello"; string s = "Goodbye";   // CS0102 public void GetString() { string s = "Hello again";   // method scope, no error } } }  
  
```
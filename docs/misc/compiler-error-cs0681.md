---
title: "컴파일러 오류 CS0681 | Microsoft Docs"
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
  - "CS0681"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0681"
ms.assetid: aa51ad94-df0a-481d-aaea-5b4291ebc41c
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0681
‘abstract’ 한정자는 필드에서 사용할 수 없습니다. 대신 속성을 사용합니다.  
  
 필드를 abstract로 만들 수 없습니다. 그러나 필드에 액세스하는 abstract 속성이 있을 수 있습니다.  
  
## 예제  
 다음 샘플에서는 CS0681을 생성합니다.  
  
```  
// CS0681.cs // compile with: /target:library abstract class C { abstract int num;  // CS0681 }  
  
```  
  
## 예제  
 다음 코드를 대신 사용해 보세요.  
  
```  
// CS0681b.cs // compile with: /target:library abstract class C { public abstract int num { get; set; } }  
```
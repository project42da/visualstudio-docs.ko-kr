---
title: "컴파일러 경고(수준 2) CS1587 | Microsoft Docs"
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
  - "CS1587"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1587"
ms.assetid: b27c2009-d485-43fd-a649-fbc15570d256
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS1587
XML 주석이 유효한 언어 요소에 배치되어 있지 않습니다.  
  
 문서 주석에 권장되는 태그가 모든 언어 요소에서 허용되지는 않습니다. 예를 들어 네임스페이스에는 태그를 사용할 수 없습니다. XML 주석에 대한 자세한 내용은 [문서 주석에 대한 권장 태그](/dotnet/csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1587을 생성합니다.  
  
```  
// CS1587.cs // compile with: /W:2 /doc:x.xml /// <summary>test</summary>   // CS1587, tag not allowed on namespace namespace MySpace { class MyClass { public static void Main() { } } }  
```
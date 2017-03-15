---
title: "컴파일러 경고(수준 1) CS1723 | Microsoft Docs"
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
  - "CS1723"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1723"
ms.assetid: d359be86-7daf-4b59-99a3-10b072336bca
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1723
'param'의 XML 주석에 형식 매개 변수를 참조하는 'attribute' cref 특성이 있습니다.  
  
 이 오류는 형식 매개 변수를 참조하는 XML 주석에 의해 생성됩니다.  
  
## 예제  
 다음 예제에서는 CS1723을 생성합니다.  
  
```  
// CS1723.cs // compile with: /t:library /doc:filename.XML ///<summary>A generic list class.</summary> ///<see cref="T" />   // CS1723 // To resolve comment the previous line. public class List<T> { }  
```
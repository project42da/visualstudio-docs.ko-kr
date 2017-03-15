---
title: "컴파일러 경고(수준 1) CS1589 | Microsoft Docs"
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
  - "CS1589"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1589"
ms.assetid: bdc47124-93ae-4c6a-81b2-dde8ec4d0ab1
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1589
'file' 파일의 'fragment' XML 조각을 포함할 수 없습니다. reason  
  
 파일\(`file`\)을 참조한 [\<include\>](../Topic/%3Cinclude%3E%20\(C%23%20Programming%20Guide\).md) 태그의 구문\(*조각*\)이 지정한 ***이유*** 때문에 잘못되었습니다.  
  
 형식이 잘못된 줄이 생성된 XML 파일에 배치됩니다.  
  
 다음 샘플에서는 CS1589를 생성합니다.  
  
```  
// CS1589.cs // compile with: /W:1 /doc:CS1589_out.xml /// <include file='CS1589.doc' path='MyDocs/MyMembers[@name="test"]/' />   // CS1589 // try the following line instead // /// <include file='CS1589.doc' path='MyDocs/MyMembers[@name="test"]/*' /> class Test { public static void Main() { } }  
```
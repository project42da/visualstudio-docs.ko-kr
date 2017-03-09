---
title: "컴파일러 경고(수준 4) CS1712 | Microsoft Docs"
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
  - "CS1712"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1712"
ms.assetid: d9a8be26-c0ba-41fa-b082-1ce4ba7724b7
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 4) CS1712
'type'의 XML 주석에 'type parameter' 형식 매개 변수와 짝이 맞는 형식 매개 변수 태그가 없습니다. 다른 형식 매개 변수는 짝이 맞는 태그가 있습니다.  
  
 제네릭 형식의 설명서에 **typeparam** 태그가 없습니다. 자세한 내용은 [\<typeparam\>](../Topic/%3Ctypeparam%3E%20\(C%23%20Programming%20Guide\).md)을 참조하세요.  
  
## 예제  
 다음 코드에서는 CS1712 경고를 생성합니다. 이 오류를 해결하려면 형식 매개 변수 S에 대한 **typeparam** 태그를 추가합니다.  
  
```  
// CS1712.cs // compile with: /doc:cs1712.xml using System; class Test { public static void Main() {} /// <param name="j"> This is the j parameter.</param> /// <typeparam name="T"> This is the T type parameter.</typeparam> public void bar<T,S>(int j) {}  // CS1712 }  
```
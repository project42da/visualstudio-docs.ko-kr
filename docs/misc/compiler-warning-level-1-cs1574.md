---
title: "컴파일러 경고(수준 1) CS1574 | Microsoft Docs"
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
  - "CS1574"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1574"
ms.assetid: 4cd2b474-ab01-4397-aed7-63e5f0081649
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1574
'construct'의 XML 주석에 잘못된 cref 특성 'name' 구문이 있습니다.  
  
 cref 태그\(예: \<exception\> 태그 내\)에 전달된 문자열이 현재 빌드 환경에서 사용할 수 없는 멤버를 참조했습니다. cref 태그에 전달하는 문자열은 구문상 멤버 또는 필드의 올바른 이름이어야 합니다.  
  
 자세한 내용은 [문서 주석에 대한 권장 태그](/dotnet/csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments)를 참조하세요.  
  
 다음 샘플에서는 CS1574를 생성합니다.  
  
```  
// CS1574.cs // compile with: /W:1 /doc:x.xml using System; /// <exception cref="System.Console.WriteLin">An exception class.</exception>   // CS1574 // instead, uncomment and try the following line // /// <exception cref="System.Console.WriteLine">An exception class.</exception> class EClass : Exception { } class TestClass { public static void Main() { try { } catch(EClass) { } } }  
```
---
title: "컴파일러 경고(수준 1) CS1584 | Microsoft Docs"
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
  - "CS1584"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1584"
ms.assetid: 56c8f9bf-4cce-4269-b573-d60e5b11f9ab
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1584
'member'의 XML 주석에 잘못된 cref 특성 'invalid\_syntax' 구문이 있습니다.  
  
 문서 주석의 태그에 전달된 매개 변수 중 하나에 잘못된 구문이 있습니다. 자세한 내용은 [문서 주석에 대한 권장 태그](/dotnet/csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS1584를 생성합니다.  
  
```  
// CS1584.cs // compile with: /W:1 /doc:CS1584.xml /// <remarks>Test class</remarks> public class Test { /// <remarks>Called in <see cref="Test.Mai()n"/>.</remarks>   // CS1584 // try the following line instead // /// <remarks>Called in <see cref="Test.Main()"/>.</remarks> public static void Test2() {} /// <remarks>Main method</remarks> public static void Main() {} }  
```
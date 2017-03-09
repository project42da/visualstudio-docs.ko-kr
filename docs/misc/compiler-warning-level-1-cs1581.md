---
title: "컴파일러 경고(수준 1) CS1581 | Microsoft Docs"
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
  - "CS1581"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1581"
ms.assetid: b7ac7586-a724-492c-887f-795af1c3bcc4
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1581
XML 주석 cref 특성에서 반환 형식이 잘못되었습니다.  
  
 메서드를 참조하려고 할 때 잘못된 반환 형식으로 인해 컴파일러가 오류를 검색했습니다.  
  
## 예제  
 다음 샘플에서는 CS1581을 생성합니다.  
  
```  
// CS1581.cs // compile with: /W:1 /doc:x.xml /// <summary>help text</summary> public class MyClass { /// <summary>help text</summary> public static void Main() { } /// <summary>help text</summary> public static explicit operator int(MyClass f) { return 0; } } /// <seealso cref="MyClass.explicit operator intt(MyClass)"/>  // CS1581 // try the following line instead // /// <seealso cref="MyClass.explicit operator int(MyClass)"/> public class MyClass2 { }  
```
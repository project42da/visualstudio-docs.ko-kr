---
title: "컴파일러 경고(수준 2) CS1571 | Microsoft Docs"
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
  - "CS1571"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1571"
ms.assetid: 23b08885-9f69-4376-a952-4820b065a5c0
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS1571
'construct'의 XML 주석에 'parameter'에 대한 중복 param 태그가 있습니다.  
  
 [\/doc](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option) 컴파일러 옵션을 사용할 때 동일한 메서드 매개 변수에 대한 여러 주석을 찾았습니다. 중복 줄 중 하나를 제거합니다.  
  
 다음 샘플에서는 CS1571을 생성합니다.  
  
```  
// CS1571.cs // compile with: /W:2 /doc:x.xml /// <summary>help text</summary> public class MyClass { /// <param name='Int1'>Used to indicate status.</param> /// <param name='Char1'>An initial.</param> /// <param name='Int1'>Used to indicate status.</param> // CS1571 public static void MyMethod(int Int1, char Char1) { } /// <summary>help text</summary> public static void Main () { } }  
```
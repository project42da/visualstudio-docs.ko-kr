---
title: "컴파일러 경고(수준 1) CS1580 | Microsoft Docs"
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
  - "CS1580"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1580"
ms.assetid: ffd1b6d7-6cab-47e3-b7fe-c79cb435cddf
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1580
XML 주석 cref 특성의 'parameter number' 매개 변수에 대해 잘못된 형식입니다.  
  
 메서드의 오버로드 형식을 참조하려는 동안 컴파일러가 구문 오류를 검색했습니다. 일반적으로 이는 형식이 아닌 매개 변수 이름이 지정되었음을 나타냅니다. 잘못된 형식의 줄이 생성된 XML 파일에 나타납니다.  
  
 다음 샘플에서는 CS1580을 생성합니다.  
  
```  
// CS1580.cs // compile with: /W:1 /doc:x.xml using System; /// <seealso cref="Test(i)"/>   // CS1580 // try the following line instead // /// <seealso cref="Test(int)"/> public class MyClass { /// <summary>help text</summary> public static void Main() { } /// <summary>help text</summary> public void Test(int i) { } /// <summary>help text</summary> public void Test(char i) { } }  
```
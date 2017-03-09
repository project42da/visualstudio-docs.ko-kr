---
title: "컴파일러 경고(수준 2) CS1572 | Microsoft Docs"
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
  - "CS1572"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1572"
ms.assetid: 24bc8b96-29d2-4201-bc4e-6b9b5a4f5a1d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS1572
'construct'의 XML 주석에 'parameter'에 대한 param 태그가 있지만 해당 이름을 가진 매개 변수가 없습니다.  
  
 [\/doc](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option) 컴파일러 옵션을 사용할 때 메서드에 대해 존재하지 않는 매개 변수에 대해 주석이 지정되었습니다. 이름 특성에 전달된 값을 변경하거나 주석 줄 중 하나를 제거합니다.  
  
 다음 샘플에서는 CS1572를 생성합니다.  
  
```  
// CS1572.cs // compile with: /W:2 /doc:x.xml /// <summary>help text</summary> public class MyClass { /// <param name='Int1'>Used to indicate status.</param> /// <param name='Char1'>Used to indicate status.</param> /// <param name='Char2'>???</param> // CS1572 public static void MyMethod(int Int1, char Char1) { } /// <summary>help text</summary> public static void Main () { } }  
```
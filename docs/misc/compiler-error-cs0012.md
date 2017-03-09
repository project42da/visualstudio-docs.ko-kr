---
title: "컴파일러 오류 CS0012 | Microsoft Docs"
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
  - "CS0012"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0012"
ms.assetid: 5523e349-22f4-4b0b-b4b0-c4bf26c461f4
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0012
'type' 형식이 참조되지 않은 어셈블리에 정의되었습니다. 'assembly' 어셈블리에 참조를 추가해야 합니다.  
  
 참조된 형식에 대한 정의를 찾을 수 없습니다. 이 오류는 필요한 .DLL 파일이 컴파일에 포함되지 않은 경우 발생할 수 있습니다. 자세한 내용은 [Add Reference Dialog Box](http://msdn.microsoft.com/ko-kr/2feb0fe2-0805-4cc9-8cba-b0315849dfb7) 및 [\/reference \(Import Metadata\)](/dotnet/csharp/language-reference/compiler-options/reference-compiler-option)를 참조하세요.  
  
 다음 컴파일 시퀀스는 CS0012를 생성합니다.  
  
```  
// cs0012a.cs // compile with: /target:library public class A {}  
```  
  
 다음을 수행합니다.  
  
```  
// cs0012b.cs // compile with: /target:library /reference:cs0012a.dll public class B { public static A f() { return new A(); } }  
```  
  
 다음을 수행합니다.  
  
```  
// cs0012c.cs // compile with: /reference:cs0012b.dll class C { public static void Main() { object o = B.f();   // CS0012 } }  
```  
  
 `/reference:cs0012b.dll;cs0012a.dll`을 사용하여 컴파일하거나 Visual Studio에서 [Add Reference Dialog Box](http://msdn.microsoft.com/ko-kr/2feb0fe2-0805-4cc9-8cba-b0315849dfb7)를 사용하여 cs0012a.dll 및 cs0012b.dll에 대한 참조를 추가하여 CS0012를 해결할 수 있습니다.
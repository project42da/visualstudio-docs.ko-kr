---
title: "컴파일러 오류 CS0208 | Microsoft Docs"
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
  - "CS0208"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0208"
ms.assetid: 03534893-1522-4dab-9822-8b9ed97b3bd0
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0208
관리되는 형식\('type'\)의 주소 또는 크기를 가져오거나 해당 형식에 대한 포인터를 선언할 수 없습니다.  
  
 [unsafe](/dotnet/csharp/language-reference/keywords/unsafe) 키워드와 함께 사용하는 경우에도 관리 개체의 주소를 사용하거나 관리 개체의 크기를 가져올 수 없으며 관리되는 형식에 대한 포인터를 선언할 수도 없습니다. 관리되는 형식은 다음과 같습니다.  
  
-   임의 참조 형식  
  
-   필드 또는 속성으로 참조 형식을 포함하는 임의 구조체  
  
 자세한 내용은 [안전하지 않은 코드 및 포인터](/dotnet/csharp/programming-guide/unsafe-code-pointers/index) 및 [sizeof](/dotnet/csharp/language-reference/keywords/sizeof)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 CS0208을 생성합니다.  
  
```  
// CS0208.cs // compile with: /unsafe class myClass { public int a = 98; } struct myProblemStruct { string s; float f; } struct myGoodStruct { int i; float f; } public class MyClass { unsafe public static void Main() { // myClass is a class, a managed type. myClass s = new myClass(); myClass* s2 = &s;    // CS0208 // The struct contains a string, a managed type. int i = sizeof(myProblemStruct); //CS0208 // The struct contains only value types. i = sizeof(myGoodStruct); //OK } }  
  
```  
  
## 참고 항목  
 [sizeof](/dotnet/csharp/language-reference/keywords/sizeof)
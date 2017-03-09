---
title: "컴파일러 오류 CS0249 | Microsoft Docs"
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
  - "CS0249"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0249"
ms.assetid: 8bc3572f-d949-4867-b119-6527fb924a4a
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0249
object.Finalize를 재정의하는 대신 소멸자를 제공하세요.  
  
 소멸자 구문을 사용하여 개체가 소멸될 때 실행할 명령을 지정합니다.  
  
 자세한 내용은 [C\# 및 C\+\+의 소멸자 구문](http://msdn.microsoft.com/ko-kr/d7901491-7e89-4b6f-8270-0635aa6581b5)을 참조하세요.  
  
 다음 샘플에서는 CS0249를 생성합니다.  
  
```  
// CS0249.cs class MyClass { protected override void Finalize()   // CS0249 // try the following line instead // ~MyClass() { } public static void Main() { } }  
```
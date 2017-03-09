---
title: "컴파일러 경고(수준 1) CS1635 | Microsoft Docs"
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
  - "CS1635"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1635"
ms.assetid: e1795880-f7ea-4dca-b15b-4ba549d7ed78
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS1635
전역으로 사용하지 않도록 설정되었기 때문에 'warning code' 경고를 복원할 수 없습니다.  
  
 **\/nowarn** 명령줄 옵션 또는 프로젝트 설정을 사용하여 전체 컴파일 단위에 대해 경고를 사용하지 않도록 활성화하고 `#pragma warning restore`를 사용하여 해당 경고를 복원하려고 시도하는 경우 이 경고가 발생합니다. 이 오류를 해결하려면 \/nowarn 명령줄 옵션 또는 프로젝트 설정을 제거하거나 명령줄 또는 프로젝트 설정을 통해 사용하지 않도록 설정하는 경고에 대해 `#pragma warning restore`를 제거합니다. 자세한 내용은 [\#pragma 경고](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning) 항목을 참조하세요.  
  
 다음 샘플에서는 CS1635를 생성합니다.  
  
```  
// CS1635.cs // compile with: /w:1 /nowarn:162 enum MyEnum {one=1,two=2,three=3}; class MyClass { public static void Main() { #pragma warning disable 162 if (MyEnum.three == MyEnum.two) System.Console.WriteLine("Duplicate"); #pragma warning restore 162 } }  
```
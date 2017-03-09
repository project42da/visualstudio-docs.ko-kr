---
title: "컴파일러 오류 CS0430 | Microsoft Docs"
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
  - "CS0430"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0430"
ms.assetid: b63c4f9a-b1cd-41d2-a02e-2ed0f177450f
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0430
\/reference 옵션에 extern 별칭 'alias'를 지정하지 않았습니다.  
  
 이 오류는 extern 별칭이 나타날 때 발생하지만 별칭이 명령줄에 참조로 지정되지 않았습니다. CS0430을 해결하려면 **\/reference**을 사용하여 컴파일합니다.  
  
## 예제  
  
```  
// CS0430_a.cs // compile with: /target:library public class MyClass {}  
```  
  
## 예제  
 이전 샘플에서 만든 DLL을 참조할 수 있도록 **\/reference:MyType\=cs0430\_a.dll**을 사용하여 컴파일하면 이 오류를 해결할 수 있습니다. 다음 샘플에서는 CS0430을 생성합니다.  
  
```  
// CS0430_b.cs extern alias MyType;   // CS0430 public class Test { public static void Main() {} }  
  
```
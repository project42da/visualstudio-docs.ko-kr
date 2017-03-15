---
title: "컴파일러 오류 CS0075 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0075"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0075"
ms.assetid: 5084d260-705e-4ff5-8f7a-7f74052fcbbb
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0075
음의 값을 캐스팅하려면 값을 괄호로 묶어야 합니다.  
  
 미리 정의된 형식을 식별하는 키워드를 사용하여 캐스팅하는 경우 괄호가 필요하지 않습니다. 그렇지 않은 경우 \(x\)\-y가 캐스트 식으로 고려되지 않기 때문에 괄호를 추가해야 합니다. C\# 사양에서 7.6.6 섹션:  
  
 *명확성 규칙에서 x 및 y가 식별자인 경우 \(x\)y, \(x\)\(y\) 및 \(x\)\(\-y\)는 캐스트 식이지만 \(x\)\-y는 캐스트 식이 아닙니다. 이는 x가 형식을 식별하는 경우에도 마찬가지입니다. 그러나 x가 미리 정의된 형식\(예: int\)을 식별하는 키워드인 경우 이러한 키워드는 자체적으로 식이 될 수 없으므로 4가지 형태가 모두 캐스트 식입니다.*  
  
 다음 코드에서는 CS0075를 생성합니다.  
  
```  
// CS0075 namespace MyNamespace { enum MyEnum { } public class MyClass { public static void Main() { // To fix the error, place the negative // values below in parentheses int i = (System.Int32) - 4; //CS0075 MyEnum e = (MyEnum) - 1;    //CS0075 System.Console.WriteLine(i); //to avoid warning System.Console.WriteLine(e); //to avoid warning } } }  
```  
  
## 참고 항목  
 [캐스팅 및 형식 변환\(C\#\)](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)
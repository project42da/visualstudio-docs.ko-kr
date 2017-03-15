---
title: "컴파일러 오류 CS0664 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0664"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0664"
ms.assetid: 60fe15a7-db22-414f-a7b8-fac79dad22b4
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0664
double 형식의 리터럴을 암시적으로 'type' 형식으로 변환할 수 없습니다. 이 형식의 리터럴을 만들려면 'suffix' 접미사를 사용합니다.  
  
 할당을 완료할 수 없습니다. 접미사를 사용하여 지침을 수정합니다. 각 형식에 대한 설명서는 형식에 대한 해당 접미사를 식별합니다. 변환에 대한 자세한 내용은 [캐스팅 및 형식 변환\(C\#\)](/dotnet/csharp/programming-guide/types/casting-and-type-conversions)를 참조하세요.  
  
 다음 샘플에서는 CS0664를 생성합니다.  
  
```c#  
// CS0664.cs class Example { static void Main() { decimal d1 = 1.0;   // CS0664, because 1.0 is interpreted // as a double. // Try the following line instead. decimal d2 = 1.0M;  // The M tells the compiler that 1.0 is a // decimal. Console.WriteLine(d2); } }  
```  
  
## 참고 항목  
 [형식 변환표](../Topic/Type%20Conversion%20Tables%20in%20the%20.NET%20Framework.md)
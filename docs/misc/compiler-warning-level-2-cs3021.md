---
title: "컴파일러 경고(수준 2) CS3021 | Microsoft Docs"
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
  - "CS3021"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3021"
ms.assetid: 89f09e4d-65b0-4422-86ea-85c7e05ac29b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS3021
어셈블리에 CLSCompliant 특성이 없으므로 'type'에 CLSCompliant 특성이 필요하지 않습니다.  
  
 어셈블리 수준의 CLSCompliant 특성이 true\(즉, `[assembly: CLSCompliant(true)]` 줄\)로 설정되지 않은 어셈블리에서 클래스에 `[CLSCompliant(false)]` 가 있는 경우 이 경고가 발생합니다. 어셈블리가 자체적으로 CLS 규격으로 선언하지 않아 비규격으로 간주되므로 어셈블리 내에서 별도로 비규격으로 선언할 필요가 없습니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)을 참조하세요.  
  
 이 경고가 발생하지 않게 하려면 특성을 제거하거나 어셈블리 수준 특성을 추가합니다.  
  
## 예제  
 다음 예제는 CS3021을 생성합니다.  
  
```  
// CS3021.cs using System; // Uncomment the following line to declare the assembly CLS Compliant, // and avoid the warning without removing the attribute on the class. //[assembly: CLSCompliant(true)] // Remove the next line to avoid the warning. [CLSCompliant(false)]               // CS3021 public class C { public static void Main() { } }  
```  
  
## 참고 항목  
 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)
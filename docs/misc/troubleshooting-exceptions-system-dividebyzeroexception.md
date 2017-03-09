---
title: "예외 문제 해결: System.DivideByZeroException | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "DivideByZeroException 클래스"
ms.assetid: ddc79201-3ba1-455f-8496-edaad792ccf1
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.DivideByZeroException
<xref:System.DivideByZeroException> 예외는 정수나 10진수 값을 0으로 나누려 할 때 throw됩니다.  
  
## 관련 팁  
 **나누기 연산을 수행하기 전에 분모의 값이 0이 아닌지 확인하십시오.**  
 부동 소수점 값을 0으로 나눈 결과는 IEEE 산술 규칙에 따라 양의 무한대, 음의 무한대 또는 NaN\(숫자가 아님\)이 될 수 있습니다. 부동 소수점 연산에서는 예외가 throw되지 않습니다.  
  
## 참고 항목  
 <xref:System.DivideByZeroException>   
 [Arithmetic Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators)   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
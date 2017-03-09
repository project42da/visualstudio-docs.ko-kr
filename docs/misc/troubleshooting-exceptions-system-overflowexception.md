---
title: "예외 문제 해결: System.OverflowException | Microsoft Docs"
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
  - "OverflowException 클래스"
ms.assetid: bd380db7-5d05-4d7f-be5b-e654fdadf14c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.OverflowException
<xref:System.OverflowException> 예외는 선택한 컨텍스트에서 산술 연산, 캐스팅 또는 변환 작업을 수행한 결과로 오버플로가 발생하는 경우에 throw됩니다. 오버플로는 작업 결과로 NaN\(숫자가 아님\), 무한대 또는 대상 형식에 비해 너무 큰 값이 생성되는 경우에 발생합니다.  
  
## 관련 팁  
 **숫자에서 캐스트할 때 그 값은 무한대보다 작은 숫자여야 합니다.**  
 소스 값은 무한대 또는 NaN\(숫자가 아님\)이 될 수 없습니다.  
  
 **분모가 0이 아닌지 확인하세요.**  
 일반적으로 0으로 나눌 때 이 예외가 발생합니다.  
  
## 설명  
 오버플로를 감지하는 언어에서 <xref:System.OverflowException>은 오버플로가 발생하는 경우에 throw되는 예외입니다. 예를 들어, C\#에서 `checked` 키워드는 오버플로 조건을 검색하는 데 사용됩니다.<xref:System.OverflowException> 예외는 checked 컨텍스트에서만 발생합니다.  
  
 정수 계열 또는 10진수 형식 산술 연산 작업이나 변환의 결과가 대상 형식의 범위 밖에 있는 경우  
  
-   연산이 상수 식이면 checked 컨텍스트에서 컴파일 시간 오류가 발생합니다. 그렇지 않으면 런타임에 작업을 수행하는 경우 <xref:System.OverflowException> 예외가 throw됩니다.  
  
-   unchecked 컨텍스트에서는 대상 형식에 맞지 않는 상위 비트가 삭제되어 해당 결과가 잘립니다.  
  
 데이터 형식의 값 범위에 대한 자세한 내용은 [Data Types](/dotnet/visual-basic/language-reference/data-types/data-type-summary), [정수 계열 형식 표](/dotnet/csharp/language-reference/keywords/integral-types-table) 또는 [부동 소수점 형식 표](/dotnet/csharp/language-reference/keywords/floating-point-types-table)를 참조하세요.  
  
## 참고 항목  
 <xref:System.OverflowException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
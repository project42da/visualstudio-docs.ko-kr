---
title: "예외 문제 해결: System.FormatException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "FormatException 클래스"
ms.assetid: b2a4f55e-da87-4915-a053-59eb1595993d
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.FormatException
<xref:System.FormatException> 예외는 인수 형식이 메서드의 매개 변수 사양에 맞지 않을 때 형식을 구문 분석하거나 형식을 지정하는 메서드에서 throw합니다.  
  
## 이 문서의 내용  
  
## 형식 예외 생성  
  
### 서식 지정  
 *형식 지정*은 대개 결과 문자열을 사용자에게 표시하거나 개체 상태를 저장하는 데 사용하기 위해 클래스, 구조체 또는 열거형 값의 인스턴스를 해당 문자열 표현으로 변환하는 프로세스입니다.  
  
 예를 들어 <xref:System.Int32.ToString%28System.String%29?displayProperty=fullName>은 표준 또는 사용자 지정 *형식 문자열*을 식별하고 숫자의 문자열 표현을 반환하는 문자열 매개 변수를 사용합니다. 형식 문자열이 잘못되었거나 지원되지 않으면 메서드는 <xref:System.FormatException>을 throw합니다.  
  
### 복합 형식 지정  
 *복합 형식 지정*에서는 개체 목록과 합성 형식 문자열을 입력으로 사용합니다. 합성 서식 문자열은 고정 텍스트와 목록의 개체에 해당하는 인덱싱된 자리 표시자\(서식 항목이라고 함\)가 결합된 형태로 구성됩니다. 서식 지정 작업을 통해 원래의 고정 텍스트와 목록에 있는 개체의 문자열 표현이 결합된 형태의 결과 문자열을 얻을 수 있습니다.  
  
 복합 형식 지정을 수행하는 메서드의 예로는 <xref:System.String.Format%2A?displayProperty=fullName> 및 <xref:System.Console.WriteLine%2A?displayProperty=fullName>이 있습니다. 복합 형식 지정을 사용하는 메서드는 형식 문자열이 잘못된 경우 또는 형식 항목의 인덱스가 0보다 작거나 인수 수 이상인 경우 <xref:System.FormatException>을 throw합니다.  
  
### 구문 분석  
 *구문 분석*은 .NET Framework 기본 형식을 나타내는 문자열을 해당 기본 형식으로 변환하는 프로세스입니다. 구문 분석 작업을 사용하여 문자열을 부동 소수점 숫자나 날짜 및 시간 값으로 변환하는 경우를 예로 들 수 있습니다.  
  
 예를 들어 <xref:System.Int32.Parse%28System.String%29?displayProperty=fullName><xref:System.DateTime.Parse%2A>는 <xref:System.IformatProvider> 매개 변수에 지정된 문화권별 형식 정보를 사용하여 날짜와 시간의 문자열 표현을 그와 동일한 <xref:System.DateTime>으로 변환합니다. 문자열 형식이 올바르지 않으면 <xref:System.FormatException>이 throw됩니다.  
  
## FormatExceptions 방지  
 <xref:System.FormatException> 클래스 참조 문서에는 <xref:System.FormatException> 오류의 일반적인 원인과 해결 방법이 나와 있습니다.  
  
 MSDN 라이브러리 섹션 [형식 서식 지정](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md) 및 [문자열 구문 분석](../Topic/Parsing%20Strings%20in%20the%20.NET%20Framework.md)에는 형식을 올바르게 지정하고 구문 분석하는 작업에 대한 정보가 포함되어 있습니다.  
  
 **복합 형식 지정**  
  
 [복합 형식 지정](../Topic/Composite%20Formatting.md)  
  
 **숫자 형식**  
  
|||  
|-|-|  
|[표준 숫자 형식 문자열](../Topic/Standard%20Numeric%20Format%20Strings.md)|[사용자 지정 숫자 형식 문자열](../Topic/Custom%20Numeric%20Format%20Strings.md)|  
|[숫자 문자열 구문 분석](../Topic/Parsing%20Numeric%20Strings%20in%20the%20.NET%20Framework.md)||  
  
 **날짜 및 시간과 Timespan 형식**  
  
|||  
|-|-|  
|[표준 날짜 및 시간 형식 문자열](../Topic/Standard%20Date%20and%20Time%20Format%20Strings.md)|[사용자 지정 날짜 및 시간 형식 문자열](../Topic/Custom%20Date%20and%20Time%20Format%20Strings.md)|  
|[표준 TimeSpan 서식 문자열](../Topic/Standard%20TimeSpan%20Format%20Strings.md)|[사용자 지정 TimeSpan 서식 문자열](../Topic/Custom%20TimeSpan%20Format%20Strings.md)|  
|[날짜 및 시간 문자열 구문 분석](../Topic/Parsing%20Date%20and%20Time%20Strings%20in%20the%20.NET%20Framework.md)||  
  
 **기타 형식**  
  
|||  
|-|-|  
|[열거형 형식 문자열](../Topic/Enumeration%20Format%20Strings.md)|[기타 문자열 구문 분석](../Topic/Parsing%20Other%20Strings%20in%20the%20.NET%20Framework.md)|
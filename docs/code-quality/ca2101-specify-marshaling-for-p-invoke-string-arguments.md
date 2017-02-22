---
title: "CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SpecifyMarshalingForPInvokeStringArguments"
  - "CA2101"
helpviewer_keywords: 
  - "CA2101"
  - "SpecifyMarshalingForPInvokeStringArguments"
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA2101: P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SpecifyMarshalingForPInvokeStringArguments|  
|CheckId|CA2101|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 플랫폼 호출 멤버가 부분 신뢰 호출자를 허용하고, 문자열 매개 변수를 사용하고, 문자열을 명시적으로 마샬링하지 않습니다.  
  
## 규칙 설명  
 유니코드를 ANSI로 변환할 경우 모든 유니코드 문자를 특정 ANSI 코드 페이지에 표시할 수 없는 경우가 있습니다.  *BestFitMapping*에서는 표시할 수 없는 문자를 대체하여 이 문제를 해결하려고 합니다.  이 기능을 사용하면 선택되는 문자를 제어할 수 없으므로 보안 문제가 발생할 수 있습니다.  예를 들어, 악의적인 코드에서 고의적으로 특정 코드 페이지에서 찾을 수 없는 문자를 포함하는 유니코드 문자열을 만들어 '..' 또는 '\/' 같은 파일 시스템 특수 문자로 변환되도록 할 수 있습니다.  또한 보안 검사에서는 문자열을 ANSI로 변환하기 전에 특수 문자가 자주 나타나는지를 확인합니다.  
  
 BestFitMapping은 WChar에서 MByte로의 관리되지 않는 변환에 사용되는 기본값입니다.  BestFitMapping을 사용하지 않도록 명시적으로 설정하지 않으면 이 문제 때문에 코드에 악용 가능한 보안 문제가 포함될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 문자열 데이터 형식을 명시적으로 마샬링합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 메서드를 보여 주고 위반 문제를 해결하는 방법을 보여 줍니다.  
  
 [!code-cs[FxCop.Security.PinvokeAnsiUnicode#1](../code-quality/codesnippet/CSharp/ca2101-specify-marshaling-for-p-invoke-string-arguments_1.cs)]
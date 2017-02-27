---
title: "CA1302: 로캘별 문자열을 하드 코딩하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DoNotHardcodeLocaleSpecificStrings"
  - "CA1302"
helpviewer_keywords: 
  - "DoNotHardcodeLocaleSpecificStrings"
  - "CA1302"
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 17
---
# CA1302: 로캘별 문자열을 하드 코딩하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotHardcodeLocaleSpecificStrings|  
|CheckId|CA1302|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드에서 특정 시스템 폴더 경로의 일부를 나타내는 문자열 리터럴을 사용합니다.  
  
## 규칙 설명  
 <xref:System.Environment.SpecialFolder?displayProperty=fullName> 열거형에는 특수 시스템 폴더를 참조하는 멤버가 포함되어 있습니다.  이들 폴더의 위치는 운영 체제에 따라 값이 다를 수 있으며, 사용자가 위치 일부를 변경할 수 있고, 위치는 지역화됩니다.  특수 폴더의 예는 [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)]에서는 "C:\\WINDOWS\\system32"이고 [!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]에서는 "C:\\WINNT\\system32"입니다.  <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> 메서드는 <xref:System.Environment.SpecialFolder> 열거형과 연결된 위치를 반환합니다.  <xref:System.Environment.GetFolderPath%2A>에서 반환하는 위치는 지역화되므로 현재 실행되고 있는 컴퓨터에 적합합니다.  
  
 이 규칙은 <xref:System.Environment.GetFolderPath%2A> 메서드를 사용하여 검색한 폴더 경로를 구분된 디렉터리 수준으로 토큰화합니다.  각 문자열 리터럴은 토큰과 비교됩니다.  일치하는 것이 있으면 메서드가 해당 토큰에 연결된 시스템 위치를 참조하는 문자열을 구성하고 있는 것으로 간주됩니다.  이식성과 지역화 가능성을 위해서는 문자열 리터럴을 사용하는 대신 <xref:System.Environment.GetFolderPath%2A> 메서드를 사용하여 특수 시스템 폴더의 위치를 검색합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Environment.GetFolderPath%2A> 메서드를 사용하여 위치를 검색합니다.  
  
## 경고를 표시하지 않는 경우  
 문자열 리터럴이 <xref:System.Environment.SpecialFolder> 열거형과 연결된 시스템 위치 중 하나를 참조하는 데 사용되지 않는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 공통 응용 프로그램 데이터 폴더에 대한 경로를 만들며 그 결과 이 규칙으로부터 세 개의 경고가 생성됩니다.  그런 다음 <xref:System.Environment.GetFolderPath%2A> 메서드를 사용하여 경로를 검색합니다.  
  
 [!code-cs[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)]
 [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]  
  
## 관련 규칙  
 [CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)
---
title: "CA1302: 로캘별 문자열을 하드 코딩 하지 마십시오 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9a6fc1bac1b13d432f395842c7de4ce6250dd708
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302: 로캘별 문자열을 하드 코딩하지 마십시오.
|||  
|-|-|  
|TypeName|DoNotHardcodeLocaleSpecificStrings|  
|CheckId|CA1302|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 메서드는 특정 시스템 폴더의 경로 나타내는 문자열 리터럴을 사용 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 <xref:System.Environment.SpecialFolder?displayProperty=fullName> 열거형 특수 시스템 폴더를 참조 하는 멤버가 포함 되어 있습니다. 이러한 폴더의 위치는 다른 운영 체제에서 서로 다른 값을 가질 수, 사용자가 위치 일부를 변경할 수 및 위치는 지역화 합니다. 특수 폴더의 예로 "C:\WINDOWS\system32"는 시스템 폴더에 켜져 [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)] "C:\WINNT\system32"에 있지만 [!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]합니다. <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> 연관 된 위치를 반환 하는 메서드는 <xref:System.Environment.SpecialFolder> 열거형입니다. 반환 되는 위치 <xref:System.Environment.GetFolderPath%2A> 는 지역화 하 고 현재 실행 중인 컴퓨터에 적합 합니다.  
  
 이 규칙에서는 사용 하 여 검색 되는 폴더 경로 토큰화는 <xref:System.Environment.GetFolderPath%2A> 메서드 별도 디렉터리 수준으로 됩니다. 각 문자열 리터럴 토큰 비교 됩니다. 일치 항목이 발견 되는 메서드가 토큰와 연결 된 시스템의 위치를 참조 하는 문자열을 구성 하 고 있는 간주 됩니다. 이식성 지역화 가능성을 사용 하 여는 <xref:System.Environment.GetFolderPath%2A> 문자열 리터럴을 사용 하는 대신 특수 시스템 폴더의 위치를 검색 하는 메서드입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면 사용 하 여 위치를 검색할는 <xref:System.Environment.GetFolderPath%2A> 메서드.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 와 연결 된 시스템 위치 중 하나를 참조 하려면 리터럴 문자열을 사용 하지 않는 경우이 규칙에서는 경고를에서 표시 하지 않는를 안전 하 게는 <xref:System.Environment.SpecialFolder> 열거형입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는이 규칙에서 세 가지 경고를 생성 하는 일반적인 응용 프로그램 데이터 폴더의 경로 빌드합니다. 이 예제를 사용 하 여 경로 검색 하는 다음으로 <xref:System.Environment.GetFolderPath%2A> 메서드.  
  
 [!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)]
 [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)
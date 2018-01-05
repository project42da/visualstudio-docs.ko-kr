---
title: "CA1306: 데이터 형식에 대 한 로캘을 설정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fc39ece5eaecfdb36576501caa432abeb365b9cb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: 데이터 형식에 맞는 로캘을 설정하십시오.
|||  
|-|-|  
|TypeName|SetLocaleForDataTypes|  
|CheckId|CA1306|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 메서드 또는 생성자 만든 하나 이상의 <xref:System.Data.DataTable?displayProperty=fullName> 또는 <xref:System.Data.DataSet?displayProperty=fullName> 인스턴스 및 locale 속성을 명시적으로 설정 되지 않은 (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> 또는 <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).  
  
## <a name="rule-description"></a>규칙 설명  
 로캘은 숫자 값, 통화 기호 및 정렬 순서에 사용 된 포멧을 등의 데이터에 대 한 문화권별 표현 요소를 결정 합니다. 만들 때 한 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>, 로캘을 명시적으로 설정 해야 합니다. 기본적으로 이러한 형식에 대 한 로캘을 현재 문화권. 데이터베이스 또는 파일에 저장 되 고 전역 공유 하는 데이터에 대 한 로캘을 일반적으로로 설정 해야 고정 문화권 (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>). 문화권에 걸쳐 데이터를 공유 하면에서 기본 로캘을 사용 하면이의 내용을 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet> 표시 되거나 올바르게 해석 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하려면에 대 한 로캘을 명시적으로 설정 된 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 라이브러리 또는 응용 프로그램은 제한 된 로컬 사용자를 대상, 데이터 공유 되지 않습니다 또는 기본 설정은 지원 되는 모든 시나리오에서 원하는 동작을 수행할 때이 규칙에서 경고를 표시 하지 않으려면 안전 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 두 개의 <xref:System.Data.DataTable> 인스턴스.  
  
 [!code-csharp[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Data.DataTable?displayProperty=fullName>   
 <xref:System.Data.DataSet?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
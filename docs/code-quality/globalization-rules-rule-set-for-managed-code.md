---
title: "관리 코드에 대 한 전역화 규칙 규칙 집합 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c4032ee-0805-4581-8c48-b1827cd6b213
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 07a2e8da87eb486f8247a79263ec371a8fd4afc5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="globalization-rules-rule-set-for-managed-code"></a>관리 코드에 대한 전역화 규칙 규칙 집합
Microsoft 전역화 규칙 규칙 집합 다양 한 언어, 로캘 및 문화권에서 올바르게 표시 응용 프로그램에서 데이터를 방해할 수 있는 문제에 초점을 사용할 수 있습니다. 응용 프로그램이 지역화 되거나 전역화 되는 경우이 규칙 집합 중 하나 또는 둘 다를 포함 해야 합니다.  
  
|규칙|설명|  
|----------|-----------------|  
|[CA1300](../code-quality/ca1300-specify-messageboxoptions.md)|MessageBoxOptions를 지정 합니다.|  
|[CA1301](../code-quality/ca1301-avoid-duplicate-accelerators.md)|중복 액셀러레이터 키를 사용하지 마십시오.|  
|[CA1302](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|로캘별 문자열을 하드 코딩 하지 마십시오|  
|[CA1303](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|리터럴을 지역화 된 매개 변수로 전달 하지 마십시오|  
|[CA1304](../code-quality/ca1304-specify-cultureinfo.md)|CultureInfo를 지정 합니다.|  
|[CA1305](../code-quality/ca1305-specify-iformatprovider.md)|IFormatProvider를 지정 하십시오|  
|[CA1306](../code-quality/ca1306-set-locale-for-data-types.md)|데이터 형식에 대 한 로캘을 설정 하십시오.|  
|[CA1307](../code-quality/ca1307-specify-stringcomparison.md)|StringComparison 지정|  
|[CA1308](../code-quality/ca1308-normalize-strings-to-uppercase.md)|문자열을 대문자로 정규화 하십시오.|  
|[CA1309](../code-quality/ca1309-use-ordinal-stringcomparison.md)|서 수 StringComparison을 사용 하 여|  
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|P/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.|
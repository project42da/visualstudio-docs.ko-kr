---
title: "관리 코드에 대한 전역화 규칙 규칙 집합 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3c4032ee-0805-4581-8c48-b1827cd6b213
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 관리 코드에 대한 전역화 규칙 규칙 집합
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Microsoft 전역화 규칙이라는 규칙 집합을 사용하면 응용 프로그램의 데이터가 다른 언어, 로캘 및 문화권에서 올바르게 표시되지 않을 수 있는 문제를 집중적으로 확인할 수 있습니다.  응용 프로그램을 지역화되거나 전역화되거나 둘 모두에 해당되는 경우에는 이 규칙 집합을 포함해야 합니다.  
  
|규칙|설명|  
|--------|--------|  
|[CA1300](../code-quality/ca1300-specify-messageboxoptions.md)|MessageBoxOptions를 지정하십시오.|  
|[CA1301](../Topic/CA1301:%20Avoid%20duplicate%20accelerators.md)|중복 액셀러레이터 키를 사용하지 마십시오.|  
|[CA1302](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|CA1302: 로캘별 문자열을 하드 코딩하지 마십시오.|  
|[CA1303](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|CA1303: 리터럴을 지역화된 매개 변수로 전달하지 마십시오.|  
|[CA1304](../Topic/CA1304:%20Specify%20CultureInfo.md)|CA1304: CultureInfo를 지정하십시오.|  
|[CA1305](../code-quality/ca1305-specify-iformatprovider.md)|CA1305: IFormatProvider를 지정하십시오.|  
|[CA1306](../code-quality/ca1306-set-locale-for-data-types.md)|CA1306: 데이터 형식에 맞는 로캘을 설정하십시오.|  
|[CA1307](../code-quality/ca1307-specify-stringcomparison.md)|CA1307: StringComparison 지정|  
|[CA1308](../code-quality/ca1308-normalize-strings-to-uppercase.md)|CA1308: 문자열을 대문자로 정규화하십시오.|  
|[CA1309](../code-quality/ca1309-use-ordinal-stringcomparison.md)|CA1309: 서수 StringComparison을 사용하십시오.|  
|[CA2101](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|P\/Invoke 문자열 인수에 대해 마샬링을 지정하십시오.|
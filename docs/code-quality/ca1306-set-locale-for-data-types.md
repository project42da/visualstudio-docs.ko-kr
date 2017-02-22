---
title: "CA1306: 데이터 형식에 맞는 로캘을 설정하십시오. | Microsoft Docs"
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
  - "CA1306"
  - "SetLocaleForDataTypes"
helpviewer_keywords: 
  - "CA1306"
  - "SetLocaleForDataTypes"
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1306: 데이터 형식에 맞는 로캘을 설정하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|SetLocaleForDataTypes|  
|CheckId|CA1306|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드 또는 생성자에서 하나 이상의 <xref:System.Data.DataTable?displayProperty=fullName> 또는 <xref:System.Data.DataSet?displayProperty=fullName> 인스턴스를 만들고 로캘 속성\(<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> 또는 <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>\)을 명시적으로 설정하지 않았습니다.  
  
## 규칙 설명  
 로캘은 숫자 값에 사용되는 서식, 통화 기호 및 정렬 순서 등과 같은 데이터의 문화권별 표현 요소를 결정합니다.  <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>을 만들 때는 로캘을 명시적으로 설정해야 합니다.  기본적으로 이러한 형식의 로캘은 현재 문화권입니다.  데이터베이스나 파일에 저장되어 있고 전역 공유되는 데이터의 경우 로캘은 일반적으로 고정 문화권\(<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>\)로 설정해야 합니다.  데이터가 여러 문화권 간에 공유되는 경우 기본 로캘을 사용하면 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 내용이 잘못 표시되거나 해석될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 <xref:System.Data.DataTable> 또는 <xref:System.Data.DataSet>의 로캘을 명시적으로 설정합니다.  
  
## 경고를 표시하지 않는 경우  
 라이브러리나 응용 프로그램이 제한된 지역의 사용자를 대상으로 하는 경우, 데이터가 공유되지 않는 경우, 지원되는 모든 시나리오에서 기본 설정으로 원하는 동작을 수행할 수 있는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 두 개의 <xref:System.Data.DataTable> 인스턴스를 만듭니다.  
  
 [!code-cs[FxCop.Globalization.DataTable#1](../code-quality/codesnippet/CSharp/ca1306-set-locale-for-data-types_1.cs)]  
  
## 참고 항목  
 <xref:System.Data.DataTable?displayProperty=fullName>   
 <xref:System.Data.DataSet?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>
---
title: "CA1308: 문자열을 대문자로 정규화하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1308"
  - "NormalizeStringsToUppercase"
helpviewer_keywords: 
  - "NormalizeStringsToUppercase"
  - "CA1308"
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 11
---
# CA1308: 문자열을 대문자로 정규화하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|NormalizeStringsToUppercase|  
|CheckId|CA1308|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 연산에서 문자열을 소문자로 정규화합니다.  
  
## 규칙 설명  
 문자열은 대문자로 정규화되어야 합니다.  일부 문자는 소문자로 변환될 때 다시 대문자로 변환되지 않습니다.  라운드트립을 발생시킨다는 것은 한 로캘의 문자를 문자 데이터의 표현에 차이가 있는 다른 로캘로 변환한 다음 변환된 문자에서 원본 문자를 정확하게 검색하는 것을 의미합니다.  
  
## 위반 문제를 해결하는 방법  
 문자를 소문자로 변환하는 연산을 변경하여 문자열이 소문자 대신 대문자로 변환되도록 합니다.  예를 들어, `String.ToLower(CultureInfo.InvariantCulture)`를 `String.ToUpper(CultureInfo.InvariantCulture)`로 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 결과를 UI에 표시하는 경우와 같이 결과에 따라 보안을 결정하지 않는 경우 경고 메시지를 표시하지 않도록 설정해도 안전합니다.  
  
## 참고 항목  
 [전역화 경고](../code-quality/globalization-warnings.md)
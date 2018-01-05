---
title: "CA1308: 문자열을 대문자로 정규화 하십시오. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1308
- NormalizeStringsToUppercase
helpviewer_keywords:
- NormalizeStringsToUppercase
- CA1308
ms.assetid: 7e9a7457-3f93-4938-ac6f-1389fba8d9cc
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9064ca9861f609499971b9f5188f5b0006458c15
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1308-normalize-strings-to-uppercase"></a>CA1308: 문자열을 대문자로 정규화하십시오.
|||  
|-|-|  
|TypeName|NormalizeStringsToUppercase|  
|CheckId|CA1308|  
|범주|Microsoft.Globalization|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 작업 문자열을 소문자로 정규화합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 문자열은 대문자로 정규화되어야 합니다. 소규모 그룹의 문자를 소문자로 변환 될, 왕복을 만들 수 없습니다. 라운드트립를 의미 로캘에서 변환 하는 문자 하나를 다른 로캘에서 문자 데이터를 다르게 표시 하 고 정확 하 게 변환된 된 문자에서 원래 문자를 검색 합니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 문자열 변환 되도록 문자열을 소문자로 변환 하는 연산을 변경 대신 대문자로 합니다. 예를 들어 변경 `String.ToLower(CultureInfo.InvariantCulture)` 를 `String.ToUpper(CultureInfo.InvariantCulture)`합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 결과 (예: UI에 표시 하는 경우)에 따라 보안을 결정 하지 않는 경우에 경고 메시지를 표시 하지 않아도 안전 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [전역화 경고](../code-quality/globalization-warnings.md)
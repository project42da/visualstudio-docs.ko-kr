---
title: "CA1701: 리소스 문자열 복합 단어 표기 해야 올바르게 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ResourceStringCompoundWordsShouldBeCasedCorrectly
- CA1701
helpviewer_keywords:
- CA1701
- ResourceStringCompoundWordsShouldBeCasedCorrectly
ms.assetid: 4ddbe09f-24b8-4c47-9373-a06f4487ca0d
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0b4b154d6e959e636ee75481816a2424d5ea2e18
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1701-resource-string-compound-words-should-be-cased-correctly"></a>CA1701: 리소스 문자열 복합 단어는 정확한 대/소문자를 사용해야 합니다.
|||  
|-|-|  
|TypeName|ResourceStringCompoundWordsShouldBeCasedCorrectly|  
|CheckId|CA1701|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경 아님|  
  
## <a name="cause"></a>원인  
 리소스 문자열을 올바르게 대/소문자는 표시 되지 않는 복합 단어를 포함 합니다.  
  
## <a name="rule-description"></a>규칙 설명  
 리소스 문자열의 각 단어는 대/소문자를 기반으로 하는 토큰으로 구분 됩니다. Microsoft 맞춤법 검사 라이브러리에서는 연속된 각 두 토큰의 조합을 검사합니다. 규칙 위반이 인식되면 단어에서 규칙 위반을 작성합니다. 위반이 발생 하는 복합 단어의 예로 "CheckSum" 및 "MultiPart" 각각 "Checksum" 및 "Multipart"으로 표기 해야 합니다. 이전 일반적인 사용으로 인해 몇 가지 예외는 규칙으로 빌드되고 "Toolbar" 및 "Filename"는 두 개의 고유한 단어와 대/소문자, 몇 가지 단일 단어 플래그가 지정. 이 예제는 "ToolBar" 및 "FileName"의 플래그가 지정 합니다.  
  
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 되므로 대/소문자를 올바르게는 단어를 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 복합 단어의 두 파트 맞춤법 사전에서 인식 되 고 두 단어로 사용 하는 것이 규칙에서 경고를 표시 하지 않아도 안전 합니다.  
  
 맞춤법 검사기에 대 한 사용자 지정 사전에 복합 단어를 추가할 수도 있습니다. 사용자 지정 사전에 있는 단어 위반이 발생 하지 않습니다. 자세한 내용은 참조 [하는 방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)합니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1702: 복합 단어는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1702-compound-words-should-be-cased-correctly.md)  
  
 [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
## <a name="see-also"></a>참고 항목  
 [대/소문자 표기 규칙](/dotnet/standard/design-guidelines/capitalization-conventions)   
 [명명 지침](/dotnet/standard/design-guidelines/naming-guidelines)
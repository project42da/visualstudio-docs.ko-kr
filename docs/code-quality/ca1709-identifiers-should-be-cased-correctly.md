---
title: 'CA1709: 식별자 표기 해야 올바르게 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- IdentifiersShouldBeCasedCorrectly
- CA1709
helpviewer_keywords:
- CA1709
- IdentifiersShouldBeCasedCorrectly
ms.assetid: f633d1a7-4ca4-40ae-b207-ec571c5fb083
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c010019c2ae5d1044d11c02c22428dda4197fcd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1709-identifiers-should-be-cased-correctly"></a>CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldBeCasedCorrectly|  
|CheckId|CA1709|  
|범주|Microsoft.Naming|  
|변경 수준|주요-어셈블리, 네임 스페이스, 형식, 멤버 및 매개 변수에서 발생 한 경우입니다.<br /><br /> 주요 변경 아님-제네릭 형식 매개 변수에서 발생 한 경우|  
  
## <a name="cause"></a>원인  
 식별자의 이름 올바르게 소문자 되지 않습니다.  
  
 \- 또는 -  
  
 식별자의 이름이 2 자 약어를 포함 하 고 두 번째 문자가 소문자입니다.  
  
 \- 또는 -  
  
 식별자의 이름에는 3 개 이상의 대문자 머리글자어 포함 되어 있습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 명명 규칙은 공통 된 모양을 라이브러리에 대 한 공용 언어 런타임을 대상으로 합니다. 이렇게 하면 새 소프트웨어 라이브러리에 필요 하 고 관리 되는 코드를 개발에 대 한 전문 지식이 있는 사용자가 라이브러리를 개발 하는 신뢰성이 향상를 배워야 할 필요성이 줄어듭니다.  
  
 규칙에 따라 매개 변수 이름에 카멜식 대/소문자; 사용 네임 스페이스, 형식 및 멤버 이름 사용 파스칼식 대/소문자 구분 합니다. 카멜식 대/소문자를 사용 하는 이름에 첫 번째 문자는 소문자를 구분 하 고 이름에 나머지 단어의 첫 번째 문자는 대문자로 표시 합니다. 카멜식 대/소문자를 사용 하는 이름에는 "packetSniffer", "ioFile" 및 "fatalErrorCode"이 있습니다. 파스칼식 대/소문자를 사용 하는 이름에 첫 글자가 대문자, 고 이름에 나머지 단어의 첫 문자가 대문자입니다. 이름은 파스칼식 대/소문자를 사용의 예로 "PacketSniffer", "IOFile" 및 "FatalErrorCode"입니다.  
  
 이 규칙에서는 이름을 대/소문자에 따라 단어로 분할 하 고 또는 "My"의 "In"와 같은 일반적인 두 문자로 단어의 목록에 대해 두 문자로 단어를 확인 합니다. 일치 하는 항목이 없는 경우 단어는 머리글자어로 간주 됩니다. 또한이 규칙 이름에 포함 한 행에 4 개의 대문자 또는 대문자 이름의 끝에 행 3 머리글자어 발견 가정 합니다.  
  
 규칙에 따라 2 자 약어는 모두 대문자로 사용 하 고 3 개 이상의 문자 머리글자어 사용 파스칼식 대/소문자 구분 합니다. 다음 예에서는 사용이 명명 규칙: 'DB', 'CR', 'Cpa' 및 'Ecma'. 규칙을 위반 하는 다음 예제에서는: 'Io', 'XML' 및 'DoD' 및 들 이름, 'xp' 및 ' c '에 대 한 합니다.  
  
 'ID' 특별 하 게 처리이 규칙을 위반 하는입니다. 'Id'는 머리글자어가 아니라 'identification'의 약어입니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 올바르게 소문자를 사용 하므로 이름을 변경 합니다.  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 식별자는 회사 또는 기술의 이름 예를 들어 적절 한 이름을 나타내는 경우 또는 사용자 지정 명명 규칙을 사용 하는 경우이 경고를 표시 하지 않아도 안전 합니다.  
  
 특정 용어, 약어 및 머리 글자어를 추가할 수도 있습니다를 코드 분석 사용자 지정 사전입니다. 사용자 지정 사전에 지정 된 용어에서이 규칙 위반을 발생 하지 않습니다. 자세한 내용은 참조 [하는 방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
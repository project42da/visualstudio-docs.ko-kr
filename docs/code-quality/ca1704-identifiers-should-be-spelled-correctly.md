---
title: "CA1704: 식별자 철자가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
helpviewer_keywords:
- CA1704
- IdentifiersShouldBeSpelledCorrectly
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 63b10dd1d1037ee90156505f2e73105be7a9ee63
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ca1704-identifiers-should-be-spelled-correctly"></a>CA1704: 식별자에는 정확한 철자를 사용해야 합니다.
|||  
|-|-|  
|TypeName|IdentifiersShouldBeSpelledCorrectly|  
|CheckId|CA1704|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## <a name="cause"></a>원인  
 식별자의 이름에 Microsoft 맞춤법 검사 라이브러리에서 인식 하지 못하는 단어가 하나 이상 있습니다. 이 규칙 생성자 또는 get 같은 특수 한 이름이 지정 된 멤버를 확인 하 고 set 속성 접근자 하지 않습니다.  
  
## <a name="rule-description"></a>규칙 설명  
 이 규칙의 식별자를 토큰으로 구문 분석 하 고 각 토큰의 맞춤법을 검사 합니다. 구문 분석 알고리즘에서는 다음과 같은 변환을 수행합니다.  
  
-   대문자는 새 토큰을 시작 합니다. 예를 들어 "My", "Name", "Is", "Joe" MyNameIsJoe 토큰화합니다.  
  
-   여러 문자가 마지막 대문자는 새 토큰을 시작합니다. 예를 들어 GUIEditor "GUI", "편집기"를 토큰화합니다.  
  
-   선행 및 후행 아포스트로피 제거 됩니다. 예를 들어 "보낸 사람에 게" 'd e r'를 토큰화합니다.  
  
-   밑줄 토큰의 끝을 나타냅니다 하 고 제거 됩니다. "Hello"에 Hello_world 토큰화 하는 예를 들어, "world"입니다.  
  
-   포함 된 앰퍼샌드 제거 됩니다. 예를 들어 for&mat은 "format"으로 토큰화됩니다.  
  
 기본적으로 영어 (en) 버전의 맞춤법 검사기 사용 됩니다. 현재 사용할 수 있는 다른 언어 사전이 없습니다.  
  
## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결 하는 word의 철자를 수정 하거나 CustomDictionary.xml 라는 사용자 지정 사전에 단어를 추가 합니다. 도구를 프로젝트 디렉터리의 설치 디렉터리에서 나 사용자의 프로필 아래에서 도구와 연관 된 디렉터리에 사전 배치할 (%USERPROFILE%\Application 데이터\\...). 사용자 지정 사전 프로젝트에 추가 하는 방법에 알아보려면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 참조 [하는 방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)  
  
-   사전/단어/인식 경로 아래의 위반 인해 발생 하지 않아야 하는 단어를 추가 합니다.  
  
-   사전/단어/알 수 없는 경로 아래의 위반이 발생 해야 하는 단어를 추가 합니다.  
  
-   사전/단어/Deprecated 경로 아래에서 사용 되지 않는으로 플래그 지정 해야 하는 단어를 추가 합니다. 관련된 규칙 항목을 참조 [CA1726: 기본 설정된 용어를 사용 하 여](../code-quality/ca1726-use-preferred-terms.md) 자세한 정보에 대 한 합니다.  
  
-   사전/머리글자어/CasingExceptions 경로에 머리글자어 대/소문자 규칙에 예외를 추가 합니다.  
  
 다음은 사용자 지정 사전 파일의 구조의 예제입니다.  
  
```  
<Dictionary>  
   <Words>  
      <Unrecognized>  
         <Word>cb</Word>  
      </Unrecognized>  
      <Recognized>  
         <Word>stylesheet</Word>  
         <Word>GotDotNet</Word>  
      </Recognized>  
      <Deprecated>  
         <Term PreferredAlternate="EnterpriseServices">ComPlus</Term>  
      </Deprecated>  
   </Words>  
   <Acronyms>  
      <CasingExceptions>  
         <Acronym>CJK</Acronym>  
         <Acronym>Pi</Acronym>  
      </CasingExceptions>  
   </Acronyms>  
</Dictionary>  
```  
  
## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우  
 단어는 의도적으로 맞춤법이 틀린 단어 라이브러리의 제한 된 집합에 적용 됩니다. 경우에이 규칙에서 경고를 표시 합니다. 맞춤법이 단어를 사용 하는 새 소프트웨어 라이브러리에 필요한 배워야 할 필요성이 줄어듭니다.  
  
## <a name="related-rules"></a>관련된 규칙  
 [CA2204: 리터럴의 철자가 맞아야 합니다.](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
 [CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
 [CA1709: 식별자는 정확한 대/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: 식별자에는 밑줄을 사용할 수 없습니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1726: 기본 설정 용어를 사용하십시오.](../code-quality/ca1726-use-preferred-terms.md)  
  
## <a name="see-also"></a>참고 항목  
 [방법: 코드 분석 사전 사용자 지정](../code-quality/how-to-customize-the-code-analysis-dictionary.md)

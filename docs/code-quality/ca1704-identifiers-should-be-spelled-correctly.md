---
title: "CA1704: 식별자에는 정확한 철자를 사용해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1704"
  - "IdentifiersShouldBeSpelledCorrectly"
helpviewer_keywords: 
  - "CA1704"
  - "IdentifiersShouldBeSpelledCorrectly"
ms.assetid: f2c7a44d-1690-44ca-9cd0-681b04b12b2a
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 25
---
# CA1704: 식별자에는 정확한 철자를 사용해야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|IdentifiersShouldBeSpelledCorrectly|  
|CheckId|CA1704|  
|범주|Microsoft.Naming|  
|변경 수준|주요 변경|  
  
## 원인  
 식별자의 이름에 Microsoft 맞춤법 검사 라이브러리에서 인식하지 못하는 단어가 하나 이상 있습니다.  이 규칙은 get 및 set 속성 접근자 같은 특수한 이름의 멤버나 생성자를 검사하지 않습니다.  
  
## 규칙 설명  
 이 규칙은 식별자를 토큰으로 구문 분석하고 각 토큰의 맞춤법을 검사합니다.  구문 분석 알고리즘은 다음과 같은 변환을 수행합니다.  
  
-   대문자는 새 토큰을 시작합니다.  예를 들어 MyNameIsJoe는 "My", "Name", "Is", "Joe"로 토큰화됩니다.  
  
-   대문자가 여러 개인 경우 마지막 대문자는 새 토큰을 시작합니다.  예를 들어 GUIEditor는 "GUI", "Editor"로 토큰화됩니다.  
  
-   앞과 뒤의 아포스트로피가 제거됩니다.  예를 들어 'sender'는 "sender"로 토큰화됩니다.  
  
-   밑줄은 토큰의 끝을 의미하고 이후에 제거됩니다.  예를 들어 Hello\_world는 "Hello", "world"로 토큰화됩니다.  
  
-   포함된 앰퍼샌드는 제거됩니다.  예를 들어 for&은 "format"으로 토큰화됩니다.  
  
 기본적으로 영어 버전의 맞춤법 검사기가 사용됩니다.  현재 사용할 수 있는 다른 언어 사전은 없습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 단어의 맞춤법을 수정하거나 해당 단어를 CustomDictionary.xml이라는 사용자 지정 사전에 추가합니다.  사전을 도구의 설치 디렉터리, 프로젝트 디렉터리 또는 도구와 연결된 사용자 프로파일\(%USERPROFILE%\\Application Data\\...\) 아래의 디렉터리에 저장합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트에 사용자 지정 사전을 추가하는 방법을 보려면 [방법: 코드 분석 사전 사용자 지정](../Topic/How%20to:%20Customize%20the%20Code%20Analysis%20Dictionary.md)를 참조하십시오.  
  
-   규칙을 위반하지 않는 단어를 Dictionary\/Words\/Recognized 경로 아래에 추가합니다.  
  
-   규칙을 위반하는 단어를 Dictionary\/Words\/Unrecognized 경로 아래에 추가합니다.  
  
-   사용되지 않음으로 플래그가 지정된 단어를 Dictionary\/Words\/Deprecated 경로 아래에 추가합니다.  자세한 내용은 관련 규칙 항목 [CA1726: 기본 설정 용어를 사용하십시오.](../code-quality/ca1726-use-preferred-terms.md)를 참조하십시오.  
  
-   머리글자어 대\/소문자 규칙에 대한 예외를 Dictionary\/Acronyms\/CasingExceptions 경로에 추가합니다.  
  
 다음은 사용자 지정 사전 파일 구조의 예입니다.  
  
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
  
## 경고를 표시하지 않는 경우  
 단어의 맞춤법을 일부러 잘못 쓴 경우 및 단어를 라이브러리의 제한된 설정에 적용하는 경우에만 이 규칙에서 경고를 표시하지 마십시오.  맞춤법이 올바른 단어를 사용하면 새 소프트웨어 라이브러리에 익숙해지는 데 필요한 학습 기간이 줄어듭니다.  
  
## 관련 규칙  
 [CA2204: 리터럴의 철자가 맞아야 합니다.](../code-quality/ca2204-literals-should-be-spelled-correctly.md)  
  
 [CA1703: 리소스 문자열에는 정확한 철자를 사용해야 합니다.](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)  
  
 [CA1709: 식별자는 정확한 대\/소문자를 사용해야 합니다.](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708: 식별자에는 대\/소문자만 다른 이름을 사용할 수 없습니다.](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)  
  
 [CA1707: 식별자에는 밑줄을 사용할 수 없습니다.](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)  
  
 [CA1726: 기본 설정 용어를 사용하십시오.](../code-quality/ca1726-use-preferred-terms.md)  
  
## 참고 항목  
 [방법: 코드 분석 사전 사용자 지정](../Topic/How%20to:%20Customize%20the%20Code%20Analysis%20Dictionary.md)
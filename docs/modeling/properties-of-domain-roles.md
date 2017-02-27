---
title: "도메인 역할의 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a7bb18c-638e-45e8-9d79-9aa6a9e14b0e
caps.latest.revision: 9
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 9
---
# 도메인 역할의 속성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다음 표의 도메인 역할에 연결 됩니다.  도메인 역할에 대 한 자세한 내용은 [모델, 클래스 및 관계 이해](../modeling/understanding-models-classes-and-relationships.md).  이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Property|설명|Default|  
|--------------|--------|-------------|  
|컬렉션 형식|복합성이 0이 역할에 있는 경우. \* 또는 1.. \*, 링크의 컬렉션을 저장 하는 데 사용 되는 제네릭 형식을이 속성을 사용자 정의 합니다.|`(none)` \- <xref:Microsoft.VisualStudio.Modeling.LinkedElementCollection%601> is used|  
|사용자 지정 특성|여기에서 지정 하는 속성 특성으로 생성 된 코드를 클래스에 추가 됩니다.|\<none\>|  
|속성을 찾을 수 있습니다.|경우 `True`, 및 관계의 복합성은 0에서 1까지 또는 1 인 경우 역할 속성에는 사용자가 찾아볼 수 있는  **속성** 창입니다.  속성 요소의 이름을 관계 연결의 다른 쪽 끝을 표시합니다.|`True`|  
|생성기 속성입니다.|경우 `True`, 관계에서 프로그램 코드를 통과 하는 데 사용할 수 있는 역할, 역할 속성이 생성 됩니다.  이 false로 설정 하면 도메인 관계의 정적 메서드를 사용 하 여 보다 효율적인 방식으로 관계를 탐색할 수 있습니다.|`True`|  
|속성 Getter 액세스 한정자|생성 된 속성의 getter의 액세스 한정자 \(`public`, `internal`, `private`, `protected`, 또는 `protected internal`\).|`public`|  
|속성 Setter의 액세스 한정자|생성 된 속성에 setter의 액세스 한정자 \(`public`, `internal`, `private`, `protected`, 또는 `protected internal`\).|`public`|  
|복합성|반대 역할을 재생할 수 있는 모델 요소 수 \(`0..1`, `1..1`, `0..*`, 또는 `1..*`\).  복합성 인 경우 `0..*` 또는 `1..*`, 컬렉션입니다; 생성 된 속성을 나타내는 다음 그렇지 않으면 생성 된 속성은 단일 모델 요소를 나타냅니다.|관계 형식에 따라 다릅니다 및 원본 또는 대상 역할 관계에 상관 없이.|  
|Name|도메인 역할의 이름입니다.  이 속성에 공백을 포함할 수 없습니다.|이 역할에 대 한 역할 수행자의 도메인 클래스의 이름입니다.|  
|복사본에 전파|`DoNotPropagateCopy`\-복사 역할 플레이어 없음이 링크를 복사를 해야 합니다.<br /><br /> `PropagateCopyToLinkOnly`반대 역할 수행자의 기존\-복사 연결 지점입니다.<br /><br /> `PropagateCopyToLinkAndOppositeRolePlayer` \-복사한 링크 반대 역할 수행자의 복사본에 연결 됩니다.|`PropagateCopyToLinkAndOppositeRolePlayer`포함 원본 역할을 합니다.<br /><br /> `DoNotPropagateCopy`다른 역할을 합니다.<br /><br /> 자세한 내용은 [복사 동작 사용자 지정](../modeling/customizing-copy-behavior.md)를 참조하십시오.|  
|삭제를 전파합니다.|`True`연결 된 링크를 삭제 하면이 역할을 수행 하는 요소를 삭제.|`True`에 대 한 대상 포함 하는 역할입니다.<br /><br /> `False`다른 역할을 합니다.<br /><br /> 자세한 내용은 [삭제 동작 사용자 지정](../modeling/customizing-deletion-behavior.md)를 참조하십시오.|  
|속성 이름|생성 된 역할 수행자의 코드에는 속성의 이름입니다.  이 이름에는 공백을 포함할 수 없습니다.|0\-에\-하나가이 역할에 있는 경우에 반대 역할의 이름 또는 일대일 복합성. 그렇지 않으면 pluralized 반대 역할의 이름입니다.|  
|역할 수행자|도메인 클래스는 관계에서이 역할을 재생할 수 있는 요소입니다.  이 속성은 읽기 전용입니다.|이 역할에는 역할 수행자의 도메인 클래스입니다.|  
|참고|도메인 역할에 연결 된 메모 비공식 수 있습니다.|\<none\>|  
|범주|범주에서 생성 된 속성 표시에  **속성이** 생성 된 디자이너 창에서에서.  이 속성이 비어 있으면 생성 된 속성 표시를  **기타** 범주|\<none\>|  
|설명|코드를 문서화 하는 데 사용 하 고 생성 된 디자이너 UI에 사용 되는 설명입니다.<br /><br /> Intellisense 도구 설명 역할 플레이어 클래스에서 생성 된 속성에 대 한 설명이 표시 됩니다.|`Description for` *역할의 전체 이름*|  
|표시 이름|도메인 역할에 대해 생성 된 디자이너에 표시 되는 이름입니다.|Name 속성의 조정 된 값입니다.|  
|도움말 키워드입니다.|도메인 역할에 대 한 F1 도움말 색인을 사용 하는 선택적 키워드입니다.|\<none\>|  
|속성 표시 이름|생성 된 역할 속성에 대해 생성 된 디자이너에 표시 되는 이름입니다.|속성 이름의 속성의 조정 된 값입니다.|  
  
> [!NOTE]
>  기본값의 표시 이름에 소문자 문자 앞에는 다른 대문자 문자가 표시 되지 않는 각 대문자 문자 앞에 공백을 삽입 하 여 연결 된 속성 값을 기반으로 합니다.  
  
## 참고 항목  
 [도메인 관계의 속성](../modeling/properties-of-domain-relationships.md)
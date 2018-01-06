---
title: "도메인 역할의 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7bb18c-638e-45e8-9d79-9aa6a9e14b0e
caps.latest.revision: "9"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 9da6a64eafa28ac173e4dd64b38d1e64d9639e34
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-of-domain-roles"></a>도메인 역할의 속성
다음 표에 있는 속성 도메인 역할 연관 됩니다. 도메인 역할에 대 한 정보를 참조 하십시오. [이해 모델, 클래스 및 관계](../modeling/understanding-models-classes-and-relationships.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|컬렉션 형식|이 역할에 복합성 0.. * 또는 1... \*,이 속성의 링크 컬렉션을 저장 하는 데 사용 되는 제네릭 형식에 맞게 사용자 지정 합니다.|`(none)` - <xref:Microsoft.VisualStudio.Modeling.LinkedElementCollection%601>사용|  
|사용자 지정 특성|여기에서 지정 하는 특성 생성된 코드 클래스를 특성으로 추가 됩니다.|< 없음\>|  
|속성을 검색할 수 있습니까|경우 `True`, 관계의 복합성이 0..1 또는 1.. 1 인 경우 역할 속성에서 사용자가 탐색할 수 있습니다는 **속성** 창. 속성 관계 링크의 다른 쪽 끝에서 요소의 이름을 표시합니다.|`True`|  
|속성 생성기|경우 `True`, 프로그램 코드에서 관계를 통과 하는 데 사용할 수 있는이 역할에 대 한 역할 속성이 하나씩 생성 됩니다. 이 false를 설정한 경우에 도메인 관계의 정적 메서드를 사용 하 여 덜 효율적인 방식으로 관계를 이동할 수 있습니다.|`True`|  
|속성 Getter의 액세스 한정자|생성 된 속성에 대 한 getter에 대 한 액세스 한정자 (`public`, `internal`, `private`, `protected`, 또는 `protected internal`).|`public`|  
|속성 Setter의 액세스 한정자|생성 된 속성의 setter에 대 한 액세스 한정자 (`public`, `internal`, `private`, `protected`, 또는 `protected internal`).|`public`|  
|복합성|반대 역할을 재생할 수 있는 모델 요소 수 (`0..1`, `1..1`, `0..*`, 또는 `1..*`). 복합성 이면 `0..*` 또는 `1..*`, 다음 생성 된 속성 컬렉션을 나타냅니다; 그렇지 않으면, 생성 된 속성 단일 모델 요소를 나타냅니다.|관계 유형에 따라 여부는 관계의 원본 또는 대상 역할입니다.|  
|name|도메인 역할의 이름입니다. 이 속성에 공백을 포함할 수 없습니다.|이 역할에 대 한 역할 수행자의 도메인 클래스의 이름입니다.|  
|복사를 전파합니다.|`DoNotPropagateCopy`-복사 된 역할 수행자가이 링크의 없는 복사본을 가지게 됩니다.<br /><br /> `PropagateCopyToLinkOnly`-복사 된 링크는 기존 반대 역할 수행자를 가리킵니다.<br /><br /> `PropagateCopyToLinkAndOppositeRolePlayer`-복사 된 링크 반대 역할 수행자의 복사본을 가리킵니다.|`PropagateCopyToLinkAndOppositeRolePlayer`포함의 소스 역할을 지정 합니다.<br /><br /> `DoNotPropagateCopy`다른 역할입니다.<br /><br /> 자세한 내용은 참조 [복사 동작을 사용자 지정](../modeling/customizing-copy-behavior.md)|  
|삭제를 전파합니다.|`True`연결 된 링크가 삭제 될 때이 역할을 수행 하는 요소를 삭제 합니다.|`True`에 대 한 포함 된 역할의 대상입니다.<br /><br /> `False`다른 역할입니다.<br /><br /> 자세한 내용은 참조 [삭제 동작 사용자 지정](../modeling/customizing-deletion-behavior.md)합니다.|  
|속성 이름|역할 수행자의 코드에서 생성 된 속성의 이름입니다. 이 이름은 공백을 포함할 수 없습니다.|이 역할에는 0-1 경우 반대 역할의 이름 또는 일대일 복합성; 그렇지 않으면 pluralized 반대 역할의 이름입니다.|  
|역할 수행자|도메인 클래스 관계에서이 역할을 수행 하는 요소입니다. 이 속성은 읽기 전용입니다.|이 역할에 대 한 역할 수행자의 도메인 클래스입니다.|  
|노트|도메인 역할 연관 된 비공식 메모 합니다.|< 없음\>|  
|범주|생성 된 속성에 표시 되는 범주는 **속성** 생성 된 디자이너의 창. 이 속성이 비어 있으면 생성 된 속성 아래에 표시 된 **기타** 범주|< 없음\>|  
|설명|코드를 작성 하는 데 사용 되 고 생성 된 디자이너의 UI에 사용 되는 설명입니다.<br /><br /> 설명은 역할 플레이어 클래스에서 생성 된 속성에 대 한 Intellisense 도구 설명에 나타납니다.|`Description for`*역할의 전체 이름*|  
|표시 이름|도메인 역할에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|Name 속성의 조정 된 값입니다.|  
|Help Keyword|도메인 역할에 대 한 F1 도움말을 인덱싱하는 데 사용할 optional 키워드|\<없음 >|  
|속성 표시 이름|생성 된 역할 속성에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|속성 이름 속성의 조정 된 값입니다.|  
  
> [!NOTE]
>  표시 이름의 기본값은 소문자 문자 앞 하 고 다른 대문자 문자가 나오지 않습니다 각 대문자 문자 앞에 공백을 삽입 하 여 연결된 된 속성 값을 기반으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [도메인 관계의 속성](../modeling/properties-of-domain-relationships.md)
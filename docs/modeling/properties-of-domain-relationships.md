---
title: 도메인 관계의 속성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain relationships
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 6cc2da3665dcf6b5d5ba07fad53c6246c04709cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="properties-of-domain-relationships"></a>도메인 관계의 속성
다음 표에 있는 속성 도메인 관계와 연결 됩니다. 도메인 관계에 대 한 정보를 참조 하십시오. [이해 모델, 클래스 및 관계](../modeling/understanding-models-classes-and-relationships.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|액세스 한정자|도메인 관계의 액세스 수준 (`public` 또는 `internal`).|`public`|  
|사용자 지정 특성|도메인 관계에서 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<없음 >|  
|Double 생성 파생|경우 `True`, 기본 클래스 및 (재정의 통해 사용자 지정은 지원) 하는 partial 클래스를 모두 생성 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|`False`|  
|사용자 지정 생성자|경우 `True`, 사용자 지정 생성자의 소스 코드에서 제공 됨을 나타냅니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|`False`|  
|상속 한정자|도메인 관계에서 생성 되는 소스 코드 클래스의 상속의 종류를 설명 (`none`, `abstract` 또는 `sealed`).|\<없음 >|  
|중복 허용|경우 `True`, 동일한 두 요소 사이의 도메인 관계의 중복 연결을 만들 수 있습니다.|`False`|  
|기본 관계|도메인 관계 파생 되는 경우 도메인 관계의 기본 관계입니다.|\<없음 >|  
|포함 하는|경우 `True`, 도메인 포함 관계입니다. 경우 `False`, 참조 관계입니다.|\<둘 다 >|  
|이름|도메인 관계의 이름입니다.|현재 이름|  
|네임스페이스|도메인 관계와 연결 되어 있는 네임 스페이스입니다.|현재 네임 스페이스|  
|노트|도메인 관계와 관련 된 비공식 메모 합니다.|\<없음 >|  
|설명|코드를 작성 하는 데 사용 되 고 생성 된 디자이너의 UI에 사용 되는 설명입니다.|\<없음 >|  
|표시 이름|도메인 관계에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|\<없음 >|  
|Help Keyword|도메인 관계에 대 한 F1 도움말을 인덱싱하는 데 사용할 optional 키워드|\<없음 >|  
  
## <a name="see-also"></a>참고 항목  
 [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
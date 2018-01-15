---
title: "커넥터의 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, connectors
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 7874e3017c714f41a660f96bedbb126fe121086e
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="properties-of-connectors"></a>연결선의 속성
커넥터 생성 된 디자이너에서 도메인 관계를 나타냅니다.  
  
 자세한 내용은 참조 [도메인 특정 언어를 정의 하는 방법을](../modeling/how-to-define-a-domain-specific-language.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
 커넥터는 다음 표에 나열 된 속성이 있습니다.  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|색|이 커넥터의 색입니다.|검정|  
|대시 스타일|(실선, 파선, 점, DashDot, 이점 쇄선, 또는 사용자 지정)이이 커넥터에 대 한 선의 대시 스타일입니다.|단색|  
|소스 끝 스타일|이 커넥터 (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond, 또는 없음)에 대 한 소스 끝 스타일입니다.|없음|  
|대상 끝 스타일|이 커넥터 (HollowArrow, EmptyArrow, FilledArrow, EmptyDiamond, FilledDiamond, 또는 없음)에 대 한 대상 끝 스타일입니다.|없음|  
|텍스트 색|이 커넥터와 관련 된 텍스트 데코레이터에 사용 되는 색입니다.|검정|  
|Thickness|이 커넥터에 대 한 선의 두께 인치 단위로 지정 합니다.|0.03125|  
|액세스 한정자|클래스의 액세스 수준 (`public` 또는 `internal`).|Public|  
|사용자 지정 특성|이 커넥터에서 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<없음 >|  
|Double 생성 파생|경우 `True`, 기본 클래스 및 (재정의 통해 사용자 지정은 지원) 하는 partial 클래스를 모두 생성 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|False|  
|사용자 지정 생성자|경우 `True`, 사용자 지정 생성자의 소스 코드에서 제공 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|False|  
|상속 한정자|커넥터에서 생성 되는 소스 코드 클래스의 상속의 종류를 설명 (`none`, `abstract` 또는 `sealed`).|없음|  
|기본 커넥터|이 커넥터의 기본 클래스입니다.|(없음)|  
|name|이 커넥터의 이름입니다.|현재 이름|  
|네임스페이스|이 커넥터와 연결 되어 있는 네임 스페이스입니다.|현재 네임 스페이스|  
|도구 설명 형식|도구 설명 (고정, 변수 또는 없음) 정의 되는 방식입니다. 다음의 값을 고정 하는 경우는 `Fixed Tooltip Text` 변수인 경우 다음 도구 설명에에서 정의 되어 사용자 지정 코드; 속성은 도구 설명으로 사용 합니다.|\<없음 >|  
|노트|이 커넥터와 관련 된 비공식 정보입니다.|\<없음 >|  
|경로 스타일|커넥터를 라우팅에 사용 되는 스타일입니다. A `Rectilinear` 직각 turns; 필요에 따라 커넥터를 사용 하면 한 `Straight` 커넥터는 그렇지 않습니다.|직선|  
|속성으로 노출 된 색<br /><br /> 속성으로 노출 된 대시 스타일<br /><br /> 속성으로 노출 된 두께<br /><br /> 텍스트 색을 노출합니다.|경우 `True`, 사용자는 도형의 명시 된 속성을 설정할 수 있습니다. 이 설정 하려면 셰이프 정의 마우스 오른쪽 단추로 클릭 하 고 클릭 **노출 추가**합니다.|False|  
|설명|생성 된 디자이너를 문서화 하는 데 사용 합니다.|\<없음 >|  
|표시 이름|이 커넥터에 대 한 생성 된 디자이너에 표시 되는 이름입니다.|\<없음 >|  
|도구 설명 텍스트를 고정된|고정 된 도구 설명에 사용 되는 텍스트입니다.|\<없음 >|  
|Help Keyword|이 요소에 대 한 F1 도움말을 인덱싱하는 데 사용 되는 키워드입니다.|\<없음 >|  
  
## <a name="see-also"></a>참고 항목  
 [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)
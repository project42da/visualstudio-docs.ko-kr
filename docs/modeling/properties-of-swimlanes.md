---
title: "스윔 레인의 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.swimlane
helpviewer_keywords:
- Domain-Specific Language, swimlane
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 39bb6be4146cf7e9e163b6da5ada6f447a930bc8
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="properties-of-swimlanes"></a>스윔 레인의 속성
스윔 레인은 다이어그램에 추가할 수 있습니다. 스윔 레인을 수직 또는 수평 영역으로 다이어그램을 나눕니다. 다른 셰이프 스윔 레인 내에 표시를 정의할 수 있습니다. 자세한 내용은 참조 [도메인 특정 언어를 정의 하는 방법을](../modeling/how-to-define-a-domain-specific-language.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인 특정 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
 스윔 레인은 다음 표에 나열 된 속성이 있습니다.  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|본문의 채우기 색|본문은 스윔 레인의 채우기 색입니다.|하얀|  
|헤더의 채우기 색|스윔 레인의 헤더에 대 한 채우기 색입니다.|DarkGray|  
|구분 기호 색|색 구분 기호 선입니다.|LightGray|  
|구분 기호 선 스타일|구분 기호 선 스타일 (`Solid`, `Dash`, `Dot`, `DashDot`, `DashDotDot`, 또는 `Custom`).|`Dash`|  
|구분 기호 두께|인치 단위 구분 기호 선 두께입니다.|0.03125|  
|텍스트 색|이 스윔 레인에 연관 된 텍스트 데코레이터에 사용 되는 색입니다.|검정|  
|액세스 한정자|클래스의 액세스 수준 (`public` 또는 `internal`).|Public|  
|사용자 지정 특성|이 스윔 레인에서 생성 되는 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<none>|  
|Double 생성 파생|경우 `True`, 기본 클래스 및 (재정의 통해 사용자 지정은 지원) 하는 partial 클래스를 모두 생성 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|False|  
|사용자 지정 생성자|경우 `True`, 사용자 지정 생성자의 소스 코드에서 제공 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|False|  
|상속 한정자|스윔 레인에서 생성 되는 소스 코드 클래스의 상속의 종류를 설명 (`none`, `abstract` 또는 `sealed`).|없음|  
|기본 스윔 레인|이 스윔 레인의 기본 클래스입니다.|(없음)|  
|name|이 스윔 레인의 이름입니다.|현재 이름|  
|네임스페이스|이 스윔 레인와 연결 되어 있는 네임 스페이스입니다.|현재 네임 스페이스|  
|도구 설명 형식|도구 설명을 정의 되는 방식 (`fixed`, `variable`, 또는 `none`). 경우 `fixed`의 값은 `Fixed Tooltip Text` 속성은 사용할; `variable`, 도구 설명 사용자 지정 코드에 정의 된 다음 합니다.|\<none>|  
|노트|이 스윔 레인에 연관 된 비공식 정보입니다.|\<none>|  
|맞춤|가로 또는 세로 맞춤입니다.|세로|  
|초기 높이|인치에서이 스윔 레인의 초기 높이입니다. 가로 스윔 레인에만 적용 가능 합니다.|0|  
|초기 너비|인치에서이 스윔 레인의 초기 너비입니다. 세로 스윔 레인에만 적용 가능 합니다.|0|  
|텍스트 색을 노출합니다.|경우 `True`, 사용자 생성 된 디자이너에서 스윔 레인의 색을 설정할 수 있습니다. 이 설정 하려면 스윔 레인 셰이프를 마우스 오른쪽 단추로 클릭 하 고 클릭 **노출 추가**합니다.|False|  
|설명|생성 된 디자이너를 문서화 하는 데 사용 합니다.|\<none>|  
|표시 이름|이 스윔 레인 클래스를 참조 하는 생성 된 디자이너에 표시 되는 이름입니다.|\<none>|  
|도구 설명 텍스트를 고정된|고정 된 도구 설명에 사용 되는 텍스트입니다.|\<none>|  
|Help Keyword|이 스윔 레인에 대 한 F1 도움말을 인덱싱하는 데 사용 되는 키워드입니다.|\<none>|  
  
## <a name="see-also"></a>참고 항목  
 [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
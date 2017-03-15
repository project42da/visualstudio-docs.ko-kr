---
title: "기 하 도형의 속성 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.geometryshape
helpviewer_keywords:
- Domain-Specific Language, geometry shape
ms.assetid: 3993a23e-eab3-4ceb-b475-c395d5992bfc
caps.latest.revision: 21
author: alancameronwills
ms.author: awills
manager: douge
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 54e600e5d626828824d5a2584e1ff4f7fdc09810
ms.lasthandoff: 02/22/2017

---
# <a name="properties-of-geometry-shapes"></a>기하 도형의 속성
도메인 클래스의 인스턴스는 도메인별 언어로 표시 되는 방법을 지정 하려면 기 하 도형에 사용할 수 있습니다. 자세한 내용은 참조 [도메인별 언어를 정의 하는 방법을](../modeling/how-to-define-a-domain-specific-language.md)합니다. 이러한 속성을 사용 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 및 도메인별 언어 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)합니다.  
  
 기 하 도형은 다음 표에 나열 된 속성이 있습니다.  
  
|속성|설명|기본|  
|--------------|-----------------|-------------|  
|채우기 색|이 셰이프의 채우기 색입니다.|White|  
|채우기 그라데이션 모드|이 셰이프 (가로, 세로, 앞으로 대각선, 이전 버전과 대각선, 또는 없음)의 채우기 그라데이션 모드입니다.|가로|  
|기하 도형|(사각형, 둥근 사각형, 타원 또는 원)이 셰이프의 기하학입니다.|사각형|  
|가 기본 연결 지점|경우 `True`, 셰이프 사용 하 여 위쪽, 아래쪽, 왼쪽, 고 생성된 된 디자이너에서 적절 한 연결 지점을 합니다.|False|  
|윤곽선 색|이 셰이프의 윤곽선 색을 지정 합니다.|검정|  
|개요 대시 스타일|이 셰이프 (단색, 대시, 점, DashDot, 이점 쇄선, 또는 사용자 지정)의 개요 대시 스타일입니다.|단색|  
|윤곽선 두께|이 셰이프의 윤곽선 두께입니다.|0.03125|  
|텍스트 색|이 셰이프와 연결 된 텍스트 decorator에 사용 되는 색입니다.|검정|  
|액세스 한정자|(공용 또는 내부) 클래스의 액세스 한정자입니다.|Public|  
|사용자 지정 특성|이 셰이프에 대해 생성 되는 소스 코드 클래스에 특성을 추가 하는 데 사용 합니다.|\<없음 >|  
|이중 생성 파생|경우 `True`, 기본 클래스와 (재정의 통해 사용자 지정을 지원) 하는 partial 클래스를 모두 생성 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|False|  
|사용자 지정 생성자|경우 `True`, 사용자 지정 생성자의 소스 코드에 제공 됩니다. 자세한 내용은 참조 [재정의 및 생성 된 클래스를 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.|False|  
|상속 한정자|도형에서 생성 되는 소스 코드 클래스의 상속의 종류를 설명 (`none`, `abstract` 또는 `sealed`).|없음|  
|기본 기 하 도형|이 셰이프의 기본 클래스입니다.|(없음)|  
|이름|이 셰이프의 이름입니다.|현재 이름|  
|네임스페이스|이 셰이프와 연결 되어 있는 네임 스페이스입니다.|현재 네임 스페이스|  
|도구 설명 형식|도구 설명 (고정, 변수 또는 없음) 정의 되는 방식입니다. 다음의 값을 고정 하는 경우는 `Fixed Tooltip Text` 속성은 도구 설명으로 사용, 변수인 경우 다음 도구 설명에 표시할 코드에 정의 된 사용자 지정 합니다.|없음|  
|노트|이 요소와 관련 된 비공식적인 참고 사항입니다.|\<없음 >|  
|초기 높이|이 셰이프를 인치 단위로 초기 높이입니다.|1|  
|초기 너비|이 셰이프의 인치에서 초기 너비입니다.|1.5|  
|속성으로 노출 된 채우기 색<br /><br /> 노출 된 채우기 그라데이션 모드<br /><br /> 윤곽선 색 속성으로 노출<br /><br /> 개요 대시 스타일 속성으로 노출<br /><br /> 윤곽선 두께 속성으로 노출합니다.<br /><br /> 텍스트 색을 노출합니다.|경우 `True`, 사용자는 도형의 명시 된 속성을 설정할 수 있습니다. 이 설정 하려면 모양 정의 마우스 오른쪽 단추로 클릭 하 고 클릭 **Add Exposed**합니다.|False|  
|설명|생성된 된 디자이너를 문서화 하는 데 사용 되는 설명입니다.|\<없음 >|  
|표시 이름|이 셰이프에 대 한 생성된 된 디자이너에 표시 될 이름입니다.|\<없음 >|  
|도구 설명 텍스트를 고정된|고정 된 도구 설명에 사용 되는 텍스트입니다.|\<없음 >|  
|Help Keyword|이 셰이프에 대 한 F1 도움말을 인덱스에 사용 되는 키워드입니다.|\<없음 >|  
  
## <a name="see-also"></a>참고 항목  
 [도메인별 언어 도구 용어집](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)

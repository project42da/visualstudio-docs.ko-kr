---
title: "분석 및 아키텍처 모델 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- Visual Studio Ultimate, exploring code
- Visual Studio Ultimate, visualizing code
- diagrams - modeling
- Visual Studio ALM, modeling
- application, design
- architecture
- code visualization
- application design
- applications, architecture
- code exploration
- Visual Studio ALM, exploring code
- modeling
- application architecture
- application, modeling
- applications, modeling
- architecture [Visual Studio ALM], modeling
- application modeling
- Visual Studio Ultimate, modeling
- architecture [Visual Studio Ultimate], modeling
- application, architecture
- Visual Studio ALM, visualizing code
- applications, designing
ms.assetid: c9f04cfa-72bd-419d-a952-616eed01472e
caps.latest.revision: 127
author: alexhomer1
ms.author: ahomer
manager: douge
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 98d1214d1cda81102f9e03a8ce8b83886aa2c0ec
ms.openlocfilehash: 78217396085aa5531ec2cbdd5dff522201287777
ms.lasthandoff: 02/22/2017

---
# <a name="analyze-and-model-your-architecture"></a>아키텍처 분석 및 모델링
응용 프로그램 모델링 디자인 하 고 응용 프로그램을 모델링 하는 도구 및 Visual Studio 아키텍처를 사용 하 여 아키텍처 요구 사항을 충족 하는지 확인 합니다. 

* Visual Studio를 사용하여 코드의 구조, 동작 및 관계를 시각화하는 방식으로 기존 프로그램 코드를 더 쉽게 이해할 수 있습니다. 

* 아키텍처 종속성을 유지 하는 것에 대 한 필요성에 팀을 교육 합니다.  
  
* 개발 프로세스의 일부로 응용 프로그램 수명 주기 전체에 걸쳐 다양한 상세 수준으로 모델을 만듭니다.

참조 [시나리오: 모델링 및 시각화를 사용 하 여 디자인 변경](../modeling/scenario-change-your-design-using-visualization-and-modeling.md)합니다.  
  
## <a name="to"></a>대상  
  
|||  
|-|-|  
|**코드 시각화**:<br /><br /> -코드 맵을 만들어서 코드의 구조와 관계 참조 하십시오. 어셈블리, 네임스페이스, 클래스, 메서드 간의 종속성을 시각화합니다.<br />-코드에서 클래스 다이어그램을 만들어서 클래스 구조 및 특정 프로젝트에 대 한 멤버 참조 하십시오.<br />-코드 유효성을 검사 하는 종속성 다이어그램을 만들어서 코드와 디자인 간의 충돌을 찾습니다.|-   [코드 시각화](../modeling/visualize-code.md)<br />-   [작업 클래스 및 기타 형식 (클래스 디자이너)](../ide/working-with-classes-and-other-types-class-designer.md)<br />-   [비디오: 코드 맵 Visual Studio 2015를 사용 하 여 코드의 디자인 이해](https://channel9.msdn.com/Events/Visual-Studio/Connect-event-2015/502)<br />-   [비디오: 실시간으로 아키텍처 종속성의 유효성을 검사합니다](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)|  
|**아키텍처 정의**:<br /><br /> -정의 하 고 종속성 다이어그램을 만들어서 코드 구성 요소 간의 종속성에 제약 조건을 적용 합니다.|-   [비디오: Visual Studio (채널 9)와 종속성을 아키텍처의 유효성을 검사합니다](https://channel9.msdn.com/Events/Connect/2016/170)|  
|**요구 사항 사용 하 여 시스템의 유효성을 검사 및 계획 된 디자인:**<br /><br /> -의도 한 아키텍처를 설명 하는 종속성 다이어그램을 코드 종속성의 유효성을 검사 하 고 설계와 충돌할 수 있는 변경 하지 못하도록 합니다.|-   [비디오: Visual Studio (채널 9)와 종속성을 아키텍처의 유효성을 검사합니다](https://channel9.msdn.com/Events/Connect/2016/170)|  
|**Team Foundation 버전 제어를 사용하여 모델, 다이어그램 및 코드 맵 공유**:<br /><br /> -코드 맵, 프로젝트 및 입력 deoendency 다이어그램 Team Foundation 버전 제어에서 공유할 수 있습니다.|Team Foundation 버전 제어에서 이들 항목을 사용하는 여러 사용자가 있으면 지침에 따라 버전 제어 문제를 방지합니다.<br /><br /> -   [버전 제어에서 모델 및 그래프 관리](../modeling/manage-models-and-diagrams-under-version-control.md)|  
|**모델 및 다이어그램 사용자 지정**:<br /><br /> 고유한 도메인별 언어 만들기.|-   [Visual Studio-도메인별 언어에 대 한 모델링 SDK](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|  
|**T4 템플릿을 사용하여 텍스트 생성**:<br /><br /> -텍스트 기반 파일을 생성 하도록 텍스트 블록 및 제어 논리 템플릿의 내부 사용 합니다.<br /> -Visual Studio에 포함 하는 MSBuild 사용 하 여 T4 템플릿 빌드|-   [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)|

각 기능을 지 원하는 Visual Studio의 버전을 확인 하려면 참조 [아키텍처 및 모델링 도구에 대 한 버전 지원](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)  
  
## <a name="types-of-models-and-their-uses"></a>모델 형식 및 해당 용도  
  
|**모델 형식 및 일반적인 용도**|  
|-------------------------------------|  
|**코드 맵**<br /><br /> 코드 맵을 통해 코드의 구성과 관계를 확인할 수 있습니다.<br /><br /> 일반적인 용도:<br /><br /> --프로그램 코드를 검사 하는 중 업데이트 및 비용을 예측 하는 방법을 제안 된 변경의 구조와 해당 종속성이 알 수 있도록 합니다.<br /><br /> 참조<br /><br /> -   [솔루션 전체의 종속성 매핑](../modeling/map-dependencies-across-your-solutions.md)<br />-   [코드 맵을 사용 하 여 응용 프로그램 디버그](../modeling/use-code-maps-to-debug-your-applications.md)<br />-   [코드 맵 분석기를 사용 하 여 잠재적인 문제 찾기](../modeling/find-potential-problems-using-code-map-analyzers.md)|  
|**종속성 다이어그램**<br /><br /> 종속성 다이어그램을 통해 명시적 종속 관계를 가진 레이어 또는 블록 집합으로 응용 프로그램의 구조를 정의할 수 있습니다. 코드의 종속성 및 종속성 다이어그램에 설명 된 종속 간 충돌을 검색 하는 유효성 검사를 실행할 수 있습니다.<br /><br /> 일반적인 용도:<br /><br /> -수명 동안 여러 변경 내용을 통해 응용 프로그램의 구조를 안정화 합니다.<br />-코드 변경 내용을 체크 인하기에서 전에 의도 하지 않은 종속성 충돌을 검색 합니다.<br /><br /> 참조<br /><br /> -   [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)<br />-   [종속성 다이어그램을 사용 하 여 코드의 유효성을 검사합니다](../modeling/validate-code-with-layer-diagrams.md)|  
|**도메인별 언어 (DSL)**<br /><br /> DSL은 특정 용도에 맞게 디자인하는 표기법입니다. Visual Studio에서는 일반적으로 그래픽으로 표시됩니다.<br /><br /> 일반적인 용도:<br /><br /> -생성 하거나 응용 프로그램 부분을 구성 합니다. 표기법 및 도구를 개발하려면 작업이 필요합니다. 결과는 UML 사용자 지정보다 도메인에 더 적합할 수 있습니다.<br />대규모 프로젝트에 대해 또는 제품 라인 둘 이상의 프로젝트에서 사용 하 여 개발 하는 DSL 및 도구에 대 한 투자 반환 되는 위치입니다.<br /><br /> 참조<br /><br /> -   [Visual Studio-도메인별 언어에 대 한 모델링 SDK](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)|  
  
## <a name="where-can-i-get-more-information"></a>추가 정보는 어디서 확인할 수 있나요?  
  
[Visual Studio Visualization / 모델링 도구 포럼](http://go.microsoft.com/fwlink/?LinkId=184720)  
  
## <a name="see-also"></a>참고 항목  
 [새로운 기능](../modeling/what-s-new-for-design-in-visual-studio.md)   
 [개발 및 응용 프로그램 수명 주기 관리](http://msdn.microsoft.com/Library/74a1f71d-7f23-4c71-8fd7-89ede614fab6)


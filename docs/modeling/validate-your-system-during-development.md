---
title: 개발하는 동안 시스템 유효성 검사
ms.date: 11/04/2016
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8d4ebc815f474f1b8a1c59c9736f9014ba02e523
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="validate-your-system-during-development"></a>개발하는 동안 시스템 유효성 검사
Visual Studio에서는 소프트웨어와 사용자 요구 사항 및 시스템 아키텍처의 일관성을 유지할 수 있습니다.

 이러한 각 기능을 지원하는 Visual Studio의 버전을 확인하려면 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)를 참조하세요.

## <a name="key-tasks"></a>주요 작업
 다음 작업으로 소프트웨어의 유효성을 검사합니다.

|**작업**|**관련 항목**|
|---------------|---------------------------|
|**소프트웨어가 사용자 요구 사항을 충족하는지 확인합니다**.<br /><br /> 요구 사항 및 아키텍처 모델을 사용하여 시스템 및 해당 구성 요소의 테스트를 구성하도록 지원할 수 있습니다. 이렇게 하면 사용자 및 기타 이해 관계자에게 중요한 요구 사항을 테스트하는지 확인할 수 있고 요구 사항이 변경될 때 테스트를 빠르게 업데이트할 수 있습니다.|-   [모델에서 테스트를 개발](../modeling/develop-tests-from-a-model.md)|
|**소프트웨어와 의도한 시스템 디자인의 일관성이 유지되는지 확인합니다.**<br /><br /> 종속성 다이어그램에서는 응용 프로그램의 구성 요소 간의 의도 한 종속성을 설명 합니다. 개발하는 동안 코드의 실제 종속성이 의도한 디자인을 따르는지 확인할 수 있습니다.|-   [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [종속성 다이어그램으로 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>외부 리소스

|**범주**|**링크**|
|------------------|---------------|
|**비디오**|![비디오에 링크](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Doug 7: Visual Studio 2010과 시스템 디자인 및 코드 이해](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![비디오에 링크](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: 종속성 다이어그램을 사용 하 여 응용 프로그램 설계](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![비디오에 링크](../data-tools/media/playvideo.gif "PlayVideo") [MSDN 어떻게 할까요 시리즈: 유효성 검사 코드 종속성 다이어그램을 사용 하는 방법](http://go.microsoft.com/fwlink/?LinkID=214405)|
|**포럼**|-   [Visual Studio 시각화 및 모델링 도구](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio 시각화 및 모델링 SDK(DSL 도구)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**블로그**|-   [Visual Studio ALM + Team Foundation Server 블로그](http://go.microsoft.com/fwlink/?LinkID=201340)|
|**기술 문서 및 저널**|[MSDN 아키텍처 센터](http://go.microsoft.com/fwlink/?LinkId=201343)|

## <a name="see-also"></a>참고 항목

- [응용 프로그램 테스트](https://www.visualstudio.com/en-gb/docs/test/overview)
- [사용자 요구 사항 모델링](../modeling/model-user-requirements.md)
- [아키텍처 분석 및 모델링](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

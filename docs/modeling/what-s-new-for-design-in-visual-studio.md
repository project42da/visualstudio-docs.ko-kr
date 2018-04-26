---
title: Visual Studio의 디자인에 대한 새로운 기능
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3f2e36bbd95146f8a8b1095fefaa7882ff5f88d2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="whats-new-for-design-in-visual-studio"></a>Visual Studio의 디자인에 대한 새로운 기능

## <a name="live-dependency-validation"></a>라이브 종속성 유효성 검사

원치 않는 종속성을 제거 기술 네 관리의 중요 한 부분입니다. 종속성의 라이브 유효성 검사, 이제 문제에 대 한 정확한 정보를 제공 하 이며 오류 목록 및 편집기의 새로운 기능에서 완전 하 게 혜택이 있습니다.

![라이브 종속성 유효성 검사 적용](media/dep-validation-whatsnew-01.png)

종속성 유효성 검사를 더 쉽게 검색할 수 및 보다 쉽게 액세스할 수 "다이어그램 종속성"을 "레이어 다이어그램" 용어를 변경 하는 제작 환경 변경 되었습니다.

**아키텍처** 메뉴에는 이제 직접 종속성 다이어그램을 만들려면 명령이 포함 되어 있습니다.

![라이브 종속성 메뉴의 항목을 아키텍처](media/dep-validation-whatsnew-02.png)

... 및 종속성 다이어그램 및 해당 설명을 계층의 속성 이름을 알기 쉬운 됨으로 변경 되었습니다.

![라이브 종속성 속성 이름 업데이트](media/dep-validation-whatsnew-03.png)

이제 표시 솔루션에서 현재 코드에 대 한 분석 결과에 즉시 변경 내용의 영향 될 때마다 다이어그램을 저장 합니다. "종속성의 유효성을 검사" 명령이 완료 될 때 더 이상까지 필요가 없습니다.

자세한 내용은 참조 하십시오. [이 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/)합니다.

## <a name="uml-designers-have-been-removed"></a>UML 디자이너 제거 되었습니다.

UML 디자이너에서이 버전의 Visual Studio Enterprise에서 제거 되었습니다.

* UML 다이어그램 XML 파일로 표시 됩니다.
* UML 모델 탐색기 더 이상 존재합니다.
* 모델링 프로젝트 종속성 유효성 검사에 대 한 참조가 더 이상 사용
* 솔루션 탐색기에서 "레이어 참조" 노드는 더 이상 더 표시
* 빌드 작업에서 제거 되었습니다-종속성 (계층) 다이어그램의 "유효성 검사" 빌드 작업은 더 이상 사용
* 버전 간 왕복에 대 한 유지 관리 되는 프로젝트 구조
* 수 여전히를 만들기, 편집 열고 종속성 (계층) 다이어그램을 XML로 저장 합니다.
* 디자인 화면에 액세스할 수 없는 종속성 (계층) 다이어그램에 연결 된 TFS 작업 항목
* 후면에서 연결 DSL 또는 계층은 더 이상 지원
* UML 확장성 Modeling SDK에는 더 이상 지원

그러나를 통해 사용할 수 없으면 시각화.NET 및 c + + 코드의 아키텍처를 지원 [코드 맵](map-dependencies-across-your-solutions.md), 및 위에서 설명한 종속성 유효성 검사는 크게 개선 되었습니다.

UML 디자이너의 중요 한 사용자 인 경우에 UML 요구에 따라 다른 도구를 결정 하는 동안 Visual Studio 2015 또는 이전 버전을 사용 하도록 계속 수 있습니다.

자세한 내용은 참조 하십시오. [이 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/)합니다.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

<a name="VersionSupport"></a>
## <a name="version-support-for-architecture-and-modeling-tools"></a>아키텍처 및 모델링 도구에 대한 버전 지원

Visual Studio는 여러 버전에서 사용할 수 있습니다. 모든 버전에서 아키텍처 및 모델링 도구가 지원되는 것은 아닙니다. 다음 표에서는 각 도구의 사용 가능 여부를 보여 줍니다.

|**기능**|**Enterprise**|**Professional**|**커뮤니티**|**Express**|
|-----------------|--------------------|----------------------|-------------------|-----------------|
|**코드 맵**|예|참고 (1)를 참조 하십시오.|-|-|
|**종속성 다이어그램**|예|참고 (2)를 참조 하십시오.|참고 (2)를 참조 하십시오.|-|
|**전송 그래프** (DGML 다이어그램)|예|예|예|-|
|**코드 복제본**|예|-|-|-|

참고 (1): 코드 맵 읽기, 코드 맵 필터링, 새 제네릭 노드 추가, 선택 영역에서 새 전송 그래프 만들기만 지원합니다.

종속성 다이어그램 읽기 참고 (2):만 지원 합니다.

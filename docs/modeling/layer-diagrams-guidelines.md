---
title: '종속성 다이어그램: 지침'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 9ce90746d89dd41c1f53d7150d83afaa2e2bad46
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="dependency-diagrams-guidelines"></a>종속성 다이어그램: 지침
만들어 높은 수준의 응용 프로그램의 아키텍처에 설명 *종속성 다이어그램* Visual Studio에서. 코드 종속성 다이어그램을 사용 하 여 코드를 검사 하 여이 디자인의 일관성이 유지 되는지 확인 합니다. 빌드 프로세스에 레이어 유효성 검사를 포함할 수도 있습니다. 참조 [Channel 9 비디오: 디자인 종속성 다이어그램을 사용 하 여 아키텍처 및 유효성 검사](http://go.microsoft.com/fwlink/?LinkID=252073)합니다.

 이 기능을 지원하는 Visual Studio 버전을 확인하려면 [아키텍처 및 모델링 도구에 대한 버전 지원](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)을 참조하세요.

## <a name="what-is-a-dependency-diagram"></a>종속성 다이어그램 이란?
 전형적인 아키텍처 다이어그램 처럼 종속성 다이어그램의 주요 구성 요소 또는 설계 및 해당 상호 종속성 기능 단위를 식별합니다. 라고 하는 다이어그램의 각 노드는 *레이어*, 네임 스페이스, 프로젝트 또는 다른 아티팩트의 논리 그룹을 나타냅니다. 디자인에 존재해야 하는 종속성을 그릴 수 있습니다. 전형적인 아키텍처 다이어그램과 달리 소스 코드의 실제 종속성이 사용자가 지정한 의도한 종속성에 부합되는지 확인할 수 있습니다. 유효성 검사를 [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)]에 대한 정기 빌드의 일부로 포함하여 프로그램 코드가 향후 변경되더라도 시스템의 아키텍처와 계속 일치하도록 할 수 있습니다. 참조 [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)합니다.

##  <a name="Update"></a> 디자인 또는 종속성 다이어그램으로 앱을 업데이트 하는 방법
 다음 단계는 개발 프로세스 내에서 종속성 다이어그램을 사용 하는 방법의 개요를 제공 합니다. 이 항목의 뒷부분에 나오는 섹션에서는 각 단계에 대해 좀 더 자세히 설명합니다. 새 디자인을 개발하는 경우 기존 코드를 참조하는 단계는 생략하도록 합니다.

> [!NOTE]
>  이러한 단계는 대략적인 순서로 나타납니다. 작업을 중복하고 상황에 맞게 순서를 변경하며 프로젝트에서 각 반복이 시작될 때 다시 확인할 수 있습니다.

1.  [종속성 다이어그램 만들기](#Create) 전체 응용 프로그램 또는 내부의 레이어에 대 한 합니다.

2.  [주요 기능 영역 또는 구성 요소를 나타내는 레이어 정의](#CreateLayers) 응용 프로그램의 합니다. 해당 기능에 따라 이러한 레이어의 이름을 지정합니다(예: "프레젠테이션" 또는 "서비스"). 있는 경우는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션을 연결할 수 있습니다 각 계층의 컬렉션 *아티팩트*, 프로젝트, 네임 스페이스, 파일, 등입니다.

3.  [기존 종속성 찾기](#Generate) 레이어 간의 합니다.

4.  [레이어 및 종속성을 편집](#EditArchitecture) 표시 업데이트 된 코드에 반영할 디자인 합니다.

5.  [응용 프로그램의 새 영역을 디자인](#NewAreas) 주요 아키텍처 블록 또는 구성 요소를 나타내는 레이어를 만들고 종속성을 각 계층의 다른 항목을 사용 방법을 정의 합니다.

6.  [다이어그램의 모양과 레이아웃 편집](#EditLayout) 동료와 논의할 수 있도록 합니다.

7.  [종속성 다이어그램에 대해 코드 유효성을 검사](#Validate) 를 코드와 필요한 아키텍처 간의 충돌을 강조 표시 합니다.

8.  [새 아키텍처에 맞게 코드 업데이트](#UpdateCode)합니다. 유효성 검사 결과로 충돌이 나타나지 않을 때까지 반복적으로 코드를 개발하고 리팩터링합니다.

9. [빌드 프로세스에 레이어 유효성 검사 포함](#BuildValidation) 코드가 디자인을 적용 하기 위해 계속 되도록 합니다.

##  <a name="Create"></a> 종속성 다이어그램 만들기
 종속성 다이어그램은 모델링 프로젝트 내 만들어야 합니다. 기존 모델링 프로젝트에 새 종속성 다이어그램을 추가 하 종속성 다이어그램에 대 한 새 모델링 프로젝트를 만들 하거나 같은 모델링 프로젝트 내에서 기존 종속성 다이어그램을 복사할 수 있습니다.

> [!IMPORTANT]
>  하지 추가, 끌어 놓거나 않거나 다른 모델링 프로젝트 또는 솔루션의 다른 위치로 모델링 프로젝트에서 기존 종속성 다이어그램을 복사 합니다. 다이어그램을 수정 하는 경우에 이러한 방식으로 복사 하는 종속성 다이어그램은 원본 다이어그램과 동일한 참조 갖습니다. 그러면 레이어 유효성 검사가 제대로 작동하지 않고 다이어그램을 열려고 할 때 요소 누락이나 기타 오류 등의 다른 문제가 발생할 수 있습니다.

 참조 [사용자 코드에서 종속성 다이어그램을 만들](../modeling/create-layer-diagrams-from-your-code.md)합니다.

##  <a name="CreateLayers"></a> 기능 영역 또는 구성 요소를 나타내는 레이어 정의
 레이어 논리 그룹을 나타내는 *아티팩트*, 프로젝트, 코드 파일, 네임 스페이스, 클래스, 메서드 등입니다. Visual C# 및 Visual Basic 프로젝트의 아티팩트에서 레이어를 만들 수 있습니다 또는 있습니다 수 사양 또는 계획을 레이어에 연결할 Word 파일 또는 PowerPoint 프레젠테이션과 같이 문서에 연결 하 여 합니다. 각 레이어는 다이어그램에서 직사각형으로 나타나고 그에 연결된 아티팩트의 수를 보여줍니다. 레이어에는 보다 구체적인 작업을 설명하는 중첩된 레이어가 포함될 수 있습니다.

 일반적인 지침대로 해당 기능에 따라 레이어의 이름을 지정합니다(예: "프레젠테이션" 또는 "서비스"). 아티팩트가 밀접하게 상호 종속되는 경우 동일한 레이어에 배치합니다. 아티팩트를 개별적으로 업데이트하거나 별도 응용 프로그램에서 사용할 수 있는 경우 다른 레이어에 배치합니다. 레이어 링 패턴에 대해 알아보려면 Patterns & Practices 사이트를 방문 [ http://go.microsoft.com/fwlink/?LinkId=145794 ](http://go.microsoft.com/fwlink/?LinkId=145794)합니다.

> [!TIP]
>  특정 유형의 아티팩트를 레이어에 연결할 수 있지만 종속성 다이어그램의 유효성 검사를 지원 하지 않습니다. 아티팩트가 유효성 검사를 지원 하는지 여부를 확인 하려면 열고 **레이어 탐색기** 를 검사 하는 **유효성 검사 지원** 아티팩트 링크의 속성입니다. 참조 [레이어 간의 기존 종속성 찾기](#Generate)합니다.

 익숙하지 않은 응용 프로그램을 업데이트하는 경우에도 코드 맵을 만들 수 있습니다. 이러한 다이어그램은 코드를 탐색하는 동안 패턴 및 종속성을 검색하는 데 도움이 됩니다. 솔루션 탐색기를 사용하여 네임스페이스와 클래스를 탐색합니다. 이러한 요소는 기존 레이어에 해당하는 경우가 많습니다. 솔루션 탐색기에서 종속성 다이어그램에 끌어서 레이어에 이러한 코드 아티팩트를 할당 합니다. 다음 코드를 업데이트 하 고와 디자인의 일관성이 유지 수 있도록 종속성 다이어그램을 사용할 수 있습니다.

 참조

-   [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)

-   [코드 맵을 사용하여 응용 프로그램 디버그](../modeling/use-code-maps-to-debug-your-applications.md)

-   [솔루션 전체의 종속성 매핑](../modeling/map-dependencies-across-your-solutions.md)

##  <a name="Generate"></a> 레이어 간의 기존 종속성 찾기
 한 레이어와 연결된 아티팩트에 다른 레이어와 연결된 아티팩트에 대한 참조가 있을 때마다 종속성이 존재합니다. 예를 들어 한 레이어의 클래스가 다른 레이어의 클래스를 포함하는 변수를 선언하는 경우입니다. 리버스 엔지니어링하여 기존 종속성을 검색할 수 있습니다.

> [!NOTE]
>  일부 아티팩트 종류의 경우 종속성을 리버스 엔지니어링할 수 없습니다. 예를 들어 텍스트 파일에 연결된 레이어를 소스 또는 대상으로 하는 종속성은 리버스 엔지니어링되지 않습니다. 리버스 엔지니어링할 수 있는 종속성이 있는 아티팩트를 확인 하려면 하나 또는 여러 레이어를 마우스 오른쪽 단추로 클릭 하 고 클릭 **링크 보기**합니다. **레이어 탐색기**, 검사는 **유효성 검사 지원** 열입니다. 종속성이 리버스 엔지니어링 아티팩트가이 열은 표시 되지 않은 **False**합니다.

#### <a name="to-reverse-engineer-existing-dependencies-between-layers"></a>레이어 간 기존 종속성을 리버스 엔지니어링하려면

-   하나 또는 여러 개의 레이어를 선택 하 고 선택한 레이어를 마우스 오른쪽 단추로 클릭 한 다음 **종속성 생성**합니다.

 일반적으로 존재할 수 없는 일부 종속성이 나타나는데, 이러한 종속성을 편집하여 계획된 디자인에 맞출 수 있습니다.

##  <a name="EditArchitecture"></a> 레이어 및 종속성을 의도 한 디자인을 보여주는 편집
 시스템 또는 의도 한 아키텍처를 하려면 계획 된 변경 내용을 설명 하기 위해 종속성 다이어그램을 편집 하려면 다음 단계를 사용 합니다. 또한 확장하기 전에 리팩터링을 약간 변경하여 코드의 구조를 향상시키는 것도 고려할 수 있습니다. 참조 [코드 구조 개선](#Improving)합니다.

|**대상**|**다음이 단계를 수행 합니다.**|
|------------|-----------------------------|
|있지 말아야 할 종속성 삭제|종속성을 클릭 한 다음 **삭제**합니다.|
|종속성 방향 변경 또는 제한|설정의 **방향** 속성입니다.|
|새 종속성 만들기|사용 하 여 **종속성** 및 **양방향 종속성** 도구입니다.<br /><br /> 종속성을 여러 개 그리려면 이 도구를 두 번 클릭합니다. 완료 했으면 클릭는 **포인터** 도구 또는 키를 눌러는 **ESC** 키입니다.|
|레이어와 연결된 아티팩트가 지정된 네임스페이스에 종속될 수 없도록 지정합니다.|계층의 네임 스페이스를 입력 **Namespace 사용할 수 없는 종속성** 속성입니다. 세미콜론을 사용 하 여 (**;**)을 네임 스페이스를 구분 합니다.|
|레이어와 연결된 아티팩트가 지정된 네임스페이스에 속하지 않도록 지정합니다.|계층의 네임 스페이스를 입력 **것이 금지 되어 네임 스페이스** 속성입니다. 세미콜론을 사용 하 여 (**;**)을 네임 스페이스를 구분 합니다.|
|레이어와 연결된 아티팩트가 지정된 네임스페이스 중 하나에 속해야 하도록 지정합니다.|레이어의에 네임 스페이스를 입력 **필요한 네임 스페이스** 속성입니다. 세미콜론을 사용 하 여 (**;**)을 네임 스페이스를 구분 합니다.|

###  <a name="Improving"></a> 코드 구조 개선
 리팩터링을 변경하면 응용 프로그램의 동작에 영향을 주지 않지만 나중에 코드를 보다 쉽게 변경하고 확장하는 데 도움이 되도록 개선됩니다. 잘 구성 된 코드에는 디자인은 종속성 다이어그램으로 쉽게 추출할 수 있습니다.

 예를 들어 각 네임스페이스에 대한 레이어를 코드에 만든 다음 종속성을 리버스 엔지니어링하면 레이어 간에 최소한의 단방향 종속성만 존재하게 됩니다. 클래스 또는 메서드를 레이어로 사용하여 더 자세한 다이어그램을 만드는 경우에도 같은 특성을 갖게 됩니다.

 없는 경우 코드 수명 주기 동안 변경 하기 더 어려운 되 고 종속성 다이어그램을 사용 하 여 유효성 검사에 적합 하지 않게 됩니다.

##  <a name="NewAreas"></a> 응용 프로그램의 새 영역 디자인
 새 프로젝트의 개발을 시작하거나 새 프로젝트에서 새 영역을 개발하게 될 경우 코드 개발을 시작하기 전에 레이어 및 종속성을 그리면 주요 구성 요소를 식별하는 데 도움이 될 수 있습니다.

-   **식별 가능한 아키텍처 패턴을 표시** 가능 하면 종속성 다이어그램에서 구성 요소입니다. 예를 들어 데스크톱 응용 프로그램을 설명 하는 종속성 다이어그램에 프레젠테이션, 도메인 논리 및 데이터 저장소와 같은 레이어가 포함 될 수 있습니다. 응용 프로그램 내의 단일 기능에 설명 하는 종속성 다이어그램에는 모델, 뷰 및 컨트롤러와 같은 레이어가 있을 수 있습니다. 이러한 패턴에 대 한 자세한 내용은 참조 [Patterns & Practices: 응용 프로그램 아키텍처](http://go.microsoft.com/fwlink/?LinkId=145794)합니다.

-   **코드 아티팩트를 각 레이어에 대해 만듭니다** 같은 네임 스페이스, 클래스 또는 구성 요소입니다. 이렇게 하면 보다 쉽게 코드를 따라가고 코드 아티팩트를 레이어에 연결할 수 있습니다. 각 아티팩트를 만드는 즉시 해당 레이어에 연결합니다.

-   **대부분의 클래스 및 기타 아티팩트가 레이어에 연결할 필요가 없습니다** 레이어에 이미 연결 된 네임 스페이스와 같은 더 큰 아티팩트에 속하는 합니다.

-   **새로운 기능에 대 한 새 다이어그램 만들기**합니다. 일반적으로 전체 응용 프로그램을 설명 하는 하나 이상의 종속성 다이어그램 됩니다. 응용 프로그램 내에서 새 기능을 디자인하는 경우 기존 다이어그램에 추가하거나 기존 다이어그램을 변경하지 않도록 합니다. 대신 코드의 새 부분을 반영하는 고유한 다이어그램을 만듭니다. 새 다이어그램의 레이어에는 새로운 기능에 대한 프레젠테이션, 도메인 논리 및 데이터베이스 레이어가 포함될 수 있습니다.

     응용 프로그램을 빌드할 경우 전체 다이어그램과 더 자세한 기능 다이어그램에 대해 코드의 유효성을 검사합니다.

##  <a name="EditLayout"></a> 프레젠테이션 및 토론을 위한 레이아웃 편집
 레이어 및 종속성을 식별하거나 팀 멤버와 논의하는 데 도움이 되도록 다음과 같은 방법으로 모양 및 다이어그램의 레이아웃을 편집합니다.

-   레이어의 크기, 모양 및 위치를 변경합니다.

-   레이어의 색과 종속성을 변경합니다.

    -   하나 이상의 레이어 또는 종속성 마우스 오른쪽 단추를 클릭 한 다음 선택 **속성**합니다. 에 **속성** 창 편집는 **색** 속성입니다.

##  <a name="Validate"></a> 다이어그램에 대해 코드 유효성 검사
 다이어그램을 편집한 경우 언제든지 수동으로 또는 로컬 빌드 또는 [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]를 실행할 때마다 자동으로 코드에 대해 유효성을 검사할 수 있습니다.

 참조

-   [종속성 다이어그램을 사용하여 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md)

-   [빌드 프로세스에 레이어 유효성 검사 포함](#BuildValidation)

##  <a name="UpdateCode"></a> 새 아키텍처에 맞게 코드 업데이트
 일반적으로 오류가 업데이트 된 종속성 다이어그램에 대해 코드의 유효성을 처음으로 표시 됩니다. 이러한 오류에는 다음과 같은 여러 원인이 있을 수 있습니다.

-   잘못된 레이어에 아티팩트가 할당되었습니다. 이 경우 아티팩트를 이동합니다.

-   클래스 등의 아티팩트가 아키텍처에 맞지 않는 방식으로 다른 클래스를 사용합니다. 이 경우 코드를 리팩터링하여 종속성을 제거합니다.

 이러한 오류를 해결하려면 유효성 검사 중 더 이상 오류가 나타나지 않을 때까지 코드를 업데이트합니다. 이것은 일반적으로 반복 프로세스입니다. 이러한 오류에 대 한 자세한 내용은 참조 [종속성 다이어그램을 사용 하 여 코드의 유효성을 검사](../modeling/validate-code-with-layer-diagrams.md)합니다.

> [!NOTE]
>  를 개발 하거나 리팩터링할 코드 종속성 다이어그램에 연결할 새 아티팩트가 있을 수 있습니다. 그러나 예를 들어 기존 네임스페이스를 나타내는 레이어가 있고 새 코드가 해당 네임스페이스에 자료만 더 추가한다면 이러한 아티팩트가 필요하지 않을 수 있습니다.

 개발 과정에서 유효성 검사 중 보고된 충돌 문제 중 일부를 표시하지 않을 수 있습니다. 예를 들어 이미 해결되었거나 특정 시나리오와 관계가 없는 오류를 표시하지 않을 수 있습니다. 오류를 표시하지 않는 경우에는 [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]에 작업 항목을 기록하는 것이 좋습니다. 이 작업을 수행 하려면 참조 [종속성 다이어그램을 사용 하 여 코드의 유효성을 검사](../modeling/validate-code-with-layer-diagrams.md)합니다.

##  <a name="BuildValidation"></a> 빌드 프로세스에 레이어 유효성 검사 포함
 코드에서 나중에 변경 내용 종속성 다이어그램을 따르게 하려면 솔루션의 표준 빌드 프로세스에 레이어 유효성 검사를 포함 합니다. 다른 팀 멤버가 솔루션을 빌드할 때마다 종속성 다이어그램 및 코드의 종속성 간 차이가 빌드 오류로 보고 됩니다. 빌드 프로세스에 레이어 유효성 검사를 포함 하는 방법에 대 한 자세한 내용은 참조 [종속성 다이어그램을 사용 하 여 코드의 유효성을 검사](../modeling/validate-code-with-layer-diagrams.md)합니다.

## <a name="see-also"></a>참고 항목

- [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)
- [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)

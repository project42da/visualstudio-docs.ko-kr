---
title: 종속성 다이어그램으로 코드 유효성 검사
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, validating
- validation, dependency diagrams
- validation, code
- code exploration, validating
- architecture, validating
- Visual Studio Ultimate, validating code
- validation, architecture
- validation, dependencies
- MSBuild, tasks
- MSBuild, dependency diagrams
- MSBuild, validating code
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 63dc6c6b1307ae5d8b8be880815f5de5e782c6f5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="validate-code-with-dependency-diagrams"></a>종속성 다이어그램으로 코드 유효성 검사

**최신 뉴스**: 참조 [이 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/2016/11/30/live-dependency-validation-in-visual-studio-2017/)합니다.

[비디오: 실시간으로 아키텍처 종속성 유효성 검사](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)

## <a name="why-use-dependency-diagrams"></a>종속성 다이어그램을 사용 하는 이유

을 코드와 디자인 충돌 하지 않습니다 확인 하기 위해 Visual Studio에서 종속성 다이어그램을 사용 하 여 코드의 유효성을 검사 합니다. 이 경우 다음에 도움이 됩니다.

-   종속성 다이어그램에서 코드의 종속성과 종속성 사이의 충돌을 찾습니다.

-   제안된 변경 내용의 영향을 받을 수 있는 종속성을 찾습니다.

     예를 들어 잠재적인 아키텍처 변경을 나타낸 다음 영향을 받는 종속성을 확인 하려면 코드 유효성을 검사 하려면 종속성 다이어그램을 편집할 수 있습니다.

-   코드를 다른 디자인으로 리팩터링 또는 마이그레이션합니다.

     코드를 다른 아키텍처로 이동할 때 아직 작업이 필요한 코드 또는 종속성을 찾을 수 있습니다.

 **요구 사항**

-   Visual Studio

-   Team Foundation Build를 사용하여 자동으로 코드의 유효성을 검사하는 Team Foundation Build 서버의 Visual Studio

-   포함 된 솔루션을 모델링 프로젝트 종속성 다이어그램을 포함 합니다. 이 종속성 다이어그램의 유효성을 검사 하려는 C# 또는 Visual Basic 프로젝트의 아티팩트에 연결 되어야 합니다. 참조 [사용자 코드에서 종속성 다이어그램을 만들](../modeling/create-layer-diagrams-from-your-code.md)합니다.

 이 기능을 지원하는 Visual Studio 버전을 확인하려면 [아키텍처 및 모델링 도구에 대한 버전 지원](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)을 참조하세요.

 Visual Studio에서 열기 종속성 다이어그램에서 수동으로 또는 명령 프롬프트에서 코드를 확인할 수 있습니다. 또한 로컬 빌드 또는 Team Foundation Build를 실행할 때 자동으로 코드 유효성 검사를 실행할 수도 있습니다. 참조 [Channel 9 비디오: 디자인 종속성 다이어그램을 사용 하 여 아키텍처 및 유효성 검사](http://go.microsoft.com/fwlink/?LinkID=252073)합니다.

> [!IMPORTANT]
>  Team Foundation Build를 사용하여 레이어 유효성 검사를 실행하려면 빌드 서버에 동일한 버전의 Visual Studio를 설치해야 합니다.

-   [항목에서 유효성 검사를 지원 하는지 확인](#SupportsValidation)

-   [다른.NET 어셈블리 및 유효성 검사에 대 한 프로젝트 포함](#IncludeReferences)

-   [수동으로 코드 유효성 검사](#ValidateManually)

-   [코드를 자동으로 유효성 검사](#ValidateAuto)

-   [레이어 유효성 검사 문제 해결](#TroubleshootingValidation)

-   [레이어 유효성 검사 오류 이해 및 해결](#UnderstandingValidationErrors)

## <a name="live-dependency-validation"></a>라이브 종속성 유효성 검사

이 버전의 Visual Studio에서 종속성 유효성 검사를 실시간으로 발생 하 고 오류는 즉시 Visual Studio 오류 목록 창에 표시 됩니다.

* C# 및 Visual Basic.NET 라이브 유효성 검사가 지원 됩니다.

* 전체 솔루션 분석을 실시간 종속성 유효성 검사를 사용 하는 경우 사용 하도록 설정 하려면 오류 목록에 나타나는 골드 모음에서 옵션 설정을 엽니다.
 - 솔루션에 대 한 모든 아키텍처 문제에 없는 경우이 골드 막대를 영구적으로 해제할 수 있습니다.
 - 전체 솔루션 분석 사용를 사용 하지 않을 경우 편집 중인 파일에 대해서만 분석이 수행 됩니다.<p />

* 라이브 유효성 검사를 사용 하도록 프로젝트를 업그레이드 하는 경우 대화 상자는 변환의 진행률을 표시 합니다.

* 라이브 종속성 유효성 검사에 대 한 프로젝트를 업데이트할 때 NuGet 패키지의 버전, 모든 프로젝트에 대해 동일 업그레이드 되 고는 사용 중인 가장 높은 버전입니다.

* 프로젝트 업데이트를 새로운 종속성 유효성 검사 프로젝트 트리거를 추가 합니다.

##  <a name="SupportsValidation"></a> 항목에서 유효성 검사를 지원 하는지 확인
 레이어를 웹 사이트, Office 문서, 일반 텍스트 파일 및 여러 앱에서 공유되는 프로젝트의 파일에 연결할 수는 있지만, 유효성 검사 프로세스에는 레이어가 포함되지 않습니다. 별도의 레이어에 연결된 프로젝트 또는 어셈블리의 경우에는 해당 레이어 간에 종속성이 나타나지 않아도 유효성 검사 오류가 나타나지 않습니다. 이러한 참조는 코드에서 사용하지 않는 한 종속성으로 처리되지 않습니다.

1.  종속성 다이어그램에서 하나 이상의 레이어를 선택 하 고 선택 항목을 마우스 오른쪽 단추로 클릭 **링크 보기**합니다.

2.  **레이어 탐색기**, 확인 된 **유효성 검사 지원** 열입니다. 값이 false일 경우 해당 항목은 유효성 검사를 지원하지 않습니다.

##  <a name="IncludeReferences"></a> 다른.NET 어셈블리 및 유효성 검사에 대 한 프로젝트 포함
 종속성 다이어그램에 항목을 끌면 해당.NET 어셈블리나 프로젝트에 대 한 참조가 자동으로 추가 되는 **레이어 참조** 모델링 프로젝트의 폴더에에서 있습니다. 이 폴더에는 유효성 검사 중 분석되는 프로젝트와 어셈블리에 대한 참조가 포함되어 있습니다. 다른.NET 어셈블리와 프로젝트 유효성 검사를 위한 수동으로 종속성 다이어그램으로 끌어 놓지 않고도 포함할 수 있습니다.

1.  **솔루션 탐색기**, 모델링 프로젝트를 마우스 오른쪽 단추로 클릭 또는 **레이어 참조** 폴더를 마우스 클릭 한 다음 **참조 추가**합니다.

2.  에 **참조 추가** 대화 상자에서 어셈블리 또는 프로젝트를 선택한 다음 **확인**합니다.

##  <a name="ValidateManually"></a> 수동으로 코드 유효성 검사
 솔루션 항목에 연결 하는 개방형 종속성 다이어그램이 있는 경우 실행할 수 있습니다는 **유효성 검사** 다이어그램에서 바로 가기 명령입니다. 실행 하려면 명령 프롬프트를 사용할 수도 있습니다는 **msbuild** 명령에 **/p:ValidateArchitecture** 로 설정 하는 사용자 지정 속성 **True**합니다. 예를 들어, 코드를 변경할 때 종속성 충돌을 빠르게 찾을 수 있도록 레이어 유효성 검사를 정기적으로 수행합니다.

#### <a name="to-validate-code-from-an-open-dependency-diagram"></a>열린 종속성 다이어그램에서 코드 유효성을 검사 하려면

1.  다이어그램 곡면을 마우스 오른쪽 단추로 누른 **아키텍처 유효성 검사**합니다.

    > [!NOTE]
    >  기본적으로는 **빌드 작업** 종속성 (.layerdiagram) 다이어그램 파일 속성이로 설정 되어 **유효성 검사** 다이어그램은 유효성 검사 프로세스에 포함 되도록 합니다.

     **오류 목록** 창에는 발생 한 오류를 보고 합니다. 유효성 검사 오류에 대 한 자세한 내용은 참조 [레이어 유효성 검사 오류 이해 및 해결](#UnderstandingValidationErrors)합니다.

2.  각 오류의 소스를 보려면 오류를 두 번 클릭 하 고 **오류 목록** 창.

    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 오류 소스 대신 코드 맵이 표시될 수도 있습니다. 이 코드에서는 종속성 다이어그램에서 지정 되지 않은 어셈블리에 대 한 종속 또는 코드 종속성 다이어그램으로 지정 된 종속성이 없는 경우 발생 합니다. 이 경우 코드 맵이나 코드를 검토하여 종속성이 있어야 하는지 여부를 확인합니다. 코드 맵에 대 한 자세한 내용은 참조 [솔루션 전체의 종속성 매핑](../modeling/map-dependencies-across-your-solutions.md)합니다.

3.  오류를 관리 하려면 참조 [유효성 검사 오류 관리](#ManageErrors)합니다.

#### <a name="to-validate-code-at-the-command-prompt"></a>명령 프롬프트에서 코드 유효성을 검사하려면

1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 명령 프롬프트를 엽니다.

2.  다음 중 하나를 선택합니다.

    -   솔루션의 특정 모델링 프로젝트를 기준으로 코드 유효성을 검사하려면 다음 사용자 지정 속성을 사용하여 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]를 실행합니다.

        ```
        msbuild <FilePath+ModelProjectFileName>.modelproj /p:ValidateArchitecture=true
        ```

         - 또는

         모델링을 포함 하는 폴더를 찾아 프로젝트 파일 (.modelproj)과 종속성 다이어그램 한 다음 실행 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 다음 사용자 지정 속성과 함께:

        ```
        msbuild /p:ValidateArchitecture=true
        ```

    -   솔루션의 모든 모델링 프로젝트를 기준으로 코드 유효성을 검사하려면 다음 사용자 지정 속성을 사용하여 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]를 실행합니다.

        ```
        msbuild <FilePath+SolutionName>.sln /p:ValidateArchitecture=true
        ```

         - 또는

         다음 실행 및 종속성 다이어그램이 포함 된 모델링 프로젝트를 포함 해야 하는 솔루션 폴더를 찾아 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 다음 사용자 지정 속성과 함께:

        ```
        msbuild /p:ValidateArchitecture=true
        ```

     발생하는 모든 오류가 나열됩니다. 에 대 한 자세한 내용은 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], 참조 [MSBuild](../msbuild/msbuild.md) 및 [MSBuild 작업](../msbuild/msbuild-task.md)합니다.

 유효성 검사 오류에 대 한 자세한 내용은 참조 [레이어 유효성 검사 오류 이해 및 해결](#UnderstandingValidationErrors)합니다.

###  <a name="ManageErrors"></a> 유효성 검사 오류 관리
 개발 과정에서 유효성 검사 중 보고된 충돌 문제 중 일부를 표시하지 않을 수 있습니다. 예를 들어 이미 해결되었거나 특정 시나리오와 관계가 없는 오류를 표시하지 않을 수 있습니다. 오류를 표시하지 않는 경우에는 [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]에 작업 항목을 기록하는 것이 좋습니다.

> [!WARNING]
>  작업 항목을 만들거나 작업 항목에 연결하려면 TFS SCC(소스 코드 제어)에 이미 연결되어 있어야 합니다. 다른 TFS SCC에 대한 연결을 열려고 하면 Visual Studio가 자동으로 현재 솔루션을 닫습니다. 작업 항목을 만들거나 작업 항목에 연결하기 전에 적절한 SCC에 이미 연결되어 있는지 확인합니다. Visual Studio의 이후 릴리스에서는 SCC에 연결되어 있지 않으면 메뉴 명령을 사용할 수 없습니다.

##### <a name="to-create-a-work-item-for-a-validation-error"></a>유효성 검사 오류에 대한 작업 항목을 만들려면

-   에 **오류 목록** 창에서 오류를 마우스 오른쪽 단추로 클릭, 가리킨 **작업 항목 만들기**, 만들려는 작업 항목의 종류를 클릭 하 고 있습니다.

 이러한 작업을 사용 하 여 유효성 검사 오류를 관리 하는 **오류 목록** 창:

|**대상**|**다음이 단계를 수행**|
|------------|----------------------------|
|선택한 오류를 유효성 검사 중에 표시 안 함|선택한 하나 이상의 오류를 마우스 오른쪽 단추로 클릭, 가리킨 **유효성 검사 오류 관리**, 클릭 하 고 **오류 표시 안 함**합니다.<br /><br /> 표시되지 않는 오류는 취소선 서식을 사용하여 나타납니다. 다음에 유효성 검사를 실행하면 이러한 오류가 나타나지 않습니다.<br /><br /> 표시 되지 않는 오류는 해당 종속성 다이어그램 파일의.suppressions 파일에서 추적 됩니다.|
|선택한 오류 표시 안 함 중지|선택한 표시 되지 않는 하나 이상의 오류 단추로 **유효성 검사 오류 관리**, 클릭 하 고 **오류 표시 안 함 중지**합니다.<br /><br /> 다음에 유효성 검사를 실행하면 표시하지 않도록 선택한 오류는 나타나지 않습니다.|
|복원에 표시 되지 않는 모든 오류는 **오류 목록** 창|아무 곳 이나 마우스 오른쪽 단추로 클릭는 **오류 목록** 창, 가리킨 **유효성 검사 오류 관리**, 클릭 하 고 **표시 안 한 오류**합니다.|
|사용자에서 표시 되지 않는 모든 오류는 **오류 목록** 창|아무 곳 이나 마우스 오른쪽 단추로 클릭는 **오류 목록** 창, 가리킨 **유효성 검사 오류 관리**, 클릭 하 고 **숨기기 안 한 오류 표시**합니다.|

##  <a name="ValidateAuto"></a> 코드를 자동으로 유효성 검사
 로컬 빌드를 실행할 때마다 레이어 유효성 검사를 수행할 수 있습니다. 팀에서 Team Foundation Build를 사용하는 경우, 사용자 지정 MSBuild 작업을 생성하여 지정할 수 있는 제어된 체크 인을 사용하여 유효성 검사를 수행하고 빌드 보고서를 사용하여 유효성 검사 오류를 수집할 수 있습니다. 제어 된 체크 인된 빌드를 만들려면 참조 [제어 된 체크 인된 빌드 프로세스를 사용 하 여 변경 사항을 확인 하려면](http://msdn.microsoft.com/Library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec)합니다.

#### <a name="to-validate-code-automatically-during-a-local-build"></a>로컬 빌드 중 자동으로 코드의 유효성을 검사하려면

-   텍스트 편집기를 사용하여 모델링 프로젝트 파일(.modelproj)을 열고 다음 속성을 포함합니다.

```
<ValidateArchitecture>true</ValidateArchitecture>
```

 \- 또는 -

1.  **솔루션 탐색기**, 하나 이상의 종속성 다이어그램이 포함 된 모델링 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.

2.  에 **속성** 창의 설정에서 모델링 프로젝트의 **아키텍처 유효성 검사** 속성을 **True**합니다.

     이렇게 하면 모델링 프로젝트가 유효성 검사 프로세스에 포함됩니다.

3.  **솔루션 탐색기**, 유효성 검사에 사용할 종속성 (.layerdiagram) 다이어그램 파일을 클릭 합니다.

4.  에 **속성** 창 있는지 확인 다이어그램의 **빌드 작업** 속성이 **유효성 검사**합니다.

     이 종속성 다이어그램이 유효성 검사 프로세스에 포함 됩니다.

 오류 목록 창에서 오류를 관리 하려면 참조 [유효성 검사 오류 관리](#ManageErrors)합니다.

#### <a name="to-validate-code-automatically-during-a-team-foundation-build"></a>Team Foundation Build 중 자동으로 코드의 유효성을 검사하려면

1.  **팀 탐색기**, 빌드 정의 두 번 클릭 하 고 클릭 **프로세스**합니다.

2.  아래 **빌드 프로세스 매개 변수**를 확장 하 고 **컴파일**에서 다음을 입력 하 고는 **MSBuild 인수** 매개 변수:

     `/p:ValidateArchitecture=true`

 유효성 검사 오류에 대 한 자세한 내용은 참조 [레이어 유효성 검사 오류 이해 및 해결](#UnderstandingValidationErrors)합니다. [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]에 대한 자세한 내용은 다음을 참조하십시오.

-   [빌드 및 릴리스](/vsts/build-release/index)

-   [빌드 프로세스에 대 한 기본 템플릿 사용](http://msdn.microsoft.com/Library/43930b12-c21b-4599-a980-2995e3d16e31)

-   [UpgradeTemplate.xaml을 기반으로 하는 레거시 빌드 수정](http://msdn.microsoft.com/Library/ee1a8259-1dd1-4a10-9563-66c5446ef41c)

-   [빌드 프로세스 템플릿 사용자 지정](http://msdn.microsoft.com/Library/b94c58f2-ae6f-4245-bedb-82cd114f6039)

-   [실행 중인 빌드의 진행률 모니터링](http://msdn.microsoft.com/Library/e51e3bad-2d1d-4b7b-bfcc-c43439c6c8ef)

##  <a name="TroubleshootingValidation"></a> 레이어 유효성 검사 문제 해결
 다음 표에서는 레이어 유효성 검사 문제와 해결 방법에 대해 설명합니다. 이 문제는 코드와 디자인 간의 충돌로 인해 발생하는 오류와 다릅니다. 이러한 오류에 대 한 자세한 내용은 참조 [레이어 유효성 검사 오류 이해 및 해결](#UnderstandingValidationErrors)합니다.

|**문제**|**가능한 원인**|**해결**|
|---------------|------------------------|--------------------|
|유효성 검사 오류가 예상대로 발생하지 않습니다.|유효성 검사 하는 솔루션 탐색기에서 다른 종속성 다이어그램에서 복사한 같은 모델링 프로젝트에 종속성 다이어그램에서 작동 하지 않습니다. 이러한 방식으로 복사 하는 종속성 다이어그램은 원래 종속성 다이어그램과 동일한 참조를 포함 합니다.|모델링 프로젝트에 새 종속성 다이어그램을 추가 합니다.<br /><br /> 소스 종속성 다이어그램에서 새 다이어그램으로 요소를 복사 합니다.|

##  <a name="UnderstandingValidationErrors"></a> 레이어 유효성 검사 오류 이해 및 해결
 종속성 다이어그램에 대해 코드 유효성을 검사할 때 코드가 디자인과 충돌 하면 유효성 검사 오류가 발생 합니다. 예를 들어, 다음과 같은 조건에서 유효성 검사 오류가 발생할 수 있습니다.

-   잘못된 레이어에 아티팩트가 할당되었습니다. 이 경우 아티팩트를 이동합니다.

-   클래스 등의 아티팩트가 아키텍처에 맞지 않는 방식으로 다른 클래스를 사용합니다. 이 경우 코드를 리팩터링하여 종속성을 제거합니다.

 이러한 오류를 해결하려면 유효성 검사 중 더 이상 오류가 나타나지 않을 때까지 코드를 업데이트합니다. 이 작업은 반복적으로 수행할 수 있습니다.

 다음 섹션에서는 이러한 오류에 사용되는 구문과 이러한 오류의 의미를 설명하고 오류의 해결 및 관리 방법을 제안합니다.

|**구문**|**설명**|
|----------------|---------------------|
|*ArtifactN*(*ArtifactTypeN*)|*ArtifactN* 종속성 다이어그램의 레이어와 연결 된 아티팩트입니다.<br /><br /> *ArtifactTypeN* 유형의 *ArtifactN*와 같은 한 **클래스** 또는 **메서드**, 예:<br /><br /> MySolution.MyProject.MyClass.MyMethod(메서드)|
|*NamespaceNameN*|네임스페이스의 이름입니다.|
|*LayerNameN*|종속성 다이어그램에서 계층의 이름입니다.|
|*DependencyType*|종속성 관계 유형을 *Artifact1* 및 *Artifact2*합니다. 예를 들어 *Artifact1* 에 **호출** 관계가 *Artifact2*합니다.|

|**오류 구문**|**오류 설명**|
|----------------------|---------------------------|
|DV0001: **잘못 된 종속성**|이 문제는 코드 요소 (네임 스페이스, 형식, 멤버) 레이어 참조에 대 한 또 다른 계층에 매핑된 코드 요소를 매핑할 수 있지만이 계층을 포함 하는 종속성 유효성 검사 다이어그램에 이러한 계층 간의 종속성 화살표 없습니다 없을 때 보고 됩니다. 이것은 종속성 제약 조건을 위반 합니다.|
|DV1001: **잘못 된 네임 스페이스 이름**|이 문제는 "허용 Namespace Names" 속성이 코드 요소가 정의 된 네임 스페이스를 포함 하지 않는 레이어에 연결 된 코드 요소에서 보고 됩니다. 이것은 명명 제약 조건을 위반 합니다. "허용 Namespace Names" 구문은 네임 스페이스는 코드에서와 관련 된 요소는 계층의 세미콜론으로 목록 이어야 하는 정의 될 수 있습니다.|
|DV1002: **unreferenceable 네임 스페이스에 대 한 종속성**|이 문제는 레이어에 연결 된 계층의 "Unreferenceable Namespace" 속성에 정의 된 네임 스페이스에 정의 된 다른 코드 요소가 참조 하는 코드 요소에 보고 됩니다. 이것은 명명 제약 조건을 위반 합니다. Note "Unreferenceable 네임 스페이스" 속성을이 레이어에 연결 된 코드 요소에서 참조할 수 없습니다 네임 스페이스의 세미콜론으로 구분 된 목록으로 정의 됩니다.|
|DV1003: **허용 안 함 네임 스페이스 이름**|이 문제는이 코드 요소가 정의 된 네임 스페이스를 포함 하는 "허용 되지 않는 Namespace Names" 속성 레이어와 연결 된 코드 요소에서 보고 됩니다. 이것은 명명 제약 조건을 위반 합니다. Note "허용 안 함 네임 스페이스 name" 속성은 네임 스페이스는 코드에서이 레이어에 연결 된 요소를 정의할 수 없습니다 세미콜론으로 구분 된 목록으로 정의 됩니다.|
|DV3001: **링크 누락**|계층 '*LayerName*'연결'*아티팩트*' 찾을 수 없습니다. 어셈블리 참조가 있는지 확인하세요.|*LayerName* 를 찾을 수 없는 아티팩트에 대 한 링크입니다. 예를 들어 모델링 프로젝트에 클래스가 포함된 어셈블리에 대한 참조가 없어서 해당 클래스에 대한 링크가 없을 수 있습니다.|
|DV9001: **아키텍처 분석 내부 오류를 찾았습니다.**|결과가 불완전할 수 있습니다. 자세한 내용은 상세 빌드 이벤트 로그를 참조하세요.|자세한 내용은 빌드 이벤트 로그 또는 출력 창을 참조하세요.|


## <a name="see-also"></a>참고 항목

- [개발하는 동안 시스템 유효성 검사](../modeling/validate-your-system-during-development.md)
- [비디오: 실시간으로 아키텍처 종속성 유효성 검사](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)

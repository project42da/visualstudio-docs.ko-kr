---
title: "Visual Studio에서 솔루션 로딩 최적화 | Microsoft Docs"
ms.custom: 
ms.date: 08/31/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- startup time [Visual Studio]
- optimizing startup time [Visual Studio]
- speed up start time [Visual Studio]
ms.assetid: 84989983-84bc-4f81-97a8-2131e3a25138
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.performancecenter
ms.technology: vs-ide-general
ms.openlocfilehash: 2102fc026b566c89108f0d74dcf604020653e358
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="optimize-solution-loading-in-visual-studio"></a>Visual Studio에서 솔루션 로딩 최적화
많은 솔루션에는 해당 솔루션을 로드하는 데 걸린 시간에 영향을 주는 다수의 프로젝트가 포함됩니다. 하지만 팀 환경에서 개발자는 일반적으로 해당 프로젝트의 다른 하위 집합을 사용하고 모든 개별 프로젝트를 로드할 필요가 없습니다.

Visual Studio 2017은 **경량 솔루션 로드**를 지원합니다. LSL(경량 솔루션 로드) 모드가 설정된 경우 Visual Studio 2017은 큰 솔루션에 있는 모든 프로젝트를 로드하는 대신 프로젝트의 작은 하위 집합을 로드합니다. 일반적으로 사용되는 IDE 기능은 대부분 LSL 모드에서 작동하고, 사용자에게 전체 솔루션에서 빌드, 검색 및 디버그하는 기능을 제공합니다. (LSL 모드에서 지원되지 않는 기본 기능은 편집 및 계속입니다.)

> [!NOTE]
> 이 콘텐츠는 Visual Studio 2017 업데이트 3에 적용됩니다.

30개 이상의 프로젝트를 포함하는 솔루션의 경우 LSL은 일반적으로 솔루션을 빠르게 두 번(평균) 로드합니다. 대부분의 IDE 기능이 LSL 모드에서 작동하는 반면 일부 IDE 기능은 모든 프로젝트를 로드해야 할 수 있습니다. 이러한 경우 기능을 사용할 수 있도록 Visual Studio는 자동으로 전체 솔루션을 로드합니다. 최악의 경우 경량 모드에서 모든 프로젝트의 로딩을 종료합니다. 

현재 로드되지 않은 프로젝트에서 IDE 기능을 사용하는 경우 Visual Studio는 사용자에게 적절한 프로젝트를 로드합니다. 예를 들어 열리지 않은 프로젝트에서 클래스 다이어그램을 만들거나 여는 경우 Visual Studio는 적절한 프로젝트를 자동으로 로드합니다. 자세한 기능 목록은 다음 섹션에서 참조됩니다.

다음 섹션에서는 경량 솔루션 로드를 사용하는 방법을 표시하고 기능 사용 여부를 결정할 수 있습니다.

## <a name="enable-or-disable-lightweight-solution-load"></a>경량 솔루션 로드를 사용 또는 사용하지 않도록 설정

솔루션 탐색기에서 솔루션 이름을 마우스 오른쪽 단추로 클릭하고 **경량 솔루션 로드 사용**을 선택합니다. 옵션을 선택한 후 경량 솔루션 로드를 활성화하려면 솔루션을 닫았다가 다시 열어야 합니다.

> [!NOTE]
> LSL을 비활성화하기 위해 유사한 단계가 적용됩니다. 경량 솔루션 로드를 사용하지 않으려면 **경량 솔루션 로드 사용 안 함**을 선택한 다음 솔루션을 닫고 다시 엽니다. 

![솔루션 탐색기](../ide/media/VSIDE_LSL_Solution_Setting.png)

## <a name="global_solution_load_settings"></a>경량 솔루션 로드를 위한 전역 설정 구성

**도구 > 옵션 > 프로젝트 및 솔루션**을 선택하여 모든 솔루션에 LSL을 전역적으로 사용하지 않거나 구성할 수 있습니다.

![옵션 대화 상자, 도구](../ide/media/VSIDE_LightweightSolutionLoad.png)

## <a name="how-does-lightweight-solution-load-work-behind-the-scenes"></a>백그라운드에서 경량 솔루션 로드는 어떻게 작동하나요?

솔루션을 로드할 때 Visual Studio는 이전에 열린 프로젝트를 기억하고 해당 프로젝트만을 로드합니다. 다른 모든 프로젝트는 솔루션 탐색기에서 볼 수 있지만 로드되지 않습니다. 프로젝트를 확장하거나 마우스 오른쪽 단추로 클릭하는 즉시 Visual Studio는 해당 프로젝트를 자동 로드합니다. 일반적으로 프로젝트를 자동으로 로드하는 데 1초 미만이 걸리지만 일부 프로젝트는 시간이 더 걸릴 수 있습니다.
그러나 Visual Studio를 사용하면 전체 솔루션에서 작동하는 검색, 디버그, 빌드 및 소스 제어와 같은 IDE 기능을 사용할 수 있습니다. 예를 들어 몇 가지 프로젝트만을 경량 모드에서 로드하는 경우에도 전체 솔루션에서 검색할 수 있습니다. 

더 많은 프로젝트를 확장하면 Visual Studio는 확장된 프로젝트 목록을 기억합니다. 솔루션을 다시 열 때 Visual Studio는 이전에 확장된 프로젝트를 자동 로드합니다.

## <a name="visual-studio-prompts-developers-likely-to-see-significant-performance-gains"></a>Visual Studio는 개발자에게 상당한 성능 이점을 확인할 수 있는 메시지를 표시합니다.

Visual Studio 원격 분석에서 30개 이상의 프로젝트를 포함하는 큰 솔루션은 LSL 모드에서 상당한 혜택을 얻습니다. 따라서 LSL 모드를 사용하도록 큰 솔루션을 가진 개발자에게 메시지를 표시합니다. 처음으로 LSL을 사용하는 대부분의 개발자는 해당 기능을 정기적으로 사용하게 됩니다. 

Visual Studio 사용 원격 분석을 지속적으로 검토하여 가장 많은 혜택을 얻는 개발자에게 LSL 모드를 제공하도록 추론을 개선합니다. 

## <a name="visual-studio-makes-recommendations-to-turn-on-lightweight-solution-load-based-on-heuristics"></a>Visual Studio에서는 추론에 따라 경량 솔루션 로드를 사용하는 것이 좋습니다.

기본적으로 Visual Studio는 가장 많은 혜택을 얻는 사용자에 대해 LSL을 설정합니다. 여러 개의 솔루션이 있는 경우 Visual Studio는 상당한 성능 이점을 얻을 가능성이 높은 솔루션에서 LSL 모드를 제공합니다. 경량 모드 옵션 **Visual Studio에서 결정**(기본 옵션)을 선택하는 경우 Visual Studio는 추론을 기반으로 하여 경량 모드에서 솔루션을 열 수 있습니다. 메시지 표시줄은 솔루션이 경량 모드인지를 나타냅니다. 메시지 표시줄이 표시될 때 자세한 내용을 알아보거나 설정을 업데이트하는 옵션이 제공됩니다.

![팝업 창](../ide/media/VSIDE_LSL_Popup.png)

## <a name="ide-features-fully-supported-in-lightweight-mode"></a>경량 모드에서 완전하게 지원되는 IDE 기능

|기능|경량 모드에서 지원되나요?|
|-|-|-|
|IntelliSense|예|
|검색|예|
|디버깅|예|
|빌드|예|
|코드 탐색(정의로 이동 & 모든 참조 찾기)|예|
|코드 렌즈|예|
|고정 코드 분석|예|
|배포 및 게시|예|
|참조 추가 및 제거|예|
|멀티 타기팅|예|
|IntelliTrace|예|
|Live Unit Testing|예|
|IntelliTest|예|
|Microsoft Fakes|예|
|편집하며 계속하기|지원 안 함|
|단위 테스트|솔루션 빌드 전에 테스트 프로젝트 로드 필요|

## <a name="scenarios-in-which-lightweight-solution-loads-the-appropriate-projects-to-complete-the-operation"></a>경량 솔루션이 적절한 프로젝트를 로드하여 작업을 완료하는 시나리오

솔루션의 프로젝트에서 작동하지 않는 경우 프로젝트는 경량 모드에서 로드되지 않습니다. 일부 기능의 경우 추가 프로젝트를 자동으로 로드하여 기능 시나리오를 지원합니다. (이 목록의 시나리오를 최소화하려고 합니다. ) 이러한 시나리오의 경우 Visual Studio는 자체 프로젝트를 로드하거나 필요에 따라 프로젝트를 로드하라는 메시지를 표시합니다.

|범주|문제|
|-|-|-|
|단위 테스트|로드되지 않은 프로젝트는 "IntelliTest 만들기" 및 "단위 테스트 만들기" 마법사 모두에 대한 테스트 프로젝트 목록에 나타나지 않습니다. </br>테스트를 만들려는 프로젝트를 로드해야 합니다(프로젝트 노드를 확장하여 프로젝트를 로드할 수 있음).|
|클래스 다이어그램|프로젝트의 클래스 다이어그램을 만들거나 열 경우 Visual Studio는 해당 프로젝트에 직접 종속되는 프로젝트를 자동으로 로드합니다. </br>전체 솔루션 로드되지 않은 경우 종속성 유효성 검사 다이어그램에서 참조하는 사용되지 않는 아티팩트의 유효성 검사를 해제합니다.|

## <a name="scenarios-in-which-lightweight-solution-loads-the-entire-solution"></a>경량 솔루션이 전체 솔루션을 로드하는 시나리오 

일부 기능의 경우 Visual Studio는 전체 솔루션을 자동으로 로드하여 시나리오를 지원합니다. 이 작업을 실행하면 전체 기능을 항상 사용할 수 있습니다. 예를 들어 일부 TFS 작업은 전체 솔루션을 로드해야 할 수 있습니다. 전체 기능을 제공하기 위해 Visual Studio는 전체 솔루션을 로드합니다.

|범주|시나리오|
|-|-|-|
|솔루션 노드의 TFS SCC 명령|SCC 명령이 솔루션 탐색기의 솔루션 노드에서 트리거된 경우 Visual Studio는 명령을 완료하기 전에 전체 솔루션을 자동으로 로드합니다.|
|프로젝트 로드|솔루션에 .NET Core 프로젝트 및 공유 프로젝트가 있는 경우 Visual Studio는 자체 초기 솔루션을 로드하는 중에 이러한 프로젝트를 항상 자동으로 로드합니다. 현재 이러한 프로젝트는 경량 모드를 지원하지 않습니다.|
|솔루션 구성 관리자|솔루션 구성 관리자 또는 일괄 처리 빌드를 사용하는 경우 Visual Studio는 자동으로 전체 솔루션을 로드하여 전체 환경을 제공합니다.|
|NuGet 패키지 관리자|NuGet 패키지 관리자의 사용자 인터페이스 또는 NuGet 패키지 관리자 콘솔을 여는 경우 Visual Studio는 자동으로 전체 솔루션을 로드하여 전체 환경을 제공합니다.|

## <a name="known-issues"></a>알려진 문제

LSL 모드에서 작동하지 않고 추가 프로젝트 또는 전체 솔루션을 로드하도록 요구하지 않는 몇 가지 시나리오가 있습니다. 이러한 사례를 해결하기 위해 노력하고 있습니다. 

|범주|문제|해결 방법|
|-|-|-|-|
|IntelliSense|구성이 변경된 후(예: 릴리스 빌드에서 디버그로 또는 그 반대로 변경) IntelliSense가 업데이트되지 않을 수 있습니다. 결과는 구성 변경으로 인한 코드 차이에 따라 달라집니다.|구성을 변경한 후 솔루션을 다시 로드합니다.|
|C#/VB 프로젝트에 대한 리팩터링 제한|프로젝트 파일을 변경하는 코드 수정으로 인해 처음에는 자동으로 실패할 수 있습니다.|이러한 프로젝트의 파일의 코드를 수정해야 하는 경우 프로젝트를 로드합니다. 경량 모드는 로드되지 않는 프로젝트를 수정하지 않습니다.|
|단위 테스트 검색|지연된 프로젝트에서 검색된 테스트는 프로젝트를 수동으로 로드할 때 실행되지 않습니다.|프로젝트를 다시 빌드하여 테스트를 다시 검색하고 선택한 테스트를 실행합니다.|
|LUT(Live Unit Testing)|LSL 모드에서 LUT가 활성화되지 않은 상태로 표시될 수 있습니다. LUT가 테스트 프로젝트 중 하나를 로드해야 하기 때문에 활성화되지 않습니다.|솔루션에서 라이브 단위 테스트를 활성화하는 테스트 프로젝트를 로드합니다.|
|솔루션 탐색기 검색|1.    LSL 모드에서 솔루션 탐색기 검색은 파일 내에서 검색하지 않습니다. 또한 진행 결과가 없습니다.(즉, 클래스, 메서드 등이 아닌 파일만 검색 트리 아래에 표시됩니다.)</br>2.    프로젝트에 속한 모든 파일은 트리 보기 대신 단순 목록으로 표시됩니다. 파일이 프로젝트의 폴더에 속한 경우 검색 보기에서 파일 이름 대신 파일의 상대 경로를 보여줍니다.</br>검색 보기에 파일 항목에 대한 상황에 맞는 메뉴가 없습니다.|비 LSL 모드에서 전체 솔루션을 로드하여 기존 솔루션 탐색기를 검색합니다.</br>Visual Studio IDE 검색을 사용할 수도 있습니다.|
|C++ 프로젝트에 대한 개체 브라우저|개체 브라우저는 로드된 프로젝트에 대해서만 어셈블리/WinMD 참조를 표시합니다.|개체 브라우저에서 정보를 보려는 프로젝트를 로드합니다.|

> [!Note]
> 본사 파트너 덕분에 Resharper를 비롯하여 널리 사용되는 확장도 경량 솔루션 로드에서 잘 작동합니다.

개발자를 위한 솔루션 로드 시간 성능을 최적화하기 위해 혁신할 생각입니다. 새로운 기능이므로 적극적으로 고객 피드백을 확인하고 알려진 문제를 해결하려고 노력하고 있습니다. 여러분의 피드백을 기다리겠습니다. lslsupport@microsoft.com에서 Visual Studio 솔루션 로드 최적화 팀에 전자 메일을 보낼 수 있습니다.

## <a name="see-also"></a>참고 항목
[Visual Studio 성능 팁과 요령](../ide/visual-studio-performance-tips-and-tricks.md)

---
title: Visual Studio에서 Roslyn 분석기를 설치 합니다.
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 8a3b40b3b471e6bb57da561ac51f23086a0f01bd
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="install-net-compiler-platform-analyzers"></a>.NET 컴파일러 플랫폼 분석기를 설치 합니다.

Visual Studio 2017.NET 컴파일러 플랫폼의 핵심 집합에 포함 됩니다 (*Roslyn*) 분석기. 다음이 분석기를 항상 켭니다. NuGet 패키지 또는에서 Visual Studio 확장으로 추가 분석기를 설치할 수 있습니다 *VSIX* 파일입니다.

## <a name="to-install-nuget-package-analyzers"></a>NuGet 패키지 분석기를 설치 하려면

1. [분석기 패키지 버전을 결정](https://github.com/dotnet/roslyn-analyzers#recommended-version-of-analyzer-packages) 를 설치 하려면 Visual Studio의 버전에 따라 합니다.

1. 중 하나를 사용 하 여 Visual Studio에서 패키지를 설치는 [패키지 관리자 콘솔](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console) 또는 [패키지 관리자 UI](/nuget/quickstart/install-and-use-a-package-in-visual-studio#package-manager-console)합니다.

   > [!NOTE]
   > 각 분석기 패키지에 대 한 nuget.org 페이지에 붙여 명령을 보여 줍니다.는 **패키지 관리자 콘솔**합니다. 텍스트를 클립보드에 복사 하는 편리한 단추 짝수 이면 합니다.
   >
   > ![패키지 관리자 콘솔 명령이 보여 주는 NuGet.org 페이지](media/nuget-package-manager-command.png)

   분석기 어셈블리 설치 되 고 표시 **솔루션 탐색기** 아래 **참조** > **분석기**합니다.

   ![솔루션 탐색기에서 노드 분석기](media/solution-explorer-analyzers-node.png)

## <a name="to-install-vsix-analyzers"></a>VSIX 분석기를 설치 하려면

1. Visual Studio에서 선택 **도구** > **확장명 및 업데이트**합니다.

   **확장명 및 업데이트** 대화 상자가 열립니다.

   > [!NOTE]
   > 또는에서 직접 확장을 다운로드 [Visual Studio 마켓플레이스](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017)합니다.

1. 확장 **온라인** 선택 고 왼쪽된 창에서 **Visual Studio 마켓플레이스**합니다.

1. 검색 상자에 "코드 분석"를 입력 하 고 찾습니다는 **Microsoft 코드 분석 2017** 확장 합니다.

   ![Microsoft 코드 분석 확장](media/extensions-and-updates-code-analysis.png)

1. 선택 **다운로드**합니다.

   확장 다운로드 됩니다.

1. 선택 **확인** 대화 상자를 닫은 다음 시작 하려면 Visual Studio의 모든 인스턴스를 종결 하는 **VSIX 설치 관리자**합니다.

   **VSIX 설치 관리자** 대화 상자가 열립니다.

   ![Microsoft 코드 분석을 위한 VSIX 설치 관리자](media/vsix-installer-code-analysis.png)

1. 선택 **수정** 설치를 시작 합니다.

1. 2 분 정도로 후 설치를 완료 합니다. 선택 **닫기**합니다.

1. Visual Studio를 다시 엽니다.

확장 설치 됨, 선택 인지 여부를 확인 하려면 **도구** > **확장명 및 업데이트**합니다. 에 **확장명 및 업데이트** 대화 상자는 **설치 됨** 왼쪽의 범주 한 다음 이름으로 확장을 검색 합니다.

## <a name="next-steps"></a>다음 단계

- [Roslyn 분석기를 사용 하 여 Visual Studio에서](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>참고자료

- [Visual Studio에서 Roslyn 분석기 개요](../code-quality/roslyn-analyzers-overview.md)
---
title: '방법: 사용 하도록 설정 하 고 관리 코드에 대 한 전체 솔루션 분석 사용 안 함 | Microsoft Docs'
ms.date: 03/23/2018
ms.topic: conceptual
helpviewer_keywords:
- full solution analysis
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-code-analysis
ms.workload:
- dotnet
ms.openlocfilehash: 4c5985792138d334de103523478841917555fc56
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-and-disable-full-solution-analysis-for-managed-code"></a>방법: 관리 코드에 대 한 전체 솔루션 분석 활성화 및 비활성화

*전체 솔루션 분석이* 은 Visual Studio 기능을 통해 솔루션에 열려 있는 Visual C# 또는 Visual Basic 파일에만 코드 분석 문제를 확인할 수 있습니다 또는 코드에서 파일을 닫힙니다. 기본적으로 전체 솔루션 분석 사용은 *사용* Visual basic 및 *비활성화* Visual C#에 대 한 합니다.

모든 파일의 모든 문제를 보려면 유용할 수 있지만 산만 수도 있습니다. 저하 Visual Studio 솔루션 매우 큰 경우 또는 경우에 많은 파일이 있습니다. 표시 된 문제 수를 제한 하 고 Visual Studio 성능 향상을 하려면 전체 솔루션 분석 사용을 비활성화할 수 있습니다. 필요한 경우이 기능을 쉽게 다시 활성화할 수 있습니다.

## <a name="to-toggle-full-solution-analysis"></a>전체 솔루션 분석 사용을 전환 하려면

1. 열려는 **옵션** Visual Studio의 메뉴 모음에서 대화 상자에서 선택 **도구** > **옵션**합니다.

1. 에 **옵션** 대화 상자에서 선택 **텍스트 편집기** > **C#** 또는 **기본**  >   **고급**합니다.

1. 선택 된 **전체 솔루션 분석 사용** 전체 솔루션 분석 사용 하거나 사용 하지 않으려면 확인란의 선택을 취소 하려면 확인란 합니다. 선택 **확인** 다 합니다.

    ![전체 솔루션 분석 사용 확인란을 사용 하도록 설정 합니다.](../code-quality/media/options-enable-full-solution-analysis.png)

## <a name="results-of-enabling-and-disabling-full-solution-analysis"></a>설정 및 해제 전체 솔루션 분석 사용의 결과

다음 스크린샷에 전체 솔루션 분석 사용 설정 된 경우 결과 볼 수 있습니다. 모든 오류 및의 코드 분석 문제 *모든* 솔루션에 있는 파일의 표시, 파일은 열려 있는지 여부에 관계 없이 합니다.

![전체 솔루션 분석 사용 하도록 설정 합니다.](../code-quality/media/fsa_enabled.png)

다음 스크린 샷에서 전체 솔루션 분석 사용을 해제 한 후 동일한 솔루션에서 결과 보여 줍니다. 오류 및 열려 있는 솔루션 파일에서 코드 분석 문제에 표시 된 **오류 목록**합니다.

![전체 솔루션 분석 사용 하지 않도록 설정 합니다.](../code-quality/media/fsa_disabled.png)

## <a name="automatically-disable-full-solution-analysis"></a>자동으로 전체 솔루션 분석 사용 안 함

Visual Studio를 검색 하는 경우 200MB 또는 시스템 메모리의 작은 사용할 수 있는 것을 자동으로 비활성화 전체 솔루션 분석 사용 (및 다른 기능) 사용 하는 경우. 이 경우 Visual Studio에 사용할 수 없도록 일부 기능을 알리는 경고가 나타납니다. 단추를 사용 하면 전체 솔루션 분석 사용 하려는 경우 다시 수 있습니다.

![전체 솔루션 분석 사용 중단 경고 텍스트](../code-quality/media/fsa_alert.png)
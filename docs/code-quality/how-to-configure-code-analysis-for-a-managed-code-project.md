---
title: '방법: 관리 코드 프로젝트에 대 한 코드 분석 구성 | Microsoft Docs'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 46d41b09f0f6639195613c8a4d9a08f952c79525
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>방법: 관리 코드 프로젝트에 대한 코드 분석 구성

Visual Studio에서 코드 분석의 목록에서 선택할 수 있습니다 *규칙 집합* 관리 코드 프로젝트에 적용할 수 있습니다. 기본 규칙 집합은 *Microsoft 최소 권장 규칙*합니다. 다른 규칙 집합을 프로젝트 또는 솔루션의 모든 프로젝트에 적용할 수 있습니다.

> [!TIP]
> ASP.NET 웹 응용 프로그램에 대 한 규칙 집합을 구성 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: ASP.NET 웹 응용 프로그램에 대 한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)합니다.

## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>.NET Framework 프로젝트에 대해 설정 하는 규칙을 구성 하려면

1. 열기는 **코드 분석** 프로젝트의 속성 페이지에서 탭 합니다. 다음 방법 중 하나로이 수행할 수 있습니다.

   - **솔루션 탐색기**, 프로젝트를 선택 합니다. 메뉴 모음에서 선택 **분석** > **코드 분석 구성** > **에 대 한 \<p r o j >**합니다.

   - 프로젝트를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 선택 **속성**를 선택한 후는 **코드 분석** 탭 합니다.

1. 에 **구성** 및 **플랫폼** 목록에서 빌드 구성과 대상 플랫폼을 선택 합니다.

1. 파일을 선택한 구성을 사용 하 여 프로젝트를 빌드할 때마다 코드 분석을 실행 하려면 선택은 **빌드에 코드 분석 사용** 확인란 합니다. 선택 하 여 코드 분석을 수동으로 실행할 수도 있습니다 **분석** > **코드 분석 실행** > **에서 코드 분석 실행 \<p r o j >**.

1. 기본적으로 외부 도구에 의해 자동으로 생성된 코드에서 발생한 경고는 코드 분석 시 보고되지 않습니다. 생성 된 코드에서 발생 한 경고를 보려면의 선택을 취소는 **생성 된 코드 결과 표시 안 함** 확인란 합니다.

    > [!NOTE]
    > 이 옵션을 선택하더라도 폼 및 템플릿에 오류와 경고가 나타날 경우에는 생성된 코드에서 발생한 코드 분석 오류 및 경고가 계속 표시됩니다. 보기와 않고도 덮어쓰는 것은 폼 이나 템플릿의 소스 코드를 유지 관리 합니다.

1. 에 **이 규칙 집합 실행** 목록에서 다음 중 하나를 수행 합니다.

    - 규칙 집합을 사용 하려면 선택 합니다.

    - 선택  **\<찾아보기... >** 는 기존 사용자 지정 규칙 집합을 찾을 수 없는 목록에 있습니다.

    - 사용할 규칙 집합을 선택합니다. 자세한 내용은 참조 [사용자 지정 규칙 집합 만들기](../code-quality/creating-custom-code-analysis-rule-sets.md)합니다.

## <a name="see-also"></a>참고자료

- [연습: 사용자 지정 규칙 집합 구성 및 사용](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)
- [방법: ASP.NET 웹 응용 프로그램에 대한 코드 분석 구성](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)
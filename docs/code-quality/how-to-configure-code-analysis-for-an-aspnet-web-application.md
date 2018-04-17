---
title: '방법: Visual Studio에서 ASP.NET 웹 응용 프로그램에 대 한 코드 분석 구성 | Microsoft Docs'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.asp
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 6f0868c825c4e3632a882a044b69e676053800ea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>방법: ASP.NET 웹 응용 프로그램에 대한 코드 분석 구성

Visual Studio에서 코드 분석의 목록에서 선택할 수 있습니다 *규칙 집합* 에 적용할 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램입니다. 기본 규칙 집합은 Microsoft 최소 권장 규칙입니다. 웹 사이트에 적용 되도록 설정 하는 또 다른 규칙을 선택할 수 있습니다.

1. 웹 사이트를 선택 **솔루션 탐색기**합니다.

2. 에 **분석** 메뉴를 클릭 하 여 **웹 사이트에 대 한 코드 분석 구성**합니다.

3. 솔루션을 선택 하는 경우 솔루션에 여러 프로젝트에서 빌드 구성과 대상 운영 체제를 선택는 **구성** 및 **플랫폼** 나열 합니다.

4. 솔루션의 각 프로젝트에 대 한 클릭는 **규칙 집합** 열, 그리고 실행 되도록 설정 된 규칙의 이름을 클릭 합니다.

5. 기본적으로 솔루션의 모든 프로젝트에서 코드 분석을 실행 합니다. 를 사용 하지 않도록 설정 하거나 특정 프로젝트에 대 한 코드 분석을 사용 하도록 설정 하려면 다음이 단계를 따르십시오.

    1. 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 Properties를 클릭 합니다.

    2. 선택 하거나 선택 취소 된 **코드 분석 사용** 확인란 합니다. 선택 하 여 코드 분석을 수동으로 실행할 수도 있습니다 **웹 사이트에서 코드 분석 실행** 에서 **분석** 메뉴.

6. 에 **이 규칙 집합 실행** 드롭 다운 목록에서 다음이 단계를 수행 합니다.

    - 규칙 집합을 사용 하려면 선택 합니다.

    - 선택  **\<찾아보기 >** 기존 사용자 지정 규칙 집합을 지정 하려면 목록에 없는 합니다.

    - 정의 [사용자 지정 규칙 집합](../code-quality/how-to-create-a-custom-rule-set.md)합니다.
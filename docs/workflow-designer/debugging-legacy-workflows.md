---
title: "레거시 워크플로 디버깅 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, debugging
- debugging, workflows
- debugging workflows
ms.assetid: e6097b47-760a-4b30-a92c-ae70cdbda49f
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4898e8f720143bd60337c9fe6bed20a7489c0d04
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="debugging-legacy-workflows"></a>레거시 워크플로 디버깅

레거시 Windows 워크플로 디자이너를 사용 하는 경우 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] 만들려는 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 빌드하 Framework 3.0 또는 3.5를 디버깅할 수 있는 다른 프로그램과 마찬가지로 워크플로에 중단점 설정, 프로세스에 연결 및 검사 하 여 응용 프로그램 스레드 및 호출 스택을 합니다. 뿐만 아니라 원격으로 디버깅할 수도 있습니다.

> [!NOTE]
> 컴퓨터에 여러 버전의 Visual Studio를 설치하고 제거한 경우 다음과 같은 두 가지 문제 중 하나로 WF3 디버깅이 실패할 수 있습니다.
>
> -   중단점이 적중되지 않습니다.
> -   다음 메시지가 표시됩니다.
>
> **웹 서버에서 디버깅을 시작할 수 없습니다. 디버거가 제대로 설치되지 않았습니다.  요청한 코드 형식을 디버깅할 수 없습니다.  설치 하거나 복구 디버거 설치 프로그램을 실행 합니다.**
>
> .NET Framework 3.0 또는 3.5 워크플로를 디버깅할 때 이러한 경우 중 하나가 발생하면 Visual Studio 설치 복구를 수행하세요.

 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)]는 다음과 같은 표준 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버그 창과 통합됩니다.

-   **중단점**: 예상 대로 작동 이지만 함수 이름에 대 한 활동을 지정 합니다.

-   **호출 스택**: 워크플로 인스턴스 실행 된 활동의 개요를 제공 하도록 수정 합니다. 에 있는 항목의 **호출 스택** 창은 실행 되는 활동의 깊이 우선 검색 합니다. 항목을 두 번 클릭하여 선택된 활동에 초점을 맞출 수 있습니다.

-   **스레드**: 디버깅 중인 워크플로 인스턴스의 인스턴스 ID를 제공 합니다.

 Visual Studio for Windows Workflow Foundation은 다음 디버깅 기능을 지원하지 않습니다.

-   디자이너 화면의 조건부 중단점

-   간략한 조사식

-   다음 문 설정

-   커서까지 실행

-   편집하며 계속하기

-   Just-In-Time 디버깅

-   혼합 모드 디버깅
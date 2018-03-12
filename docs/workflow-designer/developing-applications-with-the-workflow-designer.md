---
title: "워크플로 디자이너로 응용 프로그램 개발 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DefaultWorkflowDesigner
- DefaultWorkflowDesigner.UI
helpviewer_keywords:
- Visual Studio 2010 Workflow Designer [WFD], overview
- Workflow Designer [WFD]
- Visual Studio 2010 Workflow Designer [WFD]
- Workflow Designer [WFD], overview
ms.assetid: 4cd062b1-b496-4668-bbc1-ee85545e066d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 75a6fb6eef1f5e8e174607ac141646ab237dd285
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="developing-applications-with-the-workflow-designer"></a>워크플로 디자이너로 응용 프로그램 개발

Windows 워크플로 디자이너는는 비주얼 디자이너 겸 디버거입니다 그래픽을 생성 하 고 디버깅할 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 에서 응용 프로그램의 [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] 에 호스트 되는 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 개발 환경입니다. 여기서 템플릿 및 활동 디자이너를 사용하여 복합 워크플로 응용 프로그램, 활동 라이브러리 또는 [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 서비스를 생성할 수 있습니다. 워크플로에 대 한 자세한 내용은 참조는 [Windows Workflow Foundation &#91;.NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66)합니다.

 새 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 버전에서 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 이전 버전과 달라진 몇 가지 디자인 기능은 다음과 같습니다.

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[avalon1](../workflow-designer/includes/avalon1_md.md)]로 제작되었습니다. 따라서 활동 디자이너의 사용 경험과 대형 복합 워크플로에 대한 성능이 향상되었습니다.

-   이제 XAML을 사용하여 [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)]로 사용자 지정 활동을 설계할 수 있으며 활동 디자이너를 생성하는 프로그래밍 모델이 간소화되었습니다.

-   익숙한 순서도 모델링 스타일을 사용하여 프로그램 흐름을 시각화할 수 있도록 순서도 활동을 구현했습니다.

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]에는 워크플로 내에서 변수를 선언하고 범위를 지정하여 활동에 바인딩할 수 있도록 하는 새로운 변수 디자이너가 있습니다.

-   [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]에서 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 워크플로 내에 Visual Basic 식을 작성할 때 완전한 IntelliSense 기능을 제공합니다.

-   이제 디버깅 환경이 XAML까지 확장되어 XAML 워크플로 정의에 중단점을 설정하고 런타임 시 XAML 코드를 한 단계씩 실행할 수 있으므로 관리 코드와 비슷한 사용 경험을 얻을 수 있습니다.

-   [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 외부에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 재호스트하는 작업이 이전 버전과 비교할 때 훨씬 간소화되어 이제는 코드 몇 줄만 있으면 됩니다.

-   새 <xref:System.Activities.Statements.Flowchart> 활동 및 해당 [순서도](../workflow-designer/flowchart-activity-designer.md) 익숙한 순서도 모델링 스타일을 사용 하 여 프로그램 흐름을 시각화 합니다.

-   메시징 활동도 향상되어 완전 선언적(코드 없음) [!INCLUDE[indigo1](../workflow-designer/includes/indigo1_md.md)] 서비스를 작성할 수 있습니다.

-   **서비스 참조 추가...**  기능을 사용 하면 웹 서비스에 액세스 하는 자동으로 작업을 생성할 수 있습니다.
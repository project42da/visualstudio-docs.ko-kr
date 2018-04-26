---
title: 워크플로 디자이너로 응용 프로그램 개발
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ecc9e42146bfa7de259551ff1c90d27201db5725
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="developing-applications-with-the-workflow-designer"></a>워크플로 디자이너로 응용 프로그램 개발

Windows 워크플로 디자이너에는 비주얼 디자이너와 그래픽을 생성 하 고 Visual Studio 2010 개발 환경에서 호스팅되는.NET Framework 4의 Windows WF (Workflow Foundation) 응용 프로그램의 디버깅에 대 한 디버거는입니다. 복합 워크플로 응용 프로그램, 활동 라이브러리 또는 서식 파일 및 활동 디자이너를 사용 하 여 Windows Communication Foundation (WCF) 서비스를 작성할 수 있습니다. 워크플로에 대 한 자세한 내용은 참조는 [Windows Workflow Foundation &#91;.NET Framework 4&#93;](http://msdn.microsoft.com/Library/9a23ea6b-d600-483e-89cd-8889cfec5f66)합니다.

 다음은이 새로운 버전의 워크플로 디자이너의 이전 버전과 달라진 워크플로 디자이너를 설정 하는 몇 가지 새 디자인 기능.

-   Windows Presentation Foundation (WPF)를 사용 하 여 워크플로 디자이너 만들어집니다. 따라서 활동 디자이너의 사용 경험과 대형 복합 워크플로에 대한 성능이 향상되었습니다.

-   이제 XAML을 사용하여 [!INCLUDE[avalon2](../workflow-designer/includes/avalon2_md.md)]로 사용자 지정 활동을 설계할 수 있으며 활동 디자이너를 생성하는 프로그래밍 모델이 간소화되었습니다.

-   익숙한 순서도 모델링 스타일을 사용하여 프로그램 흐름을 시각화할 수 있도록 순서도 활동을 구현했습니다.

-   워크플로 디자이너에는 새로운 변수 디자이너가 선언 하 고 워크플로 내에서 변수 범위 수 있는 활동에 바인딩할 수 있습니다.

-   Visual Studio 2010 워크플로 디자이너는.NET Framework 4 워크플로 내에서 Visual Basic 식을 작성할 때 완전 한 IntelliSense 기능을 제공 합니다.

-   이제 디버깅 환경이 XAML까지 확장되어 XAML 워크플로 정의에 중단점을 설정하고 런타임 시 XAML 코드를 한 단계씩 실행할 수 있으므로 관리 코드와 비슷한 사용 경험을 얻을 수 있습니다.

-   Visual Studio 외부에서 워크플로 디자이너 재호스팅은 크게 단순화 이제 단 몇 줄의 코드를 요구 하는 이전 버전과 비교 합니다.

-   새 <xref:System.Activities.Statements.Flowchart> 활동 및 해당 [순서도](../workflow-designer/flowchart-activity-designer.md) 익숙한 순서도 모델링 스타일을 사용 하 여 프로그램 흐름을 시각화 합니다.

-   메시징 활동 향상 되어 완전 선언적를 작성할 수 있도록 (코드) Windows Communication Foundation (WCF) 서비스입니다.

-   **서비스 참조 추가...**  기능을 사용 하면 웹 서비스에 액세스 하는 자동으로 작업을 생성할 수 있습니다.
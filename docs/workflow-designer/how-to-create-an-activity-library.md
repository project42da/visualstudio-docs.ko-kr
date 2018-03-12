---
title: "방법: 활동 라이브러리 만들기 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 151e3f84636273de253937ebf5c91cff066b9f85
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-an-activity-library"></a>방법: 활동 라이브러리 만들기
사용자 지정 활동은 워크플로의 특정 비즈니스 프로세스를 모델링하는 데 사용됩니다. 활동 라이브러리 템플릿은 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 시각적으로 Windows 워크플로 디자이너를 사용 하 여 이러한 사용자 지정 활동을 만들 수 있도록 제공 되었습니다.

### <a name="to-create-a-workflow-activity-library"></a>워크플로 활동 라이브러리를 만들려면

1.  [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]를 시작합니다.

2.  에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트...** .

     **새 프로젝트** 대화 상자가 열립니다.

3.  에 **프로젝트 형식** 창 선택 **워크플로** 중 하 나와 **Visual C#** 프로젝트 또는 **Visual Basic** 그룹화에 따라 프로그램 언어 기본 설정 합니다.

4.  에 **템플릿** 창 선택 **활동 라이브러리**합니다.

5.  에 **이름** 상자에서 쉽게 식별할 수 있도록 프로젝트에 대 한 설명이 포함 된 이름 입력 합니다.

6.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리에 대 한 입력 **찾아보기** 찾습니다.

7.  에 **솔루션** 상자는 솔루션에 대 한 설명이 포함 된 이름을 입력 한 다음 클릭 **확인**합니다.

    > [!NOTE]
    > 기존 솔루션에 워크플로 콘솔 응용 프로그램을 추가 하려는 경우에서 해당 솔루션을 열고 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)], 솔루션을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**을 선택 하 고 **추가**, 다음  **새 프로젝트...**  열려는 **새 프로젝트** 대화 상자. 그런 다음 이 절차의 윗부분에 설명된 대로 진행합니다.

8.  프로젝트 템플릿이 활동 정의를 XAML로 만듭니다. Windows Workflow Designer가 열리고 사용자 지정 활동의 캔버스가 표시 됩니다.

9. 활동을 끌어는 **도구 상자** 사용자 지정 활동을 포함 하 여 디자인 화면에 있습니다.

    > [!CAUTION]
    > 사용자 지정 활동의 본문에 자식 활동을 한 개만 넣을 수 있지만, 자식 활동으로 <xref:System.Activities.Statements.Sequence> 활동 또는 <xref:System.Activities.Statements.Flowchart> 활동과 같은 복합 활동을 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [방법: 활동 만들기](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [워크플로 프로젝트 만들기](../workflow-designer/creating-a-workflow-project.md)
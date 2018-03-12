---
title: "방법: 순차 워크플로 콘솔 응용 프로그램 만들기 (레거시) | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, console applications
- sequential workflows, console applications
- console applications, sequential workflow
ms.assetid: 9f7be7fa-551f-42c6-a9bb-f5ae8ab83625
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 211c750dd0baa1dad0a365310b3636c0d0922882
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-create-sequential-workflow-console-applications-legacy"></a>방법: 순차 워크플로 콘솔 응용 프로그램 만들기(레거시)
제공 되는 레거시 Windows 워크플로 디자이너를 사용 하 여 순차 워크플로 콘솔 응용 프로그램 프로젝트를 만들려면 다음이 단계를 수행 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]합니다. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.

### <a name="to-create-a-sequential-workflow-console-application"></a>순차 워크플로 콘솔 응용 프로그램을 만들려면

1.  Visual Studio를 시작합니다.

2.  에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트**합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3.  중 하나를 선택는 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 목록 맨 위에 있는 드롭다운에서 **새 프로젝트** 레거시 디자이너에 액세스 하는 창입니다.

    > [!NOTE]
    > 기본 옵션 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 은 **.NET Framework 4**합니다. 이 옵션은 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]을 대상으로 하는 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 응용 프로그램을 만드는 데 사용합니다.

4.  에 **프로젝트 형식** 창, 선택 Visual C# 프로젝트 또는 Visual Basic 프로젝트 (아래 **다른 언어**)를 선택한 후 **워크플로**합니다.

5.  에 **템플릿** 창 선택 **순차 워크플로 콘솔 응용 프로그램**합니다.

6.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.

7.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.

     Windows Forms 디자이너가 열리며 사용자가 만든 프로젝트의 Form1이 나타납니다.

8.  **확인**을 클릭합니다.

     워크플로 디자이너가 열리며 사용자가 만든 순차 워크플로의 워크플로 디자인 화면이 나타납니다.

9. 활동을 끌어는 **도구 상자** 의 디자인 화면에는 **활동을 Drop** 영역을 지정 합니다.

## <a name="see-also"></a>참고 항목

- [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)
- [워크플로 개발](http://msdn.microsoft.com/en-us/557bcb1f-a7ab-49f6-8df7-2706b7001301)
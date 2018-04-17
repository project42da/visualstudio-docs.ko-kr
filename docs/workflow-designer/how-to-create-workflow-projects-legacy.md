---
title: '방법: 워크플로 프로젝트 (레거시) 만들기 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflow projects, creating
- projects, workflow
ms.assetid: 32299555-662c-469d-a90d-89f4700dc78c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ca6fdbbd8a744c472c06fdefbdafce77679ec2c9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-workflow-projects-legacy"></a>방법: 워크플로 프로젝트 만들기(레거시)
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 또는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)]를 대상으로 하는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)] 프로젝트를 만들려면 다음 단계를 따릅니다. 이 프로시저에서 제공 되는 레거시 Windows 워크플로 디자이너를 사용 하 여 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]합니다.

### <a name="to-create-a-workflow-project"></a>워크플로 프로젝트를 만들려면

1.  [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]를 시작합니다.

2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3.  중 하나를 선택는 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 목록 맨 위에 있는 드롭다운에서 **새 프로젝트** 레거시 디자이너에 액세스 하는 창입니다.

    > [!NOTE]
    > 기본 옵션 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 은 **.NET Framework 4**합니다. 이 옵션은 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]을 대상으로 하는 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 응용 프로그램을 만드는 데 사용합니다.

4.  에 **프로젝트 형식** 창에서 Visual C# 프로젝트나 Visual Basic 프로젝트를 선택한 다음 선택 **워크플로**합니다.

5.  에 **템플릿** 창에서 설치 된 프로젝트 템플릿 중 하나를 선택 합니다.

    -   순차 워크플로 콘솔 응용 프로그램

    -   순차 워크플로 라이브러리

    -   워크플로 활동 라이브러리

    -   상태 시스템 워크플로 콘솔 응용 프로그램

    -   상태 시스템 워크플로 라이브러리

    -   빈 워크플로 프로젝트

6.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.

7.  에 **위치** 상자에 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 합니다 **찾아보기** 를 디렉터리로 이동 합니다.

     솔루션 디렉터리를 만들려면 프로젝트에 대 한 선택은 **솔루션용 디렉터리 만들기** 확인란을 선택 하 고에 이름을 입력는 **솔루션 이름** 상자 합니다.

8.  **확인**을 클릭합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)
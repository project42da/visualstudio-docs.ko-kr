---
title: '워크플로 디자이너-방법: 워크플로 활동 라이브러리 만들기 (레거시)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, activity library projects
- workflow activity libraries
- projects, workflow activity libraries
ms.assetid: fb5aa940-2ae8-4b52-b52c-51c20861a7b4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 432766e60ee1384db0f8cd5bad1f369e80ddd20a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-workflow-activity-library-legacy"></a>방법: 워크플로 활동 라이브러리 만들기(레거시)

Visual Studio 2010에서 Windows 워크플로 디자이너에서 제공 하는 레거시를 사용 하 여 워크플로 활동 라이브러리 프로젝트를 만들려면 다음이 단계를 수행 합니다. WinFX 또는.NET Framework 버전 3.5 대상으로 해야 하는 경우 레거시 워크플로 디자이너를 사용 합니다.

## <a name="to-create-a-workflow-activity-library-project"></a>워크플로 활동 라이브러리 프로젝트를 만들려면

1.  Visual Studio를 시작합니다.

2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3.  중 하나를 선택는 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 목록 맨 위에 있는 드롭다운에서 **새 프로젝트** 레거시 디자이너에 액세스 하는 창입니다.

    > [!NOTE]
    > Visual Studio 2010에서 기본 옵션은 **.NET Framework 4**합니다. .NET Framework 4를 대상으로 하는 Windows WF (Workflow Foundation) 응용 프로그램을 만들려면이 옵션을 사용 하 고 레거시 디자이너를 사용 하지 않습니다.

4.  에 **프로젝트 형식** 창에서 Visual C# 또는 Visual Basic (아래 **다른 언어**)를 클릭 한 **워크플로**합니다.

5.  에 **템플릿** 창 선택 **워크플로 활동 라이브러리**합니다.

6.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.

7.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.

     솔루션 디렉터리를 만들려면 프로젝트에 대 한 선택은 **솔루션용 디렉터리 만들기** 확인란을 선택 하 고에 이름을 입력는 **솔루션 이름** 상자 합니다.

8.  **확인**을 클릭합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)
- [레거시 활동 디자이너 사용](../workflow-designer/using-the-legacy-activity-designer.md)
- [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)
- [워크플로 활동 개발](http://msdn.microsoft.com/en-us/19876dfc-dfa5-4d52-b1f5-1d087474cc52)
- [Windows Workflow Foundation 활동](http://msdn.microsoft.com/en-us/192c4c1e-afb6-4f58-ab11-2b5bbbc2d2c0)
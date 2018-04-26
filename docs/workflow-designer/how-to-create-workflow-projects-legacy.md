---
title: '워크플로 디자이너-방법: 워크플로 프로젝트 (레거시) 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflow projects, creating
- projects, workflow
ms.assetid: 32299555-662c-469d-a90d-89f4700dc78c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bb5d58c6d450a5e68d804e33785ec76349bfb6d8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-workflow-projects-legacy"></a>방법: 워크플로 프로젝트 만들기(레거시)

WinFX 또는.NET Framework 버전 3.5 대상으로 하는 Windows WF (Workflow Foundation) 프로젝트를 만들려면 다음이 단계를 수행 합니다. 이 절차는 Visual Studio 2010에서 제공 되는 레거시 Windows 워크플로 디자이너를 사용 합니다.

## <a name="to-create-a-workflow-project"></a>워크플로 프로젝트를 만들려면

1.  Visual Studio를 시작합니다.

2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3.  중 하나를 선택는 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 목록 맨 위에 있는 드롭다운에서 **새 프로젝트** 레거시 디자이너에 액세스 하는 창입니다.

    > [!NOTE]
    > Visual Studio 2010에서 기본 옵션은 **.NET Framework 4**합니다. .NET Framework 4를 대상으로 하는 Windows WF (Workflow Foundation) 응용 프로그램을 만들려면이 옵션을 사용 하 고 레거시 디자이너를 사용 하지 않습니다.

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
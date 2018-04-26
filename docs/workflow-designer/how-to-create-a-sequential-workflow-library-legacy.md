---
title: '워크플로 디자이너-방법: 순차 워크플로 라이브러리 만들기 (레거시)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- sequential workflows, creating library
- workflows, sequential workflow library
- projects, sequential workflow library
- sequential workflow libraries
ms.assetid: 9433ccf3-1eab-4d53-90ff-2e7b2341676c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2ed341481ec3e82165a9f4cefd71eb362781d96c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-sequential-workflow-library-legacy"></a>방법: 순차 워크플로 라이브러리 만들기(레거시)

Visual Studio 2010에서 Windows 워크플로 디자이너에서 제공 하는 레거시를 사용 하 여 순차 워크플로 라이브러리 프로젝트를 만들려면 다음이 단계를 수행 합니다. WinFX 또는.NET Framework 버전 3.5 대상으로 해야 하는 경우 레거시 워크플로 디자이너를 사용 합니다.

## <a name="to-create-a-sequential-workflow-library-project"></a>순차 워크플로 라이브러리 프로젝트를 만들려면

1.  Visual Studio를 시작합니다.

2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음, **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 열립니다.

3.  중 하나를 선택는 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 목록 맨 위에 있는 드롭다운에서 **새 프로젝트** 레거시 디자이너에 액세스 하는 창입니다.

    > [!NOTE]
    > Visual Studio 2010에서 기본 옵션은 **.NET Framework 4**합니다. .NET Framework 4를 대상으로 하는 Windows WF (Workflow Foundation) 응용 프로그램을 만들려면이 옵션을 사용 하 고 레거시 디자이너를 사용 하지 않습니다.

4.  에 **프로젝트 형식** 창에서 Visual C# 또는 Visual Basic (아래 **다른 언어**)를 선택한 후 **워크플로**합니다.

5.  에 **템플릿** 창 선택 **순차 워크플로 라이브러리**합니다.

6.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.

7.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.

     솔루션 디렉터리를 만들려면 프로젝트에 대 한 선택은 **솔루션용 디렉터리 만들기** 확인란을 선택 하 고에 이름을 입력는 **솔루션 이름** 상자 합니다.

8.  **확인**을 클릭합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)
- [워크플로 제작 스타일](http://msdn.microsoft.com/en-us/aacf4ec6-da05-4974-958a-974769dda739)
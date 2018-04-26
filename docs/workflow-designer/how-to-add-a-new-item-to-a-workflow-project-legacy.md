---
title: '워크플로 디자이너-방법: 워크플로 프로젝트 (레거시)에 새 항목 추가'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- sequential workflows, adding to workflow projects
- workflows, adding new items
- state machine workflows, adding to workflow projects
- activities, adding to workflow projects
ms.assetid: 130cd83d-942d-437b-bbb5-8088ec0a6d79
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d6e9607f4924057568849fd7eabd4567130dc2f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-a-new-item-to-a-workflow-project-legacy"></a>방법: 워크플로 프로젝트에 새 항목 추가(레거시)

Windows WF (Workflow Foundation) 항목 및 다른 친숙 한 Visual Studio Windows 워크플로 디자이너는 WinFX 또는.NET Framework 버전 3.5 대상으로 하는 Visual Studio 2010에서 제공 하는 레거시를 사용 하 여 워크플로 프로젝트를 만든 후 추가할 수 있습니다. 항목을 프로젝트입니다.

다음 표에서는 워크플로 프로젝트에 추가할 수 있는 Windows Workflow Foundation 항목을 보여 줍니다.

|항목|설명|
|----------|-----------------|
|동작|디자이너 코드 파일에 동작 정의가 있고 별도의 코드 파일에 사용자 코드가 있는 동작|
|동작(코드 분리)|워크플로 마크업으로 표현되었고 별도의 코드 파일에 사용자 코드가 있는 동작 정의|
|순차 워크플로(코드)|디자이너 코드 파일에 워크플로 정의가 있고 별도의 코드 파일에 사용자 코드가 있는 순차 워크플로|
|순차 워크플로(코드 분리)|워크플로 정의가 워크플로 마크업으로 표현되었고 별도의 코드 파일에 사용자 코드가 있는 순차 워크플로|
|상태 시스템 워크플로(코드)|디자이너 코드 파일에 워크플로 정의가 있고 별도의 코드 파일에 사용자 코드가 있는 상태 시스템 워크플로|
|상태 시스템 워크플로(코드 분리)|워크플로 정의가 워크플로 마크업으로 표현되었고 별도의 코드 파일에 사용자 코드가 있는 상태 시스템 워크플로|

## <a name="to-add-a-new-item-to-a-workflow-project"></a>워크플로 프로젝트에 새 항목을 추가하려면

1.  에 **프로젝트** 메뉴를 클릭 하 여 **새 항목 추가**합니다.

     **새 항목 추가** 대화 상자가 열립니다.

2.  항목을 선택합니다.

     위의 표에서는 사용 가능한 Windows Workflow Foundation 선택 항목을 보여 줍니다.

3.  클릭 **추가** 워크플로 프로젝트에 항목을 추가 하 합니다.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)
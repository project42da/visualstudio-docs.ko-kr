---
title: "방법: 워크플로 프로젝트 (레거시)에 새 항목 추가 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- sequential workflows, adding to workflow projects
- workflows, adding new items
- state machine workflows, adding to workflow projects
- activities, adding to workflow projects
ms.assetid: 130cd83d-942d-437b-bbb5-8088ec0a6d79
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d2b0c644854f8f08ff7aeeb05f92fe3fd359f45e
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-a-new-item-to-a-workflow-project-legacy"></a>방법: 워크플로 프로젝트에 새 항목 추가(레거시)
제공 되는 레거시 Windows 워크플로 디자이너를 사용 하 여 워크플로 프로젝트를 만든 후 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 를 대상으로 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 추가할 수 있습니다 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 항목 및 다른 친숙 한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 항목을 사용자 프로젝트입니다.

 다음 표에서는 워크플로 프로젝트에 추가할 수 있는 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 항목을 보여 줍니다.

|항목|설명|
|----------|-----------------|
|동작|디자이너 코드 파일에 동작 정의가 있고 별도의 코드 파일에 사용자 코드가 있는 동작|
|동작(코드 분리)|워크플로 마크업으로 표현되었고 별도의 코드 파일에 사용자 코드가 있는 동작 정의|
|순차 워크플로(코드)|디자이너 코드 파일에 워크플로 정의가 있고 별도의 코드 파일에 사용자 코드가 있는 순차 워크플로|
|순차 워크플로(코드 분리)|워크플로 정의가 워크플로 마크업으로 표현되었고 별도의 코드 파일에 사용자 코드가 있는 순차 워크플로|
|상태 시스템 워크플로(코드)|디자이너 코드 파일에 워크플로 정의가 있고 별도의 코드 파일에 사용자 코드가 있는 상태 시스템 워크플로|
|상태 시스템 워크플로(코드 분리)|워크플로 정의가 워크플로 마크업으로 표현되었고 별도의 코드 파일에 사용자 코드가 있는 상태 시스템 워크플로|

### <a name="to-add-a-new-item-to-a-workflow-project"></a>워크플로 프로젝트에 새 항목을 추가하려면

1.  에 **프로젝트** 메뉴를 클릭 하 여 **새 항목 추가**합니다.

     **새 항목 추가** 대화 상자가 열립니다.

2.  항목을 선택합니다.

     위의 표에서는 사용 가능한 Windows Workflow Foundation 선택 항목을 보여 줍니다.

3.  클릭 **추가** 워크플로 프로젝트에 항목을 추가 하 합니다.

## <a name="see-also"></a>참고 항목

- [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)
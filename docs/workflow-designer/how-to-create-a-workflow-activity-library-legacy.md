---
title: "방법: 워크플로 활동 라이브러리 만들기 (레거시) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, activity library projects
- workflow activity libraries
- projects, workflow activity libraries
ms.assetid: fb5aa940-2ae8-4b52-b52c-51c20861a7b4
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 20d017081ee1246d672ec052ce9924c35120c11b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-a-workflow-activity-library-legacy"></a>방법: 워크플로 활동 라이브러리 만들기(레거시)
[!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 제공하는 레거시 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)]를 사용하여 워크플로 활동 라이브러리 프로젝트를 만들려면 다음 단계를 따릅니다. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
### <a name="to-create-a-workflow-activity-library-project"></a>워크플로 활동 라이브러리 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  에 **파일** 메뉴에서 **새로**를 선택한 후 **프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
3.  중 하나를 선택는 **.NET Framework 3.0** 옵션 또는 **.NET Framework 3.5** 목록 맨 위에 있는 드롭다운에서 **새 프로젝트** 레거시 디자이너에 액세스 하는 창입니다.  
  
    > [!NOTE]
    >  기본 옵션 [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] 은 **.NET Framework 4**합니다. 이 옵션은 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]을 대상으로 하는 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 응용 프로그램을 만드는 데 사용합니다.  
  
4.  에 **프로젝트 형식** 창에서 Visual C# 또는 Visual Basic (아래 **다른 언어**)를 클릭 한 **워크플로**합니다.  
  
5.  에 **템플릿** 창 선택 **워크플로 활동 라이브러리**합니다.  
  
6.  에 **이름** 상자에 프로젝트를 식별 하기 쉽도록 프로젝트를 설명 하는 이름을 입력 합니다.  
  
7.  에 **위치** 상자에서 프로젝트를 저장 하거나 클릭 하려는 디렉터리를 입력 **찾아보기** 찾습니다.  
  
     솔루션 디렉터리를 만들려면 프로젝트에 대 한 선택은 **솔루션용 디렉터리 만들기** 확인란을 선택 하 고에 이름을 입력는 **솔루션 이름** 상자 합니다.  
  
8.  **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 워크플로 프로젝트 만들기](../workflow-designer/creating-legacy-workflow-projects.md)   
 [레거시 활동 디자이너 사용](../workflow-designer/using-the-legacy-activity-designer.md)   
 [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)   
 [워크플로 활동 개발](http://msdn.microsoft.com/en-us/19876dfc-dfa5-4d52-b1f5-1d087474cc52)   
 [Windows Workflow Foundation 활동](http://msdn.microsoft.com/en-us/192c4c1e-afb6-4f58-ab11-2b5bbbc2d2c0)
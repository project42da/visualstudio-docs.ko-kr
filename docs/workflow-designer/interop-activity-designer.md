---
title: "Interop 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.Interop.UI
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 726bc2fa995d819b0e554e11439c85f9fdf19243
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="interop-activity-designer"></a>Interop 활동 디자이너
**Interop** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Interop> 활동입니다.  
  
## <a name="the-interop-activity"></a>Interop 활동  
 <xref:System.Activities.Statements.Interop> 활동은 워크플로의 <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName>에서 파생되는 형식의 실행을 관리합니다.  
  
### <a name="using-the-interop-activity-designer"></a>Interop 활동 디자이너 사용  
 **Interop** 활동 디자이너에서 확인할 수 있습니다는 **마이그레이션** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구 상자**탭 (또는 선택 **도구 상자** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 [마이그레이션](../workflow-designer/migration-activity-designers.md) 범주를 포함 하는 <xref:System.Activities.Statements.Interop> 활동에 표시 된 **도구 상자** 프로젝트는 전체를 대상으로 하는 경우 [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)]합니다.  
  
 전체를 사용 하도록 프로젝트 대상 다시 C# 프로젝트에 대 한 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여는 **솔루션 탐색기** 선택 하 고 **속성**합니다. 에 **응용 프로그램** 탭을는 **.NET Framework 4** 옵션에 **대상 프레임 워크**합니다. 선택 된 **예** 단추는 **대상 프레임 워크 변경** 이 변경을 확인 하 라는 표시 하는 대화 상자.  
  
 전체를 사용 하도록 프로젝트 대상 다시 VB 프로젝트의 경우 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여는 **솔루션 탐색기** 선택 하 고 **속성**합니다. 에 **컴파일** 탭을 클릭는 **고급 컴파일 옵션** 단추입니다. 선택 **.NET Framework 4** 에서 **대상 프레임 워크 목록** 클릭 하 고 **확인**합니다. 클릭는 **예** 단추는 **대상 프레임 워크 변경** 이 변경을 확인 하 라는 표시 하는 대화 상자.  
  
 **Interop** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로, 등 배치는 <xref:System.Activities.Statements.Sequence>합니다. 그렇기 때문에 프로그램 <xref:System.Activities.Statements.Interop> 기본값 활동 **DisplayName** Interop의 합니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **Interop** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.  
  
 클릭는 **찾아보려면 클릭...**  의 텍스트는 **ActivityType** 상자는 **Interop** 활동 디자이너를 표시 하려면 속성 표에 **찾아보기.Net 유형을 선택** 대화 상자입니다. 워크플로 3.0 또는 워크플로 3.5 활동의 형식(<xref:System.Workflow.ComponentModel.Activity>에서 파생된 형식)만 표시됩니다. [!INCLUDE[crabout](../test/includes/crabout_md.md)]참조 형식을 지정 하려면이 상자를 사용 하는 [찾아.NET 유형 선택 대화 상자](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md) 항목입니다.  
  
### <a name="the-interop-properties"></a>Interop 속성  
 다음 표에서는 <xref:System.Activities.Statements.Interop> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Interop> 활동의 이름입니다. 기본값은 Interop입니다. 표시 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|True|<xref:System.Activities.Statements.Interop> 활동에 포함된 활동의 형식을 지정합니다. 지정된 이 형식은 <xref:System.Workflow.ComponentModel.Activity>에서 파생된 것이어야 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [마이그레이션](../workflow-designer/migration-activity-designers.md)
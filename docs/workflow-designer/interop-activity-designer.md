---
title: "Interop 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.Interop.UI"
ms.assetid: 800a3403-ba86-41c4-8de1-c4fee9703eb1
caps.latest.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Interop 활동 디자이너
**Interop** 활동 디자이너는 <xref:System.Activities.Statements.Interop> 활동을 만들고 구성하는 데 사용됩니다.  
  
## Interop 활동  
 <xref:System.Activities.Statements.Interop> 활동은 워크플로의 <xref:System.Workflow.ComponentModel.Activity?displayProperty=fullName>에서 파생되는 형식의 실행을 관리합니다.  
  
### Interop 활동 디자이너 사용  
 **Interop** 활동 디자이너는 **도구 상자**의 **마이그레이션** 범주에 있습니다. 이 범주에 액세스하려면 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 상자**를 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 [!INCLUDE[netfx40_long](../workflow-designer/includes/netfx40_long_md.md)] 전체를 대상으로 하는 프로젝트인 경우 <xref:System.Activities.Statements.Interop> 활동이 포함된 [마이그레이션](../workflow-designer/migration-activity-designers.md) 범주는 **도구 상자**에만 표시됩니다.  
  
 C\# 프로젝트의 경우, **솔루션 탐색기**에서 해당 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택하여 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 전체를 사용하도록 프로젝트 대상을 조정할 수 있습니다.**응용 프로그램** 탭의 **대상 프레임워크**에서 **.NET Framework 4** 옵션을 선택합니다.이렇게 변경할 것인지 묻는 **대상 프레임워크 변경** 대화 상자가 나타나면 **예** 단추를 선택합니다.  
  
 VB 프로젝트의 경우, **솔루션 탐색기**에서 해당 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택하여 [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)] 전체를 사용하도록 프로젝트 대상을 조정할 수 있습니다.**컴파일** 탭에서 **고급 컴파일 옵션** 단추를 클릭합니다.**대상 프레임워크 목록**에서 **.Net Framework 4**를 선택하고 **확인**을 클릭합니다.이렇게 변경할 것인지 묻는 **대상 프레임워크 변경** 대화 상자가 나타나면 **예** 단추를 클릭합니다.  
  
 **Interop** 활동 디자이너를 **도구 상자**에서 끌어다가 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에나 놓을 수 있습니다.그러면 기본 **DisplayName**인 Interop이라는 이름의 <xref:System.Activities.Statements.Interop> 활동이 만들어집니다.**Interop** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A>을 편집할 수 있습니다.  
  
 **Interop**  활동 디자이너나 속성 표의 **ActivityType** 상자에서 **찾아보려면 클릭하십시오…** 텍스트를 클릭하여 **.Net 유형 선택** 대화 상자를 엽니다.워크플로 3.0 또는 워크플로 3.5 활동의 형식\(<xref:System.Workflow.ComponentModel.Activity>에서 파생된 형식\)만 표시됩니다.이 상자를 사용하여 형식을 지정하는 방법 [!INCLUDE[crabout](../test/includes/crabout_md.md)][.NET 유형 선택 대화 상자](../workflow-designer/browse-and-select-a-dotnet-type-dialog-box.md) 항목을 참조하십시오.  
  
### Interop 속성  
 다음 표에서는 <xref:System.Activities.Statements.Interop> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Interop> 활동의 이름입니다.기본값은 Interop입니다.표시 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.Interop.ActivityType%2A>|True|<xref:System.Activities.Statements.Interop> 활동에 포함된 활동의 형식을 지정합니다.지정된 이 형식은 <xref:System.Workflow.ComponentModel.Activity>에서 파생된 것이어야 합니다.|  
  
## 참고 항목  
 [마이그레이션](../workflow-designer/migration-activity-designers.md)
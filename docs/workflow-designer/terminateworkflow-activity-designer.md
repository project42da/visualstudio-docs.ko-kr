---
title: "TerminateWorkflow 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.TerminateWorkflow.UI"
ms.assetid: 08e632ed-0724-4fb4-9df1-f8d443eaf0ac
caps.latest.revision: 4
caps.handback.revision: 4
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# TerminateWorkflow 활동 디자이너
**TerminateWorkflow** 활동 디자이너는 <xref:System.Activities.Statements.TerminateWorkflow> 활동을 만들고 구성하는 데 사용됩니다.  
  
## TerminateWorkflow 활동  
 <xref:System.Activities.Statements.TerminateWorkflow> 활동은 워크플로의 실행을 종료합니다.  
  
### TerminateWorkflow 활동 디자이너 사용  
 **TerminateWorkflow** 활동 디자이너는 **도구 상자**의 **런타임** 범주에 있습니다. 이 범주에 액세스하려면 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 상자**를 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **TerminateWorkflow** 활동 디자이너를 **도구 상자**에서 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 아무 곳에나 놓을 수 있습니다.그러면 기본 **DisplayName**인 TerminateWorkflow라는 이름의 <xref:System.Activities.Statements.TerminateWorkflow> 활동이 만들어집니다.**TerminateWorkflow** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A>을 편집할 수 있습니다.  
  
### TerminateWorkflow 속성  
 다음 표에서는 <xref:System.Activities.Statements.TerminateWorkflow> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TerminateWorkflow> 활동의 이름입니다.기본값은 TerminateWorkflow입니다.표시 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.TerminateWorkflow.Exception%2A>|False|워크플로가 종료될 때 throw할 예외입니다.이 속성은 속성 표에서 설정합니다.|  
|<xref:System.Activities.Statements.TerminateWorkflow.Reason%2A>|False|워크플로가 왜 종료되었는지 설명하는 이유입니다.이 속성은 속성 표에서 설정합니다.|  
  
## 참고 항목  
 [런타임](../workflow-designer/runtime-activity-designers.md)   
 [Persist](../workflow-designer/persist-activity-designer.md)
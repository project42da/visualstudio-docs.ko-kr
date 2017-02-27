---
title: "Persist 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.Persist.UI"
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
caps.latest.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Persist 활동 디자이너
**Persist** 활동 디자이너는 <xref:System.Activities.Statements.Persist> 활동을 만들고 구성하는 데 사용됩니다.  
  
## Persist 활동  
 <xref:System.Activities.Statements.Persist> 활동은 워크플로를 디스크에 저장합니다\(가능한 경우\).<xref:System.Activities.Statements.TransactionScope> 활동과 같은 비지속성 영역에서는 <xref:System.Activities.Statements.Persist> 활동을 실행할 수 없습니다.비지속성 범위 내에서 <xref:System.Activities.Statements.Persist> 활동을 사용할 경우 런타임에 예외가 throw됩니다.  
  
### Persist 활동 디자이너 사용  
 **Persist** 활동 디자이너는 **도구 상자**의 **런타임** 범주에 있습니다. 이 범주에 액세스하려면 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 상자**를 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **도구 상자**의 **Persist** 활동 디자이너를 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 아무 곳에나 놓을 수 있습니다.그러면 기본 **DisplayName**인 Persist라는 이름의 <xref:System.Activities.Statements.Persist> 활동이 만들어집니다.**Persist** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A>을 편집할 수 있습니다.  
  
### Persist 속성  
 다음 표에서는 <xref:System.Activities.Statements.Persist> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-----------|--------|--------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Persist> 활동의 이름입니다.기본값은 Persist입니다.표시 이름이 꼭 필요하지 않더라도 표시 이름을 사용하는 것이 좋습니다.|  
  
## 참고 항목  
 [런타임](../workflow-designer/runtime-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
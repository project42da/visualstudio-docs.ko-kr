---
title: "Compensate 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.Compensate.UI"
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
caps.latest.revision: 5
caps.handback.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# Compensate 활동 디자이너
**Compensate** 활동 디자이너는 <xref:System.Activities.Statements.Compensate> 활동을 만들고 구성하는 데 사용됩니다.  
  
## Compensate 활동  
 <xref:System.Activities.Statements.Compensate> 활동은 <xref:System.Activities.Statements.CompensableActivity>에 포함된 활동에 대해 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>를 명시적으로 호출합니다.<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 또는 <xref:System.Activities.Statements.CompensableActivity>의 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>에서 <xref:System.Activities.Statements.Compensate> 활동을 사용하지 않는 경우 <xref:System.Activities.Statements.Compensate.Target%2A> 속성을 지정해야 합니다.  
  
 <xref:System.Activities.Statements.Compensate.Target%2A>에 의해 지정된 <xref:System.Activities.Statements.CompensationToken>은 <xref:System.Activities.Statements.CompensableActivity>의 <xref:System.Activities.Statements.CompensableActivity.Body%2A>가 성공적으로 완료된 후 <xref:System.Activities.Statements.CompensableActivity>를 명시적으로 확인하거나 보정하는 수단을 제공합니다.  
  
### Compensate 활동 디자이너 사용  
 **Compensate** 활동 디자이너는 **도구 상자**의 **트랜잭션** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 왼쪽의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **Compensate** 활동 디자이너를 **도구 상자**에서 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 아무 곳에나 놓을 수 있습니다.그러면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 Compensate라는 이름의 <xref:System.Activities.Statements.Compensate> 활동이 만들어집니다.**Compensate** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 값을 편집할 수 있습니다.  
  
### 보정 속성  
 다음 표에서는 <xref:System.Activities.Statements.CancellationScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.<xref:System.Activities.Activity.DisplayName%2A> 속성은 속성 표 또는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있지만 <xref:System.Activities.Statements.Compensate.Target%2A> 속성은 반드시 속성 표에서 편집해야 합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Compensate> 활동의 선택적 이름을 지정합니다.기본값은 Compensate입니다.|  
|<xref:System.Activities.Statements.Compensate.Target%2A>|True|이 <xref:System.Activities.Statements.Compensate> 활동의 <xref:System.Activities.Statements.CompensationToken>이 들어 있는 <xref:System.Activities.InArgument%601>을 지정합니다.|  
  
## 참고 항목  
 [트랜잭션](../workflow-designer/transaction-activity-designers.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Compensate Activity Designer](../workflow-designer/compensate-activity-designer.md)   
 [Confirm](../workflow-designer/confirm-activity-designer.md)   
 [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)
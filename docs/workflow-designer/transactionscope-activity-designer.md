---
title: "TransactionScope 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.TransactionScope.UI"
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
caps.latest.revision: 8
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# TransactionScope 활동 디자이너
**TransactionScope** 활동 디자이너는 <xref:System.Activities.Statements.TransactionScope> 활동을 만들고 구성하는 데 사용됩니다.  
  
## TransactionScope 활동  
 <xref:System.Activities.Statements.TransactionScope> 활동은 단일 트랜잭션에 포함된 활동을 실행합니다.해당 트랜잭션의 <xref:System.Activities.Statements.TransactionScope.Body%2A> 활동 및 다른 모든 참가자가 성공적으로 완료되면 트랜잭션이 커밋됩니다.  
  
### TransactionScope 활동 디자이너 사용  
 **TransactionScope** 활동 디자이너는 **도구 상자**의 **트랜잭션** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **TransactionScope** 활동 디자이너를 **도구 상자**에서 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 아무 곳에나 놓을 수 있습니다.그러면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 TransactionScope라는 이름의 <xref:System.Activities.Statements.TransactionScope> 활동이 만들어집니다.**TransactionScope** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A> 값을 편집할 수 있습니다.  
  
### TransactionScope 속성  
 다음 표에서는 <xref:System.Activities.Statements.TransactionScope> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.<xref:System.Activities.Activity.DisplayName%2A> 및 <xref:System.Activities.Statements.TransactionScope.Body%2A> 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면에서 편집할 수 있습니다.그러나 다른 속성은 속성 표에서 편집해야 합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TransactionScope> 활동의 선택적 이름입니다.기본값은 TransactionScope입니다.<xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|True|단일 트랜잭션에서 실행할 활동을 지정합니다.<xref:System.Activities.Statements.TransactionScope.Body%2A> 활동을 추가하려면 activity, drop an activity from the **도구 상자**의 활동을 "여기에 작업 놓기" 힌트 텍스트가 있는 **TransactionScope** 활동 디자이너의 **본문** 상자로 끌어 놓습니다.|  
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|True|이 <xref:System.Activities.Statements.TransactionScope>의 <xref:System.Transactions.IsolationLevel>을 지정합니다.|  
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|트랜잭션을 완료해야 하는 시간 간격\(시:분:초를 의미하는 00:00:00 형식\)을 지정합니다.기본값은 1분입니다\(00:01:00\).|  
|<xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>|True|트랜잭션이 중단되면 워크플로를 중단할지 여부를 나타내는 값을 지정합니다.|  
  
## 참고 항목  
 [트랜잭션](../workflow-designer/transaction-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)   
 [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)   
 [Compensate](../workflow-designer/compensate-activity-designer.md)   
 [Confirm](../workflow-designer/confirm-activity-designer.md)
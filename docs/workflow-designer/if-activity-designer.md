---
title: "If 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.If.UI"
ms.assetid: 930a8fa2-db98-43e9-ad6d-a85cc7a6519a
caps.latest.revision: 4
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# If 활동 디자이너
<xref:System.Activities.Statements.If> 활동은 조건을 평가하고 그 결과에 따라 활동을 실행합니다.이 활동은 절차적 모델링 스타일의 프로그래밍을 사용하는 경우에 가장 유용합니다.예를 들어 <xref:System.Activities.Statements.Sequence> 활동 또는 <xref:System.Activities.Statements.Parallel> 활동 안에 <xref:System.Activities.Statements.If> 활동이 중첩될 수 있습니다.<xref:System.Activities.Statements.Flowchart> 활동을 사용 중인 경우 <xref:System.Activities.Statements.FlowDecision> 활동을 대신 사용해 보십시오.  
  
## Workflow Designer의 If 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.If> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Statements.If.Condition%2A>|True|실행할 자식 활동을 결정하는 조건입니다.<xref:System.Activities.Statements.If.Condition%2A>을 설정하려면 **If** 활동 디자이너의 **조건** 상자 또는 속성 표에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 식을 입력합니다.|  
|<xref:System.Activities.Statements.If.Else%2A>|False|<xref:System.Activities.Statements.If.Condition%2A>이 **false**인 경우에 실행할 활동입니다.<xref:System.Activities.Statements.If.Else%2A> 분기에서 실행할 활동을 추가하려면 **도구 상자**의 활동을 "여기에 작업 놓기" 힌트 텍스트가 있는 **If** 활동 디자이너의 **Else** 상자로 끌어 놓습니다.|  
|<xref:System.Activities.Statements.If.Then%2A>|False|<xref:System.Activities.Statements.If.Condition%2A>이 **true**인 경우에 실행할 활동입니다.<xref:System.Activities.Statements.If.Then%2A> 분기에서 실행할 활동을 추가하려면 **도구 상자**의 활동을 "여기에 작업 놓기" 힌트 텍스트가 있는 **If** 활동 디자이너의 **Then** 상자로 끌어 놓습니다.|  
  
## 참고 항목  
 [Sequence](../workflow-designer/sequence-activity-designer.md)   
 [Parallel](../workflow-designer/parallel-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)
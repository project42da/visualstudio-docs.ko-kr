---
title: "방법: 선언적 규칙 조건 만들기(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "조건문, 선언적 규칙 조건"
  - "선언적 규칙 조건"
  - "규칙 조건 편집기 대화 상자"
ms.assetid: 804b6129-c433-408f-a424-46987967730c
caps.latest.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 방법: 선언적 규칙 조건 만들기(레거시)
이 항목에서는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 하는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]를 사용하여 규칙 조건을 선언하는 방법에 대해 설명합니다.  
  
 조건문은 **True** 또는 **False**로 계산됩니다.선언적 규칙 조건은 [규칙 조건 편집기 대화 상자\(레거시\)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)를 사용하여 만들고 워크플로에 대해 XML로 저장하는 조건문입니다.여러 조건자를 결합하는 부울 대수와 워크플로 상태를 비교하는 조건자가 포함될 수 있습니다.  
  
 선언적 규칙 조건은 기본적으로 제공되는 다음과 같은 Windows Workflow Foundation 활동에 사용됩니다.  
  
-   [ConditionedActivityGroup \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65017)  
  
-   [IfElseBranchActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65034)  
  
-   [ReplicatorActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65039)  
  
-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
-   [SequentialWorkflowActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65040)  
  
-   [StateMachineWorkflowActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65045)  
  
### 규칙 조건 편집기를 사용하여 선언적 규칙 조건을 만들려면  
  
1.  활동의 **속성** 창에서 해당 활동에 따라 **Condition** 속성 또는 **UntilCondition** 속성을 클릭합니다.  
  
2.  속성 목록에서 **선언적 규칙 조건**을 선택합니다.  
  
3.  **Condition** 또는 **UntilCondition** 속성을 확장합니다.  
  
4.  **ConditionName** 속성을 클릭합니다.  
  
5.  **ConditionName** 줄임표 **\[…\]**를 클릭하여 **조건 선택** 대화 상자를 엽니다.  
  
6.  **새 조건**을 클릭하여 **규칙 조건 편집기** 대화 상자를 엽니다.  
  
7.  **조건** 텍스트 상자에 조건의 식을 입력합니다.  
  
     조건식을 만드는 방법에 대한 자세한 내용은 [규칙 조건 편집기 대화 상자\(레거시\)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)를 참조하십시오.  
  
8.  조건식을 만들고 나면 **확인**을 클릭하여 대화 상자를 닫고 할당된 이름으로 규칙 조건을 만듭니다.  
  
     **조건 선택** 대화 상자가 열립니다.  
  
     **조건 선택** 대화 상자 사용 방법에 대한 자세한 내용은 [조건 선택 대화 상자\(레거시\)](../workflow-designer/select-condition-dialog-box-legacy.md)를 참조하십시오.  
  
## 참고 항목  
 [레거시 워크플로 활동](../workflow-designer/legacy-workflow-activities.md)   
 [ConditionedActivityGroup 활동 사용](http://go.microsoft.com/fwlink?LinkID=65066)   
 [IfElseBranchActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65075)   
 [ReplicatorActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65080)   
 [WhileActivity 활동 사용](http://go.microsoft.com/fwlink?LinkID=65091)   
 [규칙 조건 편집기 대화 상자\(레거시\)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)   
 [조건 선택 대화 상자\(레거시\)](../workflow-designer/select-condition-dialog-box-legacy.md)   
 [워크플로에서 조건 사용](http://go.microsoft.com/fwlink?LinkID=65009)
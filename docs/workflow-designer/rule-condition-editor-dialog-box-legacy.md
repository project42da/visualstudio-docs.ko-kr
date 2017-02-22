---
title: "규칙 조건 편집기 대화 상자(레거시) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI"
helpviewer_keywords: 
  - "규칙 조건 대화 상자"
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
caps.latest.revision: 6
caps.handback.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# 규칙 조건 편집기 대화 상자(레거시)
이 항목에서는 레거시 [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]에서 **규칙 조건 편집기** 대화 상자를 사용하는 방법에 대해 설명합니다.레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.  
  
 **규칙 조건 편집기** 대화 상자를 사용하여 선언적 규칙 조건을 만들고 수정합니다.이러한 규칙 조건은 기본적으로 제공되는 다음과 같은 Windows Workflow Foundation 활동에 대한 속성으로 나타납니다.  
  
-   [ConditionedActivityGroup \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65017)  
  
-   [IfElseBranchActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65034)  
  
-   [ReplicatorActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65039)  
  
-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
-   [SequentialWorkflowActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65040)  
  
-   [StateMachineWorkflowActivity \(영문 페이지일 수 있음\)](http://go.microsoft.com/fwlink?LinkID=65045)  
  
 **규칙 조건 편집기** 대화 상자에 액세스하려면 [조건 선택 대화 상자\(레거시\)](../workflow-designer/select-condition-dialog-box-legacy.md)를 사용합니다.  
  
 다음 표에서는 **규칙 조건 편집기** 대화 상자의 UI\(사용자 인터페이스\) 요소에 대해 설명합니다.  
  
|UI 요소|설명|  
|-----------|--------|  
|**조건:**|규칙 조건을 위한 식을 입력합니다.|  
|**확인**|규칙 조건을 저장하려면 클릭합니다.|  
  
## 조건식 입력  
 조건식은 텍스트로 입력합니다.**this.**를 편집기에 입력하여 워크플로에 사용된 필드, 속성 및 메서드를 IntelliSense 형식의 메뉴를 사용하여 참조할 수 있습니다.또는 워크플로 멤버 이름을 직접 입력할 수도 있습니다.AND, OR, NOT 등의 논리 연산자를 조건에 추가할 수 있습니다.조건자를 추가할 수도 있습니다.조건자는 이항 연산자 한 개와 피연산자 두 개로 이루어집니다.지원되는 이항 연산자는 **\=\=**, **\>**, **\<**, **\>\=** 및 **\<\=**입니다.지원되는 피연산자는 상수 값, 산술 함수 및 범위 Public 멤버입니다.  
  
 비교 형식을 지정하고 **null** 또는 빈 문자열과 비교할 수 있습니다.`this.Address.State == "WA"`와 같이 복합 형식을 포함하는 변수에서 멤버에 대한 중첩 호출을 수행할 수 있습니다.  
  
 규칙 조건 편집기는 다음과 같은 연산자를 지원합니다.  
  
-   관계형 연산자: \=\=, \=, \!\=  
  
-   비교 연산자: \<, \<\=, \>, \>\=  
  
-   산술 연산자: \+, \- , \*, \/, MOD  
  
-   논리 연산자: AND, &&, OR, &#124;&#124;, NOT, \!  
  
-   비트 연산자: &, &#124;  
  
 식 연산자 우선 순위는 C\# 연산자 우선 순위 규칙을 따릅니다.  
  
 규칙 조건 편집기는 다음과 같은 숫자 식을 지원합니다.  
  
 this.i \=\= 1D\(1.0으로 해석됨\)  
  
 this.i \=\= 1E1\(10.0으로 해석됨\)  
  
 this.i \=\= 1L\(long 형식으로 해석됨\)  
  
 this.i \=\= 1M\(10진수로 해석됨\)  
  
 this.i \=\= 1F\(single 형식으로 해석됨\)  
  
 this.i \=\= 1U\(unsigned int 형식으로 해석됨\)  
  
 조건에 대한 자세한 내용은 [워크플로에서 조건 사용](http://go.microsoft.com/fwlink?LinkID=65009)\(영문 페이지일 수 있음\)을 참조하십시오.  
  
## 참고 항목  
 [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)   
 [ConditionedActivityGroup 클래스](http://go.microsoft.com/fwlink?LinkID=65017)   
 [ReplicatorActivity 클래스](http://go.microsoft.com/fwlink?LinkID=65039)   
 [WhileActivity 클래스](http://go.microsoft.com/fwlink?LinkID=65049)   
 [조건 선택 대화 상자\(레거시\)](../workflow-designer/select-condition-dialog-box-legacy.md)   
 [워크플로에서 조건 사용](http://go.microsoft.com/fwlink?LinkID=65009)   
 [Windows Workflow Foundation용 레거시 디자이너 UI 도움말](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)
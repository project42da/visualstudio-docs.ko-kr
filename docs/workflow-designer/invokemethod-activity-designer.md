---
title: "InvokeMethod 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.InvokeMethod.UI"
ms.assetid: 15e6efdc-52ca-46d8-9c5e-063f7c8265a6
caps.latest.revision: 6
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# InvokeMethod 활동 디자이너
**InvokeMethod** 디자이너는 <xref:System.Activities.Statements.InvokeMethod> 활동을 만들고 구성하는 데 사용됩니다.  
  
## InvokeMethod 활동  
 <xref:System.Activities.Statements.InvokeMethod>는 지정한 개체 또는 형식의 public 메서드를 호출합니다.  
  
### InvokeMethod 활동 디자이너 사용  
 **InvoikeMethod** 활동 디자이너는 **도구 상자**의 **기본 형식** 범주에 있습니다. 이 범주에 액세스하려면 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]의 **도구 상자** 탭을 클릭하거나, **보기** 메뉴에서 **도구 모음**을 선택하거나, Ctrl\+Alt\+X를 누릅니다.  
  
 **InvokeMethod** 활동 디자이너를 **도구 상자**에서 끌어다가 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 <xref:System.Activities.Statements.Sequence> 등 일반적으로 활동을 배치하는 아무 곳에나 놓을 수 있습니다.그러면 기본 <xref:System.Activities.Activity.DisplayName%2A>인 InvokeMethod라는 이름의 <xref:System.Activities.Statements.InvokeMethod> 활동이 만들어집니다.**InvokeMethod** 활동 디자이너의 머리글 또는 속성 표의 **DisplayName** 상자에서 <xref:System.Activities.Activity.DisplayName%2A>을 편집할 수 있습니다.  
  
### InvokeMethod 속성  
 다음 표에서는 <xref:System.Activities.Statements.InvokeMethod> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|사용법|  
|-----------|--------|---------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeMethod> 활동의 이름입니다.기본값은 InvokeMethod입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.InvokeMethod.MethodName%2A>|True|작업이 실행될 때 호출할 메서드의 이름입니다.호출되는 메서드는 **public**으로 선언해야 합니다.이 속성은 디자이너 화면에서 편집할 수 있습니다.이 속성은 필수 속성입니다.|  
|<xref:System.Activities.Statements.InvokeMethod.Parameters%2A>|False|호출되는 메서드의 매개 변수 컬렉션입니다.메서드 시그니처에 표시되는 것과 동일한 순서대로 컬렉션에 매개 변수를 추가해야 합니다.속성 표의 **매개 변수** 필드에서 줄임표 단추를 클릭하면 **매개 변수** 대화 상자가 표시되어 이 속성을 설정할 수 있습니다.**인수 만들기** 단추를 클릭하여 매개 변수를 추가합니다.|  
|<xref:System.Activities.Statements.InvokeMethod.Result%2A>|False|메서드 호출의 반환 값입니다.|  
|<xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>|True|메서드가 비동기적으로 호출되는지 여부를 지정합니다.기본값은 **False**입니다.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>|False|호출할 메서드가 포함된 개체입니다.이 속성은 디자이너 화면에서 편집할 수 있습니다.<br /><br /> <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> 또는 <xref:System.Activities.Statements.InvokeMethod.TargetType%2A>을 설정해야 합니다.|  
|<xref:System.Activities.Statements.InvokeMethod.TargetType%2A>|False|<xref:System.Activities.Statements.InvokeMethod.TargetObject%2A>의 형식입니다.이 속성은 디자이너 화면에서 편집할 수 있습니다.이 속성은 호출된 메서드가 정적인 경우에만 설정해야 합니다.|  
  
 매개 변수를 C\# **out** 매개 변수\(예: `Method1(out myParam)),`로 전달하려면 **InOutArgument** 대신 **OutArgument**를 사용해야 합니다.  
  
 **TargetObject** or **Result**라는 인수가 있는 메서드는 <xref:System.Activities.Statements.InvokeMethod> 활동을 사용하여 호출할 수 없습니다.그 이유는 <xref:System.Activities.Statements.InvokeMethod> 활동이 <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A>, <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> 및 <xref:System.Activities.Statements.InvokeMethod.Result%2A>를 <xref:System.Activities.Activity.CacheMetadata%2A>에 등록하기 때문입니다.  
  
 <xref:System.Activities.Activity.CacheMetadata%2A>에 매개 변수를 등록하는 알고리즘이 다음 목록에 나와 있습니다.  
  
1.  <xref:System.Activities.Statements.InvokeMethod.TargetObject%2A> 인수를 등록합니다.  
  
2.  <xref:System.Activities.Statements.InvokeMethod.Result%2A> 인수를 등록합니다.  
  
3.  <xref:System.Activities.Statements.InvokeMethod.Parameters%2A> 컬렉션을 반복하고 각 인수를 등록합니다.  
  
 다음과 같은 메시지와 함께 <xref:System.Activities.InvalidWorkflowException> 형식의 예외가 발생합니다. 'InvokeMethod': 이름이 'TargetObject'인 변수\(RuntimeArgument 또는 DelegateArgument\) 변수가 이미 있습니다.이름은 환경 범위 내에서 고유해야 합니다.  
  
 <xref:System.Activities.Statements.InvokeMethod.TargetType%2A> 및 <xref:System.Activities.Statements.InvokeMethod.RunAsynchronously%2A>는 워크플로 인수가 아니고 따라서 <xref:System.Activities.Activity.CacheMetadata%2A> 메서드에서 <xref:System.Activities.Statements.InvokeMethod> 활동의 <xref:System.Activities.Statements.InvokeMethod.GenericTypeArguments%2A> 컬렉션에 등록되어 있지 않기 때문에 이러한 제한이 적용되지 않습니다.  
  
## 참고 항목  
 [기본 형식](../workflow-designer/primitives-activity-designers.md)   
 [Assign](../workflow-designer/assign-activity-designer.md)   
 [Delay](../workflow-designer/delay-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)
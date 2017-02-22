---
title: "ForEach&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "System.Activities.Statements.ForEach`1.UI"
ms.assetid: 67097b3a-fcf5-4a72-beb1-2c7784151a86
caps.latest.revision: 5
caps.handback.revision: 5
author: "ErikRe"
ms.author: "erikre"
manager: "erikre"
---
# ForEach&lt;T&gt; 활동 디자이너
<xref:System.Activities.Statements.ForEach%601> 활동은 지정된 <xref:System.Activities.Statements.ForEach%601.Values%2A> 컬렉션의 각 항목에 대해 <xref:System.Activities.Statements.ForEach%601.Body%2A>에 포함된 활동을 실행합니다.  
  
## Workflow Designer의 ForEach\<T\> 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.ForEach%601> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|용도|  
|-----------|--------|--------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ForEach%601> 활동의 이름입니다.기본값은 ForEach\<Int32\>입니다.<xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.ForEach%601.Values%2A>|True|반복할 항목의 컬렉션입니다.<xref:System.Activities.Statements.ForEach%601.Values%2A>를 설정하려면 **ForEach\<T\>** 활동 디자이너의 **값** 상자 또는 속성 표에 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 식을 입력합니다.|  
|*TypeArgument*|True|제네릭 매개 변수 *T*에 지정된 <xref:System.Activities.Statements.ForEach%601.Values%2A> 컬렉션의 항목 형식입니다.기본적으로 *TypeArgument*는 **Int32**로 설정됩니다.이 형식을 변경하려면 속성 표의 콤보 상자에서 *TypeArgument*의 값을 변경합니다.|  
  
 기본적으로 루프 반복기의 이름은 **item**입니다.<xref:System.Activities.Statements.ForEach%601> 활동 디자이너에서 반복기 변수의 이름을 변경할 수 있습니다.루프 반복기는 <xref:System.Activities.Statements.ForEach%601> 활동의 자식에 포함된 식에서 사용할 수 있습니다.  
  
## 참고 항목  
 [ParallelForEach\<T\>](../workflow-designer/parallelforeach-t-activity-designer.md)   
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)
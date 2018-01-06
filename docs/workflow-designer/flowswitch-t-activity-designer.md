---
title: "FlowSwitch&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Core.Presentation.FlowSwitchLink.UI
- System.Activities.Statements.FlowSwitch`1.UI
- System.Activities.Core.Presentation.FlowSwitchLink`1.UI
- System.Activities.Core.Presentation.FlowSwitchLinkIdentifier.UI
ms.assetid: 5b9c5afe-7499-4ee8-8c33-28aff14bde07
caps.latest.revision: "4"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: c3e757d8ffea7e91c2d5e51bc4a04e6225d1064f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="flowswitchlttgt-activity-designer"></a>FlowSwitch&lt;T&gt; 활동 디자이너
<xref:System.Activities.Statements.FlowSwitch%601> 활동은 두 개 이상의 대안 분기가 필요할 때 일치 기준에 따라 제어 흐름에 대한 분기를 제공하는 조건 노드입니다. 흐름 분기에 두 경로만 필요한 경우 <xref:System.Activities.Statements.FlowDecision> 활동을 대신 사용합니다.  
  
## <a name="the-flowswitcht-activity"></a>FlowSwitch를 < T\> 활동  
 <xref:System.Activities.Statements.FlowSwitch%601> 활동에 포함 된 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 형식의 값을 반환 하 *T* (제네릭 매개 변수로 지정) 평가 될 때입니다. 또한 이 활동에는 가능한 계산 결과와 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 개체 집합 간의 고유 매핑을 지정하는 <xref:System.Activities.Statements.FlowNode> 집합도 포함되어 있습니다. <xref:System.Activities.Statements.FlowNode> 실행은 한 형식의 개체가 *T* 의 계산 된 값과 일치 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>합니다. 일치하는 항목이 없는 case에 대해 선택적으로 <xref:System.Activities.Statements.FlowSwitch%601.Default%2A> case를 제공할 수 있습니다.  
  
### <a name="using-the-flowswitcht-activity-designer"></a>FlowSwitch를 사용 하 여\<T > 활동 디자이너  
 **FlowSwitch\<T >** 활동 디자이너에서 확인할 수 있습니다는 **순서도** 의 범주는 **도구 상자**는 를클릭하여액세스**도구 상자** 탭의 왼쪽에는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)  
  
 **FlowSwitch\<T >** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 내에서 노출 한 **순서도** 활동 디자이너입니다. 사용 하 여는 **유형 선택** 형식을 지정 하려면 표시 창입니다 (사용 하 여 코드에서 관련 된는 <xref:System.Activities.Statements.FlowSwitch%601> 제네릭 매개 변수에 의해) 계산에서 얻은 <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>합니다. 이 절차에서는 만듭니다는 <xref:System.Activities.Statements.FlowSwitch%601> 라는 작업 **스위치** 내에서 <xref:System.Activities.Statements.Flowchart> 활동입니다. <xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 에 입력할 수 있습니다는 **식** 상자는 **속성** 힌트 텍스트가 "VB 식 입력" 이라고 표시를 클릭 하 여 창.  
  
 마우스를 위에 놓았을 **FlowSwitch\<T >** 활동 디자이너를 연결 하는 데 사용 되는 정사각형 핸들이 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 가장자리 주위에 표시를 합니다. 끌어 놓은 후는 **FlowSwitch < T\>**  활동 디자이너와 기타 활동 디자이너에는 **순서도**, <xref:System.Activities.Activity> 나타나는 개체를 함께 연결할 준비가 되었습니다. 실행 순서를 지정 합니다. 중 하나를 만드는 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 와 관련 된는 <xref:System.Activities.Statements.FlowSwitch%601>의 주위에 있는 정사각형 case 핸들 중 하나를 클릭는 **FlowSwitch < T\>**  핸들 중 하나로 끕니다 (마우스 단추를 누른 채)에서 위치 디자이너 위로 마우스를 가져가면 대상 활동 주변 비슷한 방식으로 나타납니다. 릴리스 마우스 단추 및에서 화살표는 **FlowSwitch < T\>**  대상 디자이너를이 case를 표시 합니다. 기본값은 화살표 위에 표시 된이 사례에서 편집할 수 있습니다에 대 한는 **대/소문자** 상자는 **속성** 창.  
  
### <a name="the-flowswitcht-properties"></a>FlowSwitch를 < T\> 속성  
 다음 표에서는 <xref:System.Activities.Statements.FlowSwitch%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표 또는 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A>|True|실행 경로에서 전환할 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>를 결정하기 위해 계산할 식을 지정합니다.|  
|<xref:System.Activities.Statements.FlowSwitch%601.Cases%2A>|False|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 계산으로 얻은 가능한 결과와 <xref:System.Activities.Statements.FlowNode> 개체 집합 간의 고유 매핑을 지정합니다.|  
|<xref:System.Activities.Statements.FlowSwitch%601.Default%2A>|True|<xref:System.Activities.Statements.FlowSwitch%601.Expression%2A> 계산이 <xref:System.Activities.Statements.FlowSwitch%601.Cases%2A> 개체에 포함된 값 중 하나와 일치하지 않을 경우의 매핑을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [순서도](../workflow-designer/flowchart-activity-designers.md)   
 [순서도](../workflow-designer/flowchart-activity-designer.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)
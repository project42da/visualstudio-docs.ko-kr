---
title: "While 활동 디자이너 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.While.UI
ms.assetid: ea008091-2e4c-4f64-bfa5-afb919552446
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: b70e0c66813c474d5711538843da93a669df88d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="while-activity-designer"></a>While 활동 디자이너
<xref:System.Activities.Statements.While> 활동에 포함 된 활동을 실행 합니다. 해당 <xref:System.Activities.Statements.While.Body%2A> 동안 지정 된 <xref:System.Activities.Statements.While.Condition%2A> 계산 **true**합니다. 포함된 활동이 실행되지 않을 수도 있습니다. 포함된 활동이 적어도 한 번은 실행되도록 하려면 그 대신 <xref:System.Activities.Statements.DoWhile> 활동을 사용하세요.  
  
## <a name="while-properties-in-workflow-designer"></a>Workflow Designer의 While 속성  
 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.While> 활동 속성을 보여 주고 디자이너에서 이러한 속성을 사용하는 방법을 설명합니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|머리글에 <xref:System.Activities.Statements.While> 활동 디자이너의 이름을 지정합니다. 기본값은 While입니다. 값을 편집할 수는 **속성** 창 또는 활동 디자이너 머리글에서 직접 합니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.While.Body%2A>|False|실행할 활동을 포함 하는 동안는 <xref:System.Activities.Statements.While.Condition%2A> 계산 **true**합니다.|  
|<xref:System.Activities.Statements.While.Condition%2A>|True|[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]의 활동을 실행할지 여부를 결정하기 위해 평가하는 <xref:System.Activities.Statements.While.Body%2A> 식을 포함합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [제어 흐름](../workflow-designer/control-flow-activity-designers.md)   
 [DoWhile](../workflow-designer/dowhile-activity-designer.md)
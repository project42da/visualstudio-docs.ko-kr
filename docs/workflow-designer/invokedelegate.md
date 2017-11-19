---
title: InvokeDelegate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
caps.latest.revision: "3"
ms.author: sdanie
manager: erikre
ms.openlocfilehash: 180e9ca5ae635608ca3d7f9cf24abab13c8076a6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="invokedelegate"></a>InvokeDelegate
**InvokeDelegate** 디자이너 만들고 구성 하는 데 사용 됩니다는 <xref:System.Activities.Statements.InvokeDelegate> 활동입니다.  
  
## <a name="the-invokedelegate-activity"></a>InvokeDelegate 활동  
 <xref:System.Activities.Statements.InvokeDelegate>는 public 대리자를 호출합니다.  
  
### <a name="using-the-invokedelegate-activity-designer"></a>InvokeDelegate 활동 디자이너 사용  
 **InvokeDelegate** 활동 디자이너에서 확인할 수 있습니다는 **기본 형식** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구상자** 탭 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴 또는 CRTL + ALT + X.)  
  
 **InvokeDelegate** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나은 일반적으로 등 활동을 배치와 내부는 <xref:System.Activities.Statements.Sequence>합니다. 그러면 기본 <xref:System.Activities.Statements.InvokeDelegate>인 InvokeDelegate라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **InvokeDelegate** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.  
  
### <a name="the-invokedelegate-properties"></a>InvokeDelegate 속성  
 다음 표에서는 <xref:System.Activities.Statements.InvokeDelegate> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있으며 일부 속성은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 디자이너 화면에서 편집할 수 있습니다.  
  
|속성 이름|필수|용도|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> 활동의 이름입니다. 기본값은 InvokeDelegate입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|  
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|작업이 실행될 때 호출할 <xref:System.Activities.ActivityDelegate>의 이름입니다. 이 속성은 디자이너 화면에서 편집할 수 있습니다. 이 속성은 필수 속성입니다.|  
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|호출한 대리자의 인수 컬렉션입니다. 매개 변수 개체의 이름에 키는 <xref:System.Activities.ActivityDelegate> 이며 값은 인수를 식에서 해당 평가 되 고 해당 매개 변수 개체에 할당 합니다. 속성 그리드에서에서 줄임표 단추를 클릭는 **DelegateArguments** 표시 필드는 **DelegateArguments** 대화가이 속성을 설정할 수 있습니다. 클릭는 **인수 만들기** 필드는 인수를 추가 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [방법: 워크플로 디자이너에서 활동 대리자 정의 및 사용](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)
---
title: 워크플로 디자이너-InvokeDelegate
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3d68fa1b777663ff8975f8ce99100d8eddc5f05d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate** 디자이너 만들고 구성 하는 데 사용 됩니다는 <xref:System.Activities.Statements.InvokeDelegate> 활동입니다.

## <a name="the-invokedelegate-activity"></a>InvokeDelegate 활동

<xref:System.Activities.Statements.InvokeDelegate>는 public 대리자를 호출합니다.

### <a name="using-the-invokedelegate-activity-designer"></a>InvokeDelegate 활동 디자이너 사용

**InvokeDelegate** 활동 디자이너에서 확인할 수 있습니다는 **기본 형식** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구상자** 워크플로 디자이너 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴 또는 CRTL + ALT + X.)

**InvokeDelegate** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은 일반적으로, 등 배치 변한 경우 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 그러면 기본 <xref:System.Activities.Statements.InvokeDelegate>인 InvokeDelegate라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 의 헤더에서 편집할 수는 **InvokeDelegate** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다.

### <a name="the-invokedelegate-properties"></a>InvokeDelegate 속성

다음 표에서는 <xref:System.Activities.Statements.InvokeDelegate> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다. 이러한 속성은 속성 표에서 편집할 수 있습니다 및 일부 워크플로 Designerdesigner 화면에서 편집할 수 있습니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> 활동의 이름입니다. 기본값은 InvokeDelegate입니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|작업이 실행될 때 호출할 <xref:System.Activities.ActivityDelegate>의 이름입니다. 이 속성은 디자이너 화면에서 편집할 수 있습니다. 이 속성은 필수 속성입니다.|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|호출한 대리자의 인수 컬렉션입니다. 매개 변수 개체의 이름에 키는 <xref:System.Activities.ActivityDelegate> 이며 값은 인수를 식에서 해당 평가 되 고 해당 매개 변수 개체에 할당 합니다. 속성 그리드에서에서 줄임표 단추를 클릭는 **DelegateArguments** 표시 필드는 **DelegateArguments** 대화가이 속성을 설정할 수 있습니다. 클릭는 **인수 만들기** 필드는 인수를 추가 합니다.|

## <a name="see-also"></a>참고자료

- [방법: 워크플로 디자이너에서 활동 대리자 정의 및 사용](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)
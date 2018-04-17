---
title: 스위치&lt;T&gt; 활동 디자이너 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Presentation.ModelItemKeyValuePair.UI
- System.Activities.Statements.Switch`1.UI
ms.assetid: 18a6c96e-49a9-4356-ab61-fbd7e3ab44bb
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2bfdcc86531105e3b2c743a8aa0f88cda844efc7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="switchlttgt-activity-designer"></a>스위치&lt;T&gt; 활동 디자이너
<xref:System.Activities.Statements.Switch%601> 활동은 지정된 식을 계산하고 연관된 키가 계산에서 얻은 값과 일치하는 활동 컬렉션의 활동을 실행합니다.

 **스위치 < T\>**  활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Switch%601> Windows 워크플로 디자이너에서 활동입니다.

## <a name="the-switchtactivity"></a>스위치\<T > 활동
 <xref:System.Activities.Statements.Switch%601> 활동에는 <xref:System.Activities.Statements.Switch%601.Expression%2A> 및 <xref:System.Activities.Statements.Switch%601.Cases%2A> 사전이 포함되어 있습니다. 각각의 경우 사전에 포함 하는 쌍으로 이루어져는 *키* 및 역할을 해당 하는 활동 *값*합니다. <xref:System.Activities.Statements.Switch%601> 활동은 <xref:System.Activities.Statements.Switch%601.Expression%2A>을 계산한 후 각 키와 비교하고, 일치하는 항목이 있으면 해당 작업이 실행됩니다. 사전 키는 사전의 같음 비교자로 정의된 같음 형식에 따라 고유해야 하므로 일치하는 항목은 하나만 존재할 수 있습니다. 일치하는 항목이 없으면 <xref:System.Activities.Statements.Switch%601.Default%2A> 활동이 실행됩니다.

## <a name="how-to-use-the-switcht-activity-designer"></a>스위치를 사용 하는 방법\<T > 활동 디자이너
 **스위치\<T >** 활동 디자이너에서 확인할 수 있습니다는 **제어 흐름** 의 범주는 **도구 상자**는 를클릭하여액세스**도구 상자** 탭에 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.) 놓으면는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)], 표시는 **유형 선택** 제네릭 형식을 지정할 수 있도록 대화 *T* 에 사용 된 <xref:System.Activities.Statements.Switch%601> 활동입니다. 기본값은 **Int32**합니다. 제네릭 형식 *T* 를 선택 하면 한 **스위치 < T\>**  디자이너가 워크플로 디자이너에 추가 됩니다.

 다음의 속성은 **스위치 < T\>**  디자이너입니다. 이러한 모든 속성을 속성 표에서 편집할 수 있습니다. 일부 속성은 디자이너 화면에서도 편집할 수 있습니다.

 다음 표에서는 가장 유용한 <xref:System.Activities.Statements.Switch%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Switch%601> 활동 디자이너의 이름을 지정합니다. 기본값은 스위치 < i n t 32\>합니다. 값을 편집할 수는 **속성** 창 하거나 디자이너 머리글에서 직접 합니다.<br /><br /> <xref:System.Activities.Activity.DisplayName%2A>은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.Switch%601.Expression%2A>|True|실행할 case를 결정하기 위해 case 컬렉션의 키와 비교하는 데 사용할 식을 지정합니다.|
|<xref:System.Activities.Statements.Switch%601.Default%2A>||일치하는 항목이 없는 경우에 실행할 활동을 지정합니다. 클릭는 **활동 추가** 열려는 디자이너에서 단추는 **기본** 상자 활동을 삭제할 수 있습니다.|
|<xref:System.Activities.Statements.Switch%601.Cases%2A>||계산할 case를 지정합니다. Case를 추가 하려면 클릭는 **새 사례를 추가** 아래쪽의 단추 **스위치\<T >** 디자이너입니다. 텍스트 상자에 단추가 바뀝니다 (스위치를 추가 하는 경우 제네릭 형식이 선택 콤보 상자\<T >는 String 또는 Enum). 키를 추가한 후의 **값을 대/소문자** 상자 case 영역이 확장 되 고 작업을 삭제할 수 있습니다 위치는 사례에 대 한 실행 논리를 정의 하려면 "여기에 작업 놓기" 힌트 텍스트가 합니다.|

 case 키가 중복되지 않는 한 여러 case를 추가할 수 있습니다. 키가 중복되는 경우 지정한 case 키가 이미 있으며 다른 키를 선택해야 한다는 메시지가 표시된 오류 대화 상자가 나타납니다. 에 **스위치\<T >** 디자이너, 한 case 영역만 한 번에 확장 된 뷰에 있을 수 있습니다. case 영역이 축소된 보기로 되어 있는 경우 case 영역을 클릭하면 보기가 확장됩니다. 축소된 case는 디자이너에서 case 내 활동의 표시 이름(있는 경우)이 case 오른쪽에 표시됩니다. 표시는 **활동 추가** 단추를 클릭 하면 case가 확장 되어 고 활동을 추가할 수 있습니다.

 기존 case의 키를 클릭하면 키 레이블이 텍스트 상자로 바뀌어 case 키를 편집할 수 있게 됩니다.

 case를 삭제하는 방법은 두 가지입니다.

1.  case를 선택하여 삭제합니다.

2.  상황에 맞는 메뉴를 표시 하 고 선택할 경우 마우스 선택 **삭제**합니다.

 삭제하려면 case 자체를 선택해야 합니다. case 내의 활동을 선택하여 삭제하는 경우 case가 아닌 활동만 삭제됩니다.

## <a name="see-also"></a>참고자료

- [제어 흐름](../workflow-designer/control-flow-activity-designers.md)
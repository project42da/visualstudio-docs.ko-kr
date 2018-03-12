---
title: "ClearCollection&lt;T&gt; 활동 디자이너 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.ClearCollection`1.UI
ms.assetid: db0e5da2-7b5a-4f1a-864c-f3aeeeeb51a7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6f4a89d062fe8adeb06c05ba25929bce6d466511
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="clearcollectionlttgt-activity-designer"></a>ClearCollection&lt;T&gt; 활동 디자이너
**ClearCollection\<T >** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.ClearCollection%601> 활동입니다.

## <a name="the-clearcollectiont-activity"></a>ClearCollection < T\> 활동
 <xref:System.Activities.Statements.ClearCollection%601> 활동은 모든 항목의 지정한 컬렉션을 지웁니다.

### <a name="using-the-clearcollectiont-activity-designer"></a>ClearCollection를 사용 하 여\<T > 활동 디자이너
 **ClearCollection\<T >** 활동 디자이너에서 확인할 수 있습니다는 **컬렉션** 의 범주는 **도구 상자**는 를클릭하여액세스 **도구 상자** 탭은 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **ClearCollection\<T >** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로, 등 배치는 <xref:System.Activities.Statements.Sequence>. 그렇기 때문에 <xref:System.Activities.Statements.ClearCollection%601> 기본값 활동 <xref:System.Activities.Activity.DisplayName%2A> ClearCollection의 < i n t 32\>합니다. (기본적으로는 *TypeArgument* 은 **Int32**합니다. 속성 표에서 이를 변경할 수 있습니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 편집할 수 있습니다는 **ClearCollection < T\>**  활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다. 다른 속성은 속성 표에서 편집해야 합니다.

### <a name="the-clearcollectiont-properties"></a>ClearCollection < T\> 속성
 다음 표에서는 <xref:System.Activities.Statements.ClearCollection%601> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.ClearCollection%601> 활동의 선택적 이름을 지정합니다. 기본값은 ClearCollection < i n t 32\>합니다. <xref:System.Activities.Activity.DisplayName%2A> 값은 꼭 필요하지 않더라도 사용하는 것이 좋습니다.|
|<xref:System.Activities.Statements.ClearCollection%601.Collection%2A>|True|선언할 항목 컬렉션을 지정합니다. 이 컬렉션은 형식의 **ICollection\<TypeArgument > 합니다.** 컬렉션을 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|
|*TypeArgument*|True|<xref:System.Collections.Generic.ICollection%601>에 포함된 T 형식의 항목을 지정합니다. 기본적으로이 *TypeArgument* 유형이으로 설정 되어 **Int32**합니다. 값을 변경의 종류를 변경 하려면는 *TypeArgument* 속성 표의 콤보 상자에 있습니다.|

## <a name="see-also"></a>참고 항목

- [컬렉션](../workflow-designer/collection-activity-designers.md)
- [AddToCollection\<T>](../workflow-designer/addtocollection-t-activity-designer.md)
- [ExistsInCollection\<T>](../workflow-designer/existsincollection-t-activity-designer.md)
- [RemoveFromCollection\<T>](../workflow-designer/removefromcollection-t-activity-designer.md)
---
title: 워크플로 디자이너-Throw 활동 디자이너
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02bb94ad17b78b1264129b8a5ba00a964edbd2f2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="throw-activity-designer"></a>Throw 활동 디자이너

**Throw** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.Throw> 활동입니다.

## <a name="the-throw-activity"></a>Throw 활동
 <xref:System.Activities.Statements.Throw> 활동은 예외를 throw합니다.

### <a name="using-the-throw-activity-designer"></a>Throw 활동 디자이너 사용
 **Throw** 활동 디자이너에서 확인할 수 있습니다는 **의 오류 처리** 의 범주는 **도구 상자**, 클릭 하 여 액세스는 **도구 상자**워크플로 디자이너의 왼쪽에 탭 (또는 선택 **도구 모음** 에서 **보기** 메뉴나 CTRL + ALT + X.)

 **Throw** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 활동은 일반적으로, 등 배치 때마다 워크플로 디자이너 화면에 끌어 놓 및는 <xref:System.Activities.Statements.Sequence>합니다. 그렇기 때문에 <xref:System.Activities.Statements.Throw> 기본값 활동 **DisplayName** 의 Throw 합니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 편집할 수 있습니다는 **Throw** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다. <xref:System.Activities.Statements.Throw.Exception%2A> 속성은 속성 표에서 편집해야 합니다.

### <a name="the-throw-properties"></a>Throw 속성
 다음 표에서는 <xref:System.Activities.Statements.Throw> 속성을 보여 주고 디자이너에서 이 속성을 사용하는 방법을 설명합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Throw> 활동의 선택적 이름을 지정합니다. 기본값은 Throw입니다.|
|<xref:System.Activities.Statements.Throw.Exception%2A>|True|throw할 예외입니다. 이 예외는 <xref:System.Exception>에서 파생되어야 합니다. 이 예외를 지정하려면 속성 표에 Visual Basic 식을 입력합니다.|

## <a name="see-also"></a>참고자료

- [컬렉션](../workflow-designer/collection-activity-designers.md)
- [rethrow](../workflow-designer/rethrow-activity-designer.md)
- [Throw 활동 디자이너](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)
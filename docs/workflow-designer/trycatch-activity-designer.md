---
title: "TryCatch 활동 디자이너 | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.TryCatch.UI
- System.Activities.Statements.Catch`1.UI
ms.assetid: 02a326c2-4009-442f-b7cb-e42121fd2992
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3dc20be3f2d8b2e6281d44139bbd97d9dd67593d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="trycatch-activity-designer"></a>TryCatch 활동 디자이너
**TryCatch** 활동 디자이너는 만들고 구성 하는 데 사용 되는 <xref:System.Activities.Statements.TryCatch> 활동입니다.

## <a name="the-trycatch-activity"></a>TryCatch 활동
 <xref:System.Activities.Statements.TryCatch> 활동에 포함 한 <xref:System.Activities.Statements.TryCatch.Try%2A> 활동, 컬렉션을 **Catch\<TException >** 및 <xref:System.Activities.Statements.TryCatch.Finally%2A> 활동입니다. A <xref:System.Activities.Statements.Catch%601> 형식의 **TException** 포함 한 <xref:System.Activities.Statements.Catch%601.ExceptionType%2A> 및 <xref:System.Activities.Statements.Catch%601.Action%2A>합니다. 둘 다 일반적인 예외 기반의 오류 처리 메커니즘을 구현하는 데 사용됩니다. <xref:System.Activities.Statements.TryCatch> 활동은 <xref:System.Activities.Statements.TryCatch.Try%2A> 활동을 실행하려고 합니다. 경우는 <xref:System.Activities.Statements.TryCatch.Try%2A> 활동이 예외를 throw 된 <xref:System.Activities.Statements.TryCatch> 활동을 사용 해당 **Catch < TException\>**  예외에 맞도록 컬렉션입니다. 일치 하는 경우 다음의 <xref:System.Activities.Statements.Catch%601.Action%2A> 해당 **Catch\<TException >** 오류 처리는 예외에 대 한 논리로 실행 됩니다. <xref:System.Activities.Statements.TryCatch.Try%2A> 섹션의 활동이 성공적으로 완료되었거나 <xref:System.Activities.Statements.TryCatch.Catches%2A>의 활동이 성공적으로 완료된 경우 <xref:System.Activities.Statements.TryCatch> 활동은 해당 <xref:System.Activities.Statements.TryCatch.Finally%2A> 활동을 실행합니다. 자세한 내용은 참조 [Windows 워크플로 예외](/dotnet/framework/windows-workflow-foundation/exceptions)합니다.

### <a name="using-the-trycatch-activity-designer"></a>TryCatch 활동 디자이너 사용
 **TryCatch** 활동 디자이너에서 확인할 수 있습니다는 **의 오류 처리** 의 범주는 **도구 상자**를 클릭 하 여 액세스는 **도구상자** 탭의 왼쪽에는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (또는 선택 **도구 모음** 에서 **보기** 메뉴 또는 보조키 + ALT + X.)

 **TryCatch** 에서 활동 디자이너를 끌 수 있습니다는 **도구 상자** 끌어다는 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] 화면의 아무 곳에 나 활동은 일반적으로, 등 배치는 <xref:System.Activities.Statements.Sequence>합니다. 이렇게 하면 기본 <xref:System.Activities.Statements.TryCatch>인 TryCatch라는 이름의 <xref:System.Activities.Activity.DisplayName%2A> 활동이 만들어집니다. <xref:System.Activities.Activity.DisplayName%2A> 헤더의 값을 편집할 수 있습니다는 **TryCatch** 활동 디자이너 또는 **DisplayName** 속성 표의 상자입니다. 다른 속성의 화면에서 편집 해야 합니다는 **TryCatch** 활동 디자이너입니다.

 오른쪽 위 모서리에 있는 확장 단추의 클릭 **TryCatch** 보려면 디자이너는 **시도**, **Catch**, 및 **마지막** 상자에 확장 된 보기입니다. Catch를 추가 하려면 클릭는 **새 캐치 추가** 단추 **TryCatch** 디자이너입니다. 단추가 형식 콤보 상자로 바뀝니다. 예외 형식을 선택하고 <ENTER> 키를 눌러 Catch를 추가합니다. 추가한 후 한 **Catch**, 하면 catch 영역이 확장 되 고 catch catch에 대 한 실행 논리를 정의로 작업을 삭제할 수 있습니다. 확장된 Catch 영역 오른쪽에는 텍스트 상자가 있습니다. 이 텍스트 상자를 사용하여 예외 변수의 이름을 지정할 수 있습니다. 동일한 작업에 대 한 예외 변수 에서만 사용할 수 있습니다 **Catch**합니다.

 **TryCatch** 디자이너 편집을 지원 하지 않습니다 **Catch**합니다. 삭제 해야 하는 예외 형식을 변경 하려는 경우는 **Catch** 새 계정을 추가 합니다. A **Catch** 선택 하 고 삭제 하거나 사용 하 여 삭제할 수는 **삭제** 마우스 오른쪽 단추로 클릭 하면 상황에 맞는 메뉴에 메뉴.

### <a name="the-trycatch-properties"></a>TryCatch 속성
 다음 표는 <xref:System.Activities.Statements.TryCatch>속성 디자이너에서 사용 되는 방법을 설명 합니다.

|속성 이름|필수|용도|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TryCatch> 활동의 선택적 이름을 지정합니다. 기본 TryCatch입니다.|
|<xref:System.Activities.Statements.TryCatch.Try%2A>|False|<xref:System.Activities.Statements.TryCatch>를 실행할 때 먼저 실행된 활동입니다.|
|<xref:System.Activities.Statements.TryCatch.Catches%2A>|False|컬렉션 **Catch** 때 확인 해야 할 요소는 <xref:System.Activities.Statements.TryCatch.Try%2A> 작업 예외를 throw 합니다.<br /><br /> <xref:System.Activities.Statements.TryCatch.Catches%2A>에 하나 이상의 활동을 추가하거나 <xref:System.Activities.Statements.TryCatch.Finally%2A> 블록에 활동을 추가해야 합니다.|
|<xref:System.Activities.Statements.TryCatch.Finally%2A>|False|<xref:System.Activities.Statements.TryCatch.Try%2A> 및 <xref:System.Activities.Statements.TryCatch.Catches%2A> 컬렉션의 필요한 모든 활동이 실행 완료될 때 실행할 활동입니다.<br /><br /> <xref:System.Activities.Statements.TryCatch.Catches%2A>에 하나 이상의 활동을 추가하거나 <xref:System.Activities.Statements.TryCatch.Finally%2A> 블록에 활동을 추가해야 합니다.|

## <a name="see-also"></a>참고 항목

- [컬렉션](../workflow-designer/collection-activity-designers.md)
- [rethrow](../workflow-designer/rethrow-activity-designer.md)
- [Throw](../workflow-designer/throw-activity-designer.md)
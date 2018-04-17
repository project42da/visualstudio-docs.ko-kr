---
title: 활동에 바인딩하려면&#39;s 속성 대화 상자 (레거시) | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Workflow.ComponentModel.Design.ActivityBindForm.UI
helpviewer_keywords:
- Bind to an Activity's Property dialog box
ms.assetid: 19ebb207-e0a9-4642-8f5f-a5e31395c683
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a799b57169116343f5d83e54ce5bd87dedfd801
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="bind-to-an-activity39s-property-dialog-box-legacy"></a>활동에 바인딩하려면&#39;s 속성 대화 상자 (레거시)
이 항목에서는 설명 방법을 사용 하 여는 **활동의 속성에 바인딩할** 레거시 Windows 워크플로 디자이너의 대화 상자. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.

 종속성 속성인 인스턴스 형식을 다른 활동의 public 속성이나 이벤트에 바인딩할 수 있습니다. 활동 바인딩에 대 한 자세한 내용은 참조 [종속성 속성을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65007)합니다.

 사용 하 여 바인딩할 속성을 선택 하면는 **활동의 속성에 바인딩할** 대화 상자. 줄임표를 클릭 하 여이 대화 상자를 열면 **[...]**  끝에서 선택한 속성의 텍스트 상자에는 **속성** 창 또는 속성 브라우저에서 속성 이름 옆에 나타나는 파란색 느낌표 아이콘을 클릭 하 여 합니다.

 다음 표에 사용자 인터페이스 (UI) 요소는 **활동의 속성에 바인딩할** 대화 상자.

|UI 요소|설명|
|----------------|-----------------|
|**기존 멤버에 바인딩**|트리 뷰 창에서 바인딩할 멤버를 선택합니다. 트리 뷰 아래의 창에서는 멤버가 바인딩하기에 올바른 형식인지 여부를 나타내는 메시지가 표시됩니다. 클릭 **확인** 선택 된 올바른 멤버에 바인딩할 합니다.|
|**새 멤버에 바인딩**|바인딩할 새 멤버 필드나 속성을 만듭니다. 입력 한 **새 멤버 이름은**합니다. 종속성 속성을 만들거나 선택 하 여 public 필드를 선택 **필드 만들기** 또는 **속성 만들기**합니다. 클릭 **확인** 새 멤버를 만들 합니다.|

## <a name="see-also"></a>참고자료

- [활동 속성을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65013)
- [종속성 속성을 사용 하 여](http://go.microsoft.com/fwlink?LinkID=65007)
- [Windows Workflow Foundation용 레거시 디자이너 UI 도움말](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)
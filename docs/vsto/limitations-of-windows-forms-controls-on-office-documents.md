---
title: Office 문서의 Windows Forms 컨트롤의 제한 사항
ms.date: 02/02/2017
ms.technology: office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], ActiveX legacy
- ActiveX controls [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], limitations
- controls [Office development in Visual Studio], Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], unsupported properties and methods
- Toolbox [Office development in Visual Studio], unsupported controls
- user controls [Office development in Visual Studio], grouping controls
- Windows Forms controls [Office development in Visual Studio], Toolbox
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 104b8b3449b2ffb689caf66d5c180817b633f83e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572961"
---
# <a name="limitations-of-windows-forms-controls-on-office-documents"></a>Office 문서의 Windows Forms 컨트롤의 제한 사항

Microsoft Office Word 문서 또는 Microsoft Office Excel 워크시트에 추가 된 Windows Forms 컨트롤 및 Windows Forms에 추가 하는 Windows Forms 컨트롤 간의 차이가 있습니다. 추가한 경우에 예를 들어 한 <xref:Microsoft.Office.Tools.Word.Controls.Button> 등의 속성을 문서에 컨트롤 <xref:System.Windows.Forms.Control.Dock>, <xref:System.Windows.Forms.Control.Anchor>, 및 <xref:System.Windows.Forms.Control.TabIndex> 예상 대로 작동 하지 않습니다.

이러한 차이점 대부분의 일반적인 원인은 방식으로 컨트롤을 호스팅하는 Windows Forms 문서에서 합니다. Windows Forms 컨트롤을 문서에 추가 되 고 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 다음 문서에 Windows Forms 컨트롤을 호스트 하는 ActiveX 컨트롤을 포함 합니다. Windows Forms 컨트롤의 문서에 직접 포함 되지 않습니다.

[!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]

## <a name="limitations-of-methods-and-properties-of-windows-forms-controls"></a>Windows Forms 컨트롤의 메서드 및 속성의 제한 사항

다양 한 방법 및 Windows Form에서 있으며, 따라서 것이 좋습니다은 사용 하지 않도록 하는 대로 문서에 동일한 방식으로 작동 하지 않는 Windows Forms 컨트롤의 속성이 있습니다. 예를 들어 같은 속성을 설정 <xref:System.Windows.Forms.Control.Dock> 및 <xref:System.Windows.Forms.Control.Anchor> 문서 보다는 컨테이너 ActiveX 컨트롤을 기준으로 컨트롤의 위치에만 영향을 줍니다. 다음은 Word 및 Excel에 대 한 Windows Forms 컨트롤의 지원 되지 않는 메서드 및 속성의 목록입니다.

- Excel 컨트롤의 지원 되지 않는 속성:

    - <xref:System.Windows.Forms.Control.Anchor>
    - <xref:System.Windows.Forms.Control.Dock>
    - <xref:System.Windows.Forms.Control.Location>
    - <xref:System.Windows.Forms.Control.TabIndex>
    - <xref:System.Windows.Forms.Control.TabStop>
    - <xref:System.Windows.Forms.Control.TopLevelControl>

- 지원 되지 않는 메서드 및 Word 컨트롤의 속성:

    - <xref:System.Windows.Forms.Control.Hide%2A>
    - <xref:System.Windows.Forms.Control.Show%2A>
    - <xref:System.Windows.Forms.Control.Anchor>
    - <xref:System.Windows.Forms.Control.Dock>
    - <xref:System.Windows.Forms.Control.Location>
    - <xref:System.Windows.Forms.Control.TabIndex>
    - <xref:System.Windows.Forms.Control.TabStop>
    - <xref:System.Windows.Forms.Control.TopLevelControl>
    - <xref:System.Windows.Forms.Control.Visible>

도 설정할 수 없습니다는 <xref:System.Windows.Forms.Control.Left> 또는 <xref:System.Windows.Forms.Control.Top> Word 문서에서 텍스트 줄에 있는 Windows Forms 컨트롤의 속성입니다. Windows Forms 컨트롤은 다음과 같은 경우에는 텍스트에 맞춰 추가 됩니다.

- 프로그래밍 방식으로 Word 문서에 컨트롤을 추가 하 고 위치에 대 한 범위를 지정 하는 메서드를 사용 합니다.

- 디자인 타임에 Word 문서에 Windows Forms 컨트롤을 추가 합니다. 디자이너의 컨트롤을 수정 하 여이 변경할 수 있습니다.

## <a name="differences-in-windows-forms-controls-on-office-documents"></a>Office 문서의 Windows Forms 컨트롤의 차이점

Windows Forms 컨트롤 일반적으로 동일 하 게 동작 Office 문서에 Windows Form에서 하지만 몇 가지 차이점이 분명히 존재 합니다. 다음 표에서 Office 문서의 Windows Forms 컨트롤에 대 한 존재 하는 차이점을 설명 합니다.

|기능|차이|
|-------------------|----------------|
|컨트롤 탭 순서|Excel 워크시트 또는 Word 문서에 배치 된 컨트롤을 이동할 수 없습니다.|
|컨트롤 그룹화|사용할 수 없습니다는 <xref:System.Windows.Forms.GroupBox> 을 Office 문서에 있는 다른 컨트롤을 포함 하도록 합니다. 문서에 직접 여러 라디오 단추를 추가 하면 라디오 단추는 동시 되지 않습니다. 라디오 단추를 함께 사용할 수 없습니다; 하도록 코드를 작성할 수 있습니다. 그러나 사용자 정의 컨트롤의 라디오 단추를 추가 하 고 다음 문서에 사용자 정의 컨트롤을 추가 하는 기본 방법이입니다. 자세한 내용은 참조는 Word 컨트롤 샘플 또는 Excel 컨트롤 샘플 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)합니다.|
|컨트롤 종류|문서에서 사용 되는 Windows Forms 컨트롤에서 제공 하는 클래스에 래핑됩니다.이 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 에 제공 하는 컨트롤 관련 된 추가 기능 Excel 워크시트 또는 Word 문서. 예를 들어 한 **단추** Excel 워크시트에서 컨트롤을 유형으로 지정 해야 합니다. <xref:Microsoft.Office.Tools.Excel.Controls.Button> 대신 <xref:System.Windows.Forms.Button> 참조 하거나 개체를 캐스팅할 때.|
|컨트롤 위치 및 크기|크기와 컨트롤의 위치는 ActiveX 컨트롤 컨테이너의 일부인 속성에 의해 결정 됩니다. ActiveX 컨트롤 속성에는 Windows Forms 컨트롤의 해당 속성 값은 다른 수행 합니다. 설정 하는 경우는 `Top`, `Left`, `Height`, 또는 `Width` 에서 측정 되는 컨트롤의 속성을 픽셀 아닌 포인트입니다.|
|Word 문서에서 컨트롤 위치|흐름 기반 레이아웃 컨트롤을 추가 하는 경우 컨트롤은 콘텐츠가 변경 내용을 사용 하 여 흐릅니다 염두에 둬야 합니다. 으로 끌어 옵니다 컨트롤을 단락에 고정할 수 없습니다는 **도구 상자** 컨트롤은 Word 문서에서 텍스트 줄에 추가 되기 때문에 있습니다. 다른 메서드를 사용 하 여 컨트롤을 두 번 클릭 하면 같은 컨트롤을 추가 하려면 컨트롤 그림 삽입을 위해 설정 하는 Word 옵션에 따라 삽입 됩니다.<br /><br /> 설정할 수 없습니다.는 `Left` 또는 `Top` 텍스트와 같은 줄에 있는 컨트롤의 속성입니다.<br /><br /> 머리글 또는 바닥글에서 나 하위 문서에 컨트롤을 배치할 수 없습니다.|
|컨트롤 이벤트|컨트롤을 선택 하면 다음과 같은 순서로 이벤트가 발생 합니다.<br /><br /> 1.  `Enter`<br />2.  `GotFocus`<br /><br /> 컨트롤을 선택 취소 하면 다음과 같은 순서로 이벤트가 발생 합니다.<br /><br /> 1.  `Leave`<br />2.  `Validating`<br />3.  `Validated`<br />4.  `LostFocus`|
|컨트롤 크기 조정|문서의 확대/축소 설정을 100% 이외의 값으로 변경 하면 컨트롤을 해제 상태로 표시 되어도 문서와 크기를 조정 합니다. 예를 들어 문서를 130% 확대/축소에 단추를 클릭할 경우 메시지가 표시 됩니다 확대/축소를 100%로 설정 될 때까지 컨트롤이 비활성화 되었습니다. 100%로 확대/축소를 변경 하는 경우는 컨트롤이 올바르게 작동 합니다.|
|컨트롤 속성 값|Windows Form의 컨트롤 속성은 정수 값으로 설정 되어, Word 문서에 컨트롤에 대 한 single로 설정 됩니다. Excel에서 컨트롤의 속성 값이 double로 설정 됩니다. 경우는 `Height` 및 `Width` 워크시트 또는 화면 크기를 초과 하는 워크시트에 컨트롤의 속성, 값이 잘립니다.|
|컨트롤 크기 조정|8 개의 크기 조정 핸들 중 하나를 사용 하 여 문서에서 컨트롤의 크기를 조정 하면 새 컨트롤 차원에 반영 되지 않습니다는 **속성** 컨트롤 다시 선택 될 때까지 창.|
|동작을 제어|Excel 워크시트에서 컨트롤은 워크시트 창 분할 될 때 예기치 않게 동작할 수 있습니다. 예를 들어에 대 한 액세스는 <xref:Microsoft.Office.Tools.Excel.Controls.TextBox> 워크시트에만 사용할 수 창 중 하나에 있습니다.|
|컨트롤 이름 지정|컨트롤의 이름에 예약어를 사용할 수 없습니다. 예를 들어, 추가 하는 경우는 <xref:Microsoft.Office.Tools.Excel.Controls.Button> 워크시트에는 하 고 이름을 **시스템**, 프로젝트를 빌드할 때 오류가 발생 합니다.|
|프로그래밍 방식으로 컨트롤 추가|런타임에 문서에 컨트롤을 추가 하는 컨트롤의 생성자를 사용 하지 마십시오. 제공 하는 도우미 메서드를 사용 하 여 대신는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다. 예를 들어, 사용 된 <xref:Microsoft.Office.Tools.Excel.ControlExtensions.AddButton%2A> 워크시트에 단추를 추가 하는 메서드. 이러한 도우미 메서드에서 지원 되지 않는 컨트롤을 추가 하려는 경우 사용할 수 있습니다는 `AddControl` 메서드. 자세한 내용은 참조 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.|
|컨트롤 복사|Windows Forms 컨트롤을 복사 하 고 런타임에 문서에 붙여 경우 빈 컨테이너 ActiveX 컨트롤이 문서에 붙여넣습니다. Windows Forms 컨트롤의 새 위치에 나타나지 않으며 원래 컨트롤 뒤에 있는 코드 ActiveX 컨트롤 컨테이너에 복사 되지 않습니다.|

## <a name="limitations-in-document-level-projects"></a>문서 수준 프로젝트에 대 한 제한 사항

몇 가지 제한이 문서에 Windows Forms 컨트롤을 사용 하는 문서 수준 프로젝트에 고유 합니다.

### <a name="control-support-at-design-time"></a>디자인 타임에 컨트롤을 지 원하

특정 Windows Forms 컨트롤에서 제거 되 고 **도구 상자** Excel 워크시트 또는 Word 문서는 Visual Studio 디자이너에에서 열려 있는 경우. 이것은 기술적 제한 사항을 위반 때문에 게 없거나 기능은 이미 Word 또는 Excel 내에서 사용할 수 있습니다. Excel 및 Word 프로젝트를 지 원하는 모든 Windows Forms 컨트롤 및 기타 구성 요소에 표시 되는 **도구 상자** 문서에 포커스가 시점과 워크시트 또는 문서에 타사 컨트롤을 추가할 수도 있습니다.

> [!NOTE]
> 모든 컨트롤에서 제거 되는 **도구 상자** 문서가 보호 되는 경우. 문서 보호에 대 한 정보를 참조 하십시오. [문서 보호 문서 수준 솔루션의](../vsto/document-protection-in-document-level-solutions.md)합니다.

> [!NOTE]
> 타사 컨트롤 있어야는 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성이로 설정 **true** Office 솔루션에 사용할 수 있도록 합니다.

다음 컨트롤 및 구성 요소에서 사용할 수 없는 **도구 상자**:

- <xref:System.Windows.Forms.BindingNavigator>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.DataGrid>

- <xref:System.DirectoryServices.DirectoryEntry>

- <xref:System.DirectoryServices.DirectorySearcher>

- <xref:System.Windows.Forms.ErrorProvider>

- <xref:System.Diagnostics.EventLog>

- <xref:System.IO.FileSystemWatcher>

- <xref:System.Windows.Forms.FlowLayoutPanel>

- <xref:System.Windows.Forms.GroupBox>

- <xref:System.Windows.Forms.MainMenu>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Messaging.MessageQueue>

- <xref:System.Windows.Forms.NotifyIcon>

- <xref:System.Windows.Forms.PageSetupDialog>

- <xref:System.Windows.Forms.Panel>

- <xref:System.Diagnostics.PerformanceCounter>

- <xref:System.Windows.Forms.PrintDialog>

- <xref:System.Drawing.Printing.PrintDocument>

- <xref:System.Windows.Forms.PrintPreviewControl>

- <xref:System.Diagnostics.Process>

- <xref:System.Windows.Forms.RichTextBox>

- <xref:System.IO.Ports.SerialPort>

- <xref:System.ServiceProcess.ServiceController>

- <xref:System.Windows.Forms.SplitContainer>

- <xref:System.Windows.Forms.Splitter>

- <xref:System.Windows.Forms.StatusBar>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.TabControl>

- <xref:System.Windows.Forms.TableLayoutPanel>

- <xref:System.Timers.Timer>

- <xref:System.Windows.Forms.Timer>

- <xref:System.Windows.Forms.ToolBar>

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.ToolStripContainer>

- <xref:System.Windows.Forms.ToolStripDropDown>

- <xref:System.Windows.Forms.ToolStripDropDownMenu>

- <xref:System.Windows.Forms.ToolStripPanel>

### <a name="support-for-legacy-activex-controls"></a>레거시 ActiveX 컨트롤에 대 한 지원

ActiveX 컨트롤의 기능 손실;가 기존 Word 문서 또는 ActiveX 컨트롤이 포함 된 Excel 통합 문서를 사용 하는 문서 수준 Office 프로젝트를 만드는 경우 그러나 Visual Studio 내에서 문서에 새 ActiveX 컨트롤을 추가 하기 위한 지원은 없습니다. 예를 들어 Word 문서에서 단추는 **제어** VBA 매크로 Visual Basic을 실행 하는 도구 상자, 문서 Office 프로젝트에서 사용 된 후에 매크로 실행 하려면 계속 됩니다. 그러나, ActiveX 컨트롤 및 VBA 매크로 제거 하 고 Windows Forms 컨트롤 바꿉니다 하는 관리 코드 것이 좋습니다.

## <a name="see-also"></a>참고자료

- [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)
- [Office 문서 개요에서 Windows Forms 컨트롤](../vsto/windows-forms-controls-on-office-documents-overview.md)
- [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)
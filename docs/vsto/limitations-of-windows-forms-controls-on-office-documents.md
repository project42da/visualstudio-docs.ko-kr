---
title: "Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "ActiveX 컨트롤[Visual Studio에서 Office 개발]"
  - "컨트롤[Visual Studio에서 Office 개발], Windows Forms 컨트롤"
  - "Office 문서[Visual Studio에서 Office 개발], Windows Forms 컨트롤"
  - "도구 상자[Visual Studio에서 Office 개발], 지원되지 않는 컨트롤"
  - "사용자 컨트롤[Visual Studio에서 Office 개발], 컨트롤 그룹화"
  - "Windows Forms 컨트롤[Visual Studio에서 Office 개발], ActiveX 레거시"
  - "Windows Forms 컨트롤[Visual Studio에서 Office 개발], 제한 사항"
  - "Windows Forms 컨트롤[Visual Studio에서 Office 개발], 도구 상자"
  - "Windows Forms 컨트롤[Visual Studio에서 Office 개발], 지원되지 않는 속성 및 메서드"
ms.assetid: 95ff473e-4952-4977-bc88-c77289c9fb0b
caps.latest.revision: 56
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 52
---
# Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항
  Microsoft Office Word 문서나 Microsoft Office Excel 워크시트에 추가되는 Windows Forms 컨트롤과 Windows Forms에 추가되는 Windows Forms 컨트롤 사이에는 몇 가지 차이가 있습니다.  예를 들어 문서에 <xref:Microsoft.Office.Tools.Word.Controls.Button> 컨트롤을 추가하는 경우 <xref:Microsoft.Office.Tools.Word.Controls.Button.Dock%2A>, <xref:Microsoft.Office.Tools.Word.Controls.Button.Anchor%2A> 및 <xref:Microsoft.Office.Tools.Word.Controls.Button.TabIndex%2A> 같은 속성이 의도한 대로 작동하지 않습니다.  
  
 이러한 차이점이 있는 이유는 Windows Forms 컨트롤이 문서에서 호스팅되는 방식 때문입니다.  문서에 Windows Forms 컨트롤을 추가하면 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 Windows Forms 컨트롤을 호스팅하는 ActiveX 컨트롤을 문서에 포함합니다.  Windows Forms 컨트롤이 문서에 직접 포함되지는 않습니다.  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## Windows Forms 컨트롤의 메서드와 속성에 대한 제한 사항  
 Windows Forms 컨트롤의 몇 가지 메서드와 속성은 문서에서 사용할 때와 Windows Form에서 사용할 때의 동작이 다르므로 이러한 메서드나 속성은 사용하지 않는 것이 좋습니다.  예를 들어 `Dock` 및 `Anchor` 같은 속성을 설정하면 문서가 아니라 컨테이너 ActiveX 컨트롤에 대한 Windows Forms 컨트롤의 위치만 영향을 받습니다.  다음은 Word와 Excel에서 Windows Forms 컨트롤의 지원되지 않는 메서드와 속성의 목록입니다.  
  
-   지원되지 않는 Excel 컨트롤 메서드 및 속성  
  
    -   `Anchor`  
  
    -   `Dock`  
  
    -   `Location`  
  
    -   `TabIndex`  
  
    -   `TabStop`  
  
    -   `TopLevelControl`  
  
-   지원되지 않는 Word 컨트롤 메서드 및 속성  
  
    -   `Hide`  
  
    -   `Show`  
  
    -   `Anchor`  
  
    -   `Dock`  
  
    -   `Location`  
  
    -   `TabIndex`  
  
    -   `TabStop`  
  
    -   `TopLevelControl`  
  
    -   `Visible`  
  
 또한 Word 문서에서 텍스트 줄 안에 있는 Windows Forms 컨트롤의 `Left` 또는 `Top` 속성을 설정할 수 없습니다.  Windows Forms 컨트롤은 다음과 같은 경우에 텍스트 줄 안에 추가됩니다.  
  
-   프로그래밍 방식으로 Word 문서에 컨트롤을 추가하고 해당 위치에 대한 범위를 지정하는 메서드를 사용할 경우.  
  
-   디자인 타임에 Word 문서에 Windows Forms 컨트롤을 추가할 경우.  디자이너에서 컨트롤을 수정하여 이를 변경할 수 있습니다.  
  
## Office 문서에서 Windows Forms 컨트롤의 차이점  
 Office 문서에 배치되는 Windows Forms 컨트롤은 일반적으로 Windows Form에서와 동일하게 작동하지만 몇 가지 차이는 있습니다.  다음 표에서는 Office 문서에 배치된 Windows Forms 컨트롤에 해당하는 차이점을 설명합니다.  
  
|기능|차이점|  
|--------|---------|  
|컨트롤 탭 순서|Excel 워크시트나 Word 문서에 배치된 컨트롤 간에 Tab 키를 사용하여 이동할 수 없습니다.|  
|컨트롤 그룹화|<xref:System.Windows.Forms.GroupBox> 컨트롤을 사용하여 Office 문서의 다른 컨트롤을 포함할 수 없습니다.  문서에 여러 개의 라디오 단추를 직접 추가하면 라디오 단추를 한 번에 하나만 선택할 수 없습니다.  라디오 단추를 한 번에 하나만 선택할 수 있도록 코드를 작성할 수 있지만 기본 방법은 라디오 단추를 사용자 정의 컨트롤에 추가한 다음 사용자 정의 컨트롤을 문서에 추가하는 것입니다.  자세한 내용은 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)에서 Word Controls 샘플 또는 Excel Controls 샘플을 참조하십시오.|  
|컨트롤 형식|문서에 사용되는 Windows Forms 컨트롤은 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 제공하는 클래스에 래핑됩니다. 이 클래스에서는 Excel 워크시트나 Word 문서에 고유하게 사용되는 추가 기능을 컨트롤에 부여합니다.  예를 들어, Excel 워크시트에 `Button` 컨트롤이 있으면 개체를 참조하거나 캐스팅할 때 <xref:System.Windows.Forms.Button>이 아니라 <xref:Microsoft.Office.Tools.Excel.Controls.Button>으로 형식을 지정해야 합니다.|  
|컨트롤 위치 및 크기|컨트롤의 크기와 위치는 컨테이너 ActiveX 컨트롤의 일부인 속성을 통해 결정됩니다.  ActiveX 컨트롤 속성에 사용되는 값은 상응하는 Windows Forms 컨트롤의 속성에 사용되는 값과 다릅니다.  컨트롤의 `Top`, `Left`, `Height` 또는 `Width` 속성을 설정하면 해당 값은 픽셀 단위가 아닌 포인트 단위로 측정됩니다.|  
|Word 문서에서의 컨트롤 위치|선형 기반 레이아웃에 컨트롤을 추가하는 경우에는 콘텐츠가 변경되면 컨트롤이 콘텐츠와 함께 이동한다는 점을 염두에 두어야 합니다.  **도구 상자**에서 컨트롤을 끌어 놓으면 컨트롤이 Word 문서에서 텍스트와 같은 줄에 추가되므로 컨트롤을 단락에 고정할 수 없습니다.  컨트롤을 두 번 클릭하는 경우와 같이 다른 방법을 사용하여 컨트롤을 추가하는 경우 컨트롤은 그림 삽입을 위해 설정한 Word 옵션에 따라 삽입됩니다.<br /><br /> 텍스트와 같은 줄에 있는 컨트롤의 `Left` 및 `Top` 속성은 설정할 수 없습니다.<br /><br /> 머리글\/바닥글이나 하위 문서에는 컨트롤을 추가할 수 없습니다.|  
|컨트롤 이벤트|컨트롤을 선택하면 다음과 같은 순서로 이벤트가 발생합니다.<br /><br /> 1.  `Enter`<br />2.  `GotFocus`<br /><br /> 컨트롤의 선택을 취소하면 다음과 같은 순서로 이벤트가 발생합니다.<br /><br /> 1.  `Leave`<br />2.  `Validating`<br />3.  `Validated`<br />4.  `LostFocus`|  
|컨트롤 크기 조정|문서의 확대\/축소 설정을 100%가 아닌 다른 값으로 변경하면 컨트롤이 문서와 함께 크기 조정된 상태로 표시되어도 이를 사용할 수 없습니다.  예를 들어, 문서를 130%로 확대한 상태에서 단추를 클릭하면 컨트롤이 비활성화되어 있으며 이를 사용하려면 확대\/축소를 100%로 설정해야 한다는 메시지가 나타납니다.  확대\/축소를 100%로 변경하면 컨트롤이 올바르게 작동합니다.|  
|컨트롤 속성 값|Windows Form에서는 컨트롤의 속성이 정수 값으로 설정되지만 Word 문서의 컨트롤에 대해서는 single로 설정됩니다.  Excel의 경우 컨트롤의 속성 값은 double로 설정됩니다.  워크시트에서 컨트롤의 `Height` 및 `Width` 속성이 워크시트나 화면의 크기를 초과하면 해당 값이 잘립니다.|  
|컨트롤 크기 조정|여덟 개의 크기 조정 핸들 중 하나를 사용하여 문서에서 컨트롤 크기를 조정해도 **속성** 창에 새 컨트롤 치수가 반영되지 않습니다. 이를 적용하려면 컨트롤을 다시 선택해야 합니다.|  
|컨트롤 동작|Excel 워크시트의 컨트롤은 워크시트 창을 분할하는 경우 예기치 않게 동작할 수 있습니다.  예를 들어, 워크시트의 <xref:Microsoft.Office.Tools.Excel.Controls.TextBox>에는 창 하나에서만 액세스할 수 있습니다.|  
|컨트롤 이름 지정|예약어는 컨트롤의 이름에 사용할 수 없습니다.  예를 들어, <xref:Microsoft.Office.Tools.Excel.Controls.Button>을 워크시트에 추가하고 이름을 **System**으로 변경하면 프로젝트를 빌드할 때 오류가 발생합니다.|  
|프로그래밍 방식으로 컨트롤 추가|런타임에 컨트롤의 생성자를 사용하여 문서에 컨트롤을 추가하면 안 됩니다.  대신 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 제공하는 도우미 메서드를 사용해야 합니다.  예를 들어, 워크시트에 단추를 추가하려면 <xref:Microsoft.Office.Tools.Excel.ControlExtensions.AddButton%2A> 메서드를 사용합니다.  이러한 도우미 메서드가 지원하지 않는 컨트롤을 추가하려면 AddControl 메서드를 사용합니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)을 참조하십시오.|  
|컨트롤 복사|런타임에 Windows Forms 컨트롤을 복사하여 문서에 붙여넣으면 빈 컨테이너 ActiveX 컨트롤이 문서에 삽입됩니다.  Windows Forms 컨트롤이 새 위치에 나타나지 않고 원본 컨트롤에 숨겨진 코드가 컨테이너 ActiveX 컨트롤에 복사되지 않습니다.|  
  
## 문서 수준 프로젝트의 제한 사항  
 문서에 Windows Forms 컨트롤을 사용할 때의 제한 사항 중 일부는 문서 수준 프로젝트에만 해당됩니다.  
  
### 디자인 타임의 컨트롤 지원  
 Visual Studio 디자이너에서 Excel 워크시트나 Word 문서를 열 때 특정 Windows Forms 컨트롤은 **도구 상자**에서 제거됩니다.  이러한 컨트롤이 제거되는 이유는 기술적인 제한 때문이거나 Word나 Excel에서 이미 사용할 수 있는 기능이기 때문일 수 있습니다.  문서에 포커스가 있는 경우 Excel 및 Word 프로젝트에서는 **도구 상자**에 나타나는 모든 Windows Forms 컨트롤과 그 밖의 구성 요소를 지원할 뿐만 아니라 타사 컨트롤도 워크시트나 문서에 추가할 수 있도록 지원합니다.  
  
> [!NOTE]  
>  문서가 보호되어 있으면 모든 컨트롤이 **도구 상자**에서 제거됩니다.  문서 보호에 대한 자세한 내용은 [문서 수준 솔루션의 문서 보호](../vsto/document-protection-in-document-level-solutions.md)를 참조하십시오.  
  
> [!NOTE]  
>  타사 컨트롤의 경우 <xref:System.Runtime.InteropServices.ComVisibleAttribute> 특성이 **true**로 설정되어 있어야만 Office 솔루션에 사용할 수 있습니다.  
  
 다음 컨트롤과 구성 요소는 **도구 상자**에서 사용할 수 없습니다.  
  
-   <xref:System.Windows.Forms.BindingNavigator>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.DataGrid>  
  
-   <xref:System.DirectoryServices.DirectoryEntry>  
  
-   <xref:System.DirectoryServices.DirectorySearcher>  
  
-   <xref:System.Windows.Forms.ErrorProvider>  
  
-   <xref:System.Diagnostics.EventLog>  
  
-   <xref:System.IO.FileSystemWatcher>  
  
-   <xref:System.Windows.Forms.FlowLayoutPanel>  
  
-   <xref:System.Windows.Forms.GroupBox>  
  
-   <xref:System.Windows.Forms.MainMenu>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Messaging.MessageQueue>  
  
-   <xref:System.Windows.Forms.NotifyIcon>  
  
-   <xref:System.Windows.Forms.PageSetupDialog>  
  
-   <xref:System.Windows.Forms.Panel>  
  
-   <xref:System.Diagnostics.PerformanceCounter>  
  
-   <xref:System.Windows.Forms.PrintDialog>  
  
-   <xref:System.Drawing.Printing.PrintDocument>  
  
-   <xref:System.Windows.Forms.PrintPreviewControl>  
  
-   <xref:System.Diagnostics.Process>  
  
-   <xref:System.Windows.Forms.RichTextBox>  
  
-   <xref:System.IO.Ports.SerialPort>  
  
-   <xref:System.ServiceProcess.ServiceController>  
  
-   <xref:System.Windows.Forms.SplitContainer>  
  
-   <xref:System.Windows.Forms.Splitter>  
  
-   <xref:System.Windows.Forms.StatusBar>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.TabControl>  
  
-   <xref:System.Windows.Forms.TableLayoutPanel>  
  
-   <xref:System.Timers.Timer>  
  
-   <xref:System.Windows.Forms.Timer>  
  
-   <xref:System.Windows.Forms.ToolBar>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.ToolStripContainer>  
  
-   <xref:System.Windows.Forms.ToolStripDropDown>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownMenu>  
  
-   <xref:System.Windows.Forms.ToolStripPanel>  
  
### 레거시 ActiveX 컨트롤 지원  
 ActiveX 컨트롤이 포함된 기존 Word 문서나 Excel 통합 문서를 사용하는 문서 수준 Office 프로젝트를 만드는 경우 ActiveX 컨트롤의 기능이 유지되지만 Visual Studio 내에서 문서에 새로운 ActiveX 컨트롤을 추가할 수 없습니다.  예를 들어 **컨트롤** 도구 상자의 단추가 Word 문서에 들어 있고 이 단추가 VBA\(Visual Basic for Applications\) 매크로를 실행하는 경우 Office 프로젝트에서 문서를 사용한 후에도 이 단추는 계속하여 이 매크로를 실행합니다.  그러나 ActiveX 컨트롤과 VBA 매크로를 제거하고 Windows Forms 컨트롤과 관리 코드로 바꾸는 것이 더 좋습니다.  
  
## 참고 항목  
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)  
  
  
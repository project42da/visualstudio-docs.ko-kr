---
title: "편집기 어댑터로 새롭거나 변경 된 동작 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-어댑터 동작"
ms.assetid: 5555b116-cfdb-4773-ba62-af80fda64abd
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 편집기 어댑터로 새롭거나 변경 된 동작
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio core 편집기의 이전 버전에 대해 작성 한 코드를 업데이트 하는 새로운 API를 사용 하는 대신 편집기 어댑터 \(또는 shim\)를 사용 하려는 경우 이전 코어 편집기와 관련 하 여 편집기 어댑터의 동작에 다음과 같은 차이점을 알고 있어야 합니다.  
  
## 기능  
  
#### SetSite\(\)를 사용 하 여  
 호출 해야 <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite.SetSite%2A> 텍스트 버퍼, 텍스트 뷰를 CoCreate 하 고 다른 작업을 수행 하기 전에 windows 코드입니다. 그러나이 필요 없는 사용 하는 경우는 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> 를 자체는이 서비스의 create \(\) 메서드를 호출 하기 때문에 만드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.SetSite%2A>합니다.  
  
#### 자신의 내용을 IVsCodeWindow 및 IVsTextView 호스팅  
 둘 다 호스트할 수 있습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Win32 모드 또는 WPF 모드를 사용 하 여 자신의 내용을 합니다. 그러나 두 가지 모드에서 몇 가지 차이점은입니다 유지 해야 합니다.  
  
##### IVsCodeWindow의 Win32 및 WPF 버전을 사용 하 여  
 코드 편집기 창에서 파생 됩니다 <xref:Microsoft.VisualStudio.Shell.WindowPane>, 이전 Win32를 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 새 WPF 뿐만 아니라 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> 인터페이스입니다. 사용할 수는 <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsWindowPane%23CreatePaneWindow%2A> HWND 기반 호스팅 환경에서 만드는 메서드를 또는 <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsUIElementPane%23CreateUIElementPane%2A> WPF 호스팅 환경을 만드는 방법. 기본 편집기는 항상 WPF을 사용 하지만이 창을 선택 내용을 직접에 직접 포함 하는 경우 호스팅 요구 사항에 맞는 창의 종류를 만들 수 있습니다.  
  
##### IVsTextView의 Win32 및 WPF 버전을 사용 하 여  
 설정할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Win32 모드 또는 WPF 모드에 있습니다.  
  
 편집기 팩터리의 HWND 내에서 호스팅되는 기본적으로 텍스트 뷰를 만들 때 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> HWND를 반환 합니다. WPF 컨트롤 내 편집기를 포함 하려면이 모드를 사용 하지 해야 합니다.  
  
 텍스트 뷰 WPF 모드로 설정 하려면 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.Initialize%2A> 전달 <xref:Microsoft.VisualStudio.TextManager.Interop.TextViewInitFlags3> 플래그는 초기화 중 하나를에서으로 `InitView` 매개 변수입니다. 가져올 수는 <xref:System.Windows.FrameworkElement> 를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane.CreateUIElementPane%2A>합니다.  
  
 WPF 모드는 두 가지 방법으로 Win32 모드에서 다릅니다. 첫째, WPF 컨텍스트에서 텍스트 뷰를 호스팅할 수 있습니다. 캐스팅 하 여 WPF 창에 액세스할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElement.GetUIObject%2A>합니다. 둘째, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> 여전히 반환 HWND 되지만이 HWND의 위치를 확인 하 고 포커스를 설정에 사용 될 수 있습니다. 하지 것은 편집기 창을 칠하는 하는 방법에 영향을 주지 WM\_PAINT 메시지에 응답 하도록이 HWND를 사용 해야 합니다. 이 HWND 어댑터를 사용 하 여 새 코드 편집기로의 전환을 용이 하 게 하기 위해만 제공 됩니다. 사용 하지 않아야 것이 좋습니다 `VIF_NO_HWND_SUPPORT` 요소에서 반환 된 HWND의 제한으로 인해 작동 하도록 HWND에 필요한 경우 `GetWindowHandle` 이 모드에 있는 동안.  
  
#### 네이티브 코드의 배열을 매개 변수로 전달  
 배열 및 해당 개수를 포함 하는 매개 변수가 있는 레거시 편집기 API에서에서 많은 방법이 있습니다. 예제입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.AppendViewOnlyMarkerTypes%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.RemoveViewOnlyMarkerTypes%2A>  
  
 네이티브 코드에서 이러한 메서드를 호출 하는 경우 한 번에 하나의 요소만 전달 해야 합니다. 둘 이상의 요소에 전달 하는 경우 호출이 거부 됩니다, 주 interop 구현 문제로 인해.  
  
 문제는와 같은 방법으로 더 복잡 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.SetIgnoreMarkerTypes%2A>합니다. 이 메서드가 호출 될 때마다 간단히이 메서드를 호출 세 번 3 다른 표식 유형을 통해 되지 않으므로 무시 표식 유형의 이전 목록을 지웁니다. 해결 하는 유일한 방법은 관리 되는 코드에만이 메서드를 호출 하는 것입니다.  
  
#### 스레딩  
 버퍼 어댑터 UI 스레드에서 호출 해야 합니다. 버퍼 어댑터는 COM 마샬링에 관리 코드에서 호출을 무시 하는 전화는 자동으로 마샬링할 수 없는 UI 스레드를 의미 하는 관리 되는 개체입니다.  백그라운드 스레드에서 버퍼 어댑터를 호출 하는 경우에 사용 해야 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 또는 이와 비슷한 메서드.  
  
#### LockBuffer 메서드  
 모든 LockBuffer\(\) 메서드가 지원 되지 않습니다. 예제입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.LockBuffer%2A>  
  
#### 이벤트를 커밋  
 커밋 이벤트가 지원 되지 않습니다. 이러한 이벤트에 대 한 조언 하는 메서드를 호출 하면 메서드가 오류 코드를 반환 하도록 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUndoRedoClusterWithCommitEvents>  
  
#### TextEditorEvents  
 <xref:EnvDTE.TextEditorEvents> commit \(\)에 더 이상 발생 합니다. 대신 텍스트 변경 될 때마다 시작 됩니다.  
  
#### 텍스트 표식  
 호출 해야 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker.Invalidate%2A> 에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker> 개체를 제거 하면 됩니다. 이전 버전 릴리스 표식에만 필요 합니다.  
  
#### 줄 번호  
 다양 한 방법에 대 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx>, 기본 버퍼 줄 번호에 해당 하는 줄 번호, 줄이 아니라 해당 개요 및 단어 잘림, Visual Studio 2008에서와 같이 요소 번호입니다.  
  
 영향을 받는 방법 \(목록 전부가 아닙니다\) 다음과 같습니다.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.CenterLines%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetCaretPos%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetLineAndColumn%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetNearestPosition%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetPointOfLineColumn%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetTextStream%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWordExtent%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.PositionCaretForEditing%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.ReplaceTextOnLine%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetCaretPos%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetSelection%2A>  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.SetTopLine%2A>  
  
#### 개요  
 클라이언트의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 를 사용 하 여 추가 된 개요 영역만 표시 됩니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A>또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSessionEx.AddHiddenRegionsEx%2A>합니다. 되지 편집기 어댑터를 통해 추가 되지 않습니다 때문에 임시 영역이 표시 됩니다. 마찬가지로, 이러한 클라이언트는 개요 편집기 어댑터 보다는 새 코드 편집기를 사용 하는 언어 \(C\# 및 c \+ \+ 포함\)으로 추가 영역을 표시 되지 않습니다.  
  
#### 줄 높이  
 새 편집기에서 텍스트 줄 높이가 글꼴 크기 및 다른 줄에 상대적인 해당 줄을 이동할 수 있는 가능한 줄 변환에 따라 다를 가질 수 있습니다. 줄 높이 등의 메서드가 반환한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetLineHeight%2A> 적용 없는 줄 변환을 사용 하 여 기본 글꼴 크기를 사용 하 여 줄의 높이입니다. 이 높이 되거나 보기에는 줄의 실제 높이 나타내지 않을 수 있습니다.  
  
#### 이벤트 및 실행 취소  
 새 편집기에서 보기 계속 렌더링 및 실행 취소 클러스터가 열려 있는 경우에 계속 해 서 이벤트를 발생 시키는 등의 작업을 수행 합니다. 이 동작은 실행 취소 클러스터의 닫는 지날 때까지 해당 작업을 수행 하지 않은 하는 레거시 보기의 구현과 다릅니다.  
  
#### IntelliSense  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.UpdateTipWindow%2A> 메서드를 구현 하지 않는 클래스에 전달 하는 경우 사용할 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextTipWindow2> 또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow3>합니다. 사용자 지정 Win32 소유자가 그린 팝업 이상 지원 되지 않습니다.  
  
#### 스마트 태그  
 스마트 태그를 사용 하 여 만든 어댑터 지원은 없습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagData>, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow>, 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow2> 인터페이스입니다.  
  
#### DTE  
 <xref:EnvDTE80.IncrementalSearch> 구현 되지 않았습니다.  
  
## 구현 되지 않은 메서드  
 텍스트 버퍼 어댑터, 텍스트 뷰 어댑터 및 텍스트 레이어 어댑터에 일부 메서드가 구현 되지 않았으므로.  
  
|인터페이스|구현 되지 않음|  
|-----------|--------------|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>|`Reload(false)` 구현 되지 않았습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.EnumSpans%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetBufferMappingModes%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.GetMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.ReleaseMarkerData%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CanReplaceLines%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CopyLineText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.EnumLayerMarkers%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetBaseBuffer%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLengthOfLine%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLineCount%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetLineText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.GetMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.LockBufferEx%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.MapLocalSpansToTextOriginatingLayer%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReleaseMarkerData%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReplaceLines%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.ReplaceLinesEx%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.UnlockBufferEx%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView.GetSelectedAtom%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetSelectionDataObject%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.PositionCaretForEditing%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.RestrictViewRange%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateViewFrameCaption%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.GetSmartTagRect%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.InvokeInsertionUI%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.SetHoverWaitTimer%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow.SetViewClassID%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.AfterCompletorCommit%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.BeforeCompletorCommit%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.Exec%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetContextLocation%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetServiceProvider%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSmartTagRect%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectCaretPos%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectSelection%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetSubjectText%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.QueryStatus%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.ReplaceSubjectTextSpan%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.SetSubjectCaretPos%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.SetSubjectSelection%2A><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.UpdateSmartTagWindow%2A>|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost.SetSubjectFromPrimaryBuffer%2A> 개요는 UI에 의해 무시 하지만 어댑터에서 구현 됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx.GetBannerAttr%2A> 개요는 UI에 의해 무시 하지만 어댑터에서 구현 됩니다.|
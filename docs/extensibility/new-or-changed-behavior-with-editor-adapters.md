---
title: 편집기 어댑터로 새롭거나 변경 된 동작 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - adapter behavior
ms.assetid: 5555b116-cfdb-4773-ba62-af80fda64abd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 22028b1b2725f184c3d5748f2885a17d4bff0c60
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="new-or-changed-behavior-with-editor-adapters"></a>편집기 어댑터로 새롭거나 변경 된 동작
편집기 어댑터의 동작에 다음과 같은 차이점을 알고 있어야 이전 버전의 Visual Studio 핵심 편집기에 대해 작성 된 코드를 업데이트 하는 새로운 API를 사용 하는 대신 편집기 어댑터 (또는 shim)를 사용 하려는 경우 와 관련 하 여 이전 코어 편집기입니다.  
  
## <a name="features"></a>기능  
  
#### <a name="using-setsite"></a>SetSite()를 사용 하 여  
 호출 해야 <xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite.SetSite%2A> 텍스트 버퍼를 텍스트 뷰를 CoCreate 하지 못했습니다. 및 코드에 다른 작업을 수행 하기 전에 창을 합니다. 그러나이 작업이 필요 없습니다 사용 하는 경우는 <xref:Microsoft.VisualStudio.Editor.IVsEditorAdaptersFactoryService> 를 자체는이 서비스의 create () 메서드를 호출 하므로 만드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.SetSite%2A>합니다.  
  
#### <a name="hosting-ivscodewindow-and-ivstextview-in-your-own-content"></a>자신의 내용을 IVsCodeWindow 및 IVsTextView 호스팅  
 둘 다 호스트할 수 있습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Win32 모드 또는 WPF 모드를 사용 하 여 자신의 내용을 합니다. 그러나 두 가지 모드에 차이가 있는지 염두에서 유지 해야 합니다.  
  
##### <a name="using-win32-and-wpf-versions-of-ivscodewindow"></a>IVsCodeWindow의 Win32 및 WPF 버전을 사용 하 여  
 코드 편집기 창에서 파생 된 <xref:Microsoft.VisualStudio.Shell.WindowPane>, 구현 하는 이전 Win32 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> 새 WPF 뿐만 아니라 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> 인터페이스입니다. 사용할 수는 <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsWindowPane%23CreatePaneWindow%2A> HWND 기반 호스팅 환경에서 만드는 메서드를 또는 <xref:Microsoft.VisualStudio.Shell.WindowPane.Microsoft%23VisualStudio%23Shell%23Interop%23IVsUIElementPane%23CreateUIElementPane%2A> WPF 호스팅 환경을 만들려면 메서드. 기본 편집기 항상 WPF를 사용 하지만이 창의 내용을 직접에 직접 포함 하는 경우 호스팅 요구 사항에 맞는 창의 종류를 만들 수 있습니다.  
  
##### <a name="using-win32-and-wpf-versions-of-ivstextview"></a>IVsTextView의 Win32 및 WPF 버전을 사용 하 여  
 설정할 수 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> Win32 모드 또는 WPF 모드에 있습니다.  
  
 편집기 팩터리 HWND 내에서 호스팅되는 기본적으로 텍스트 보기를 만들 때 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> HWND를 반환 합니다. WPF 컨트롤 안에 편집기를 포함 하려면이 모드를 사용 하지 해야 합니다.  
  
 텍스트 보기 WPF 모드로 설정 하려면 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.Initialize%2A> 전달 <xref:Microsoft.VisualStudio.TextManager.Interop.TextViewInitFlags3> 의 플래그는 초기화 중 하나를 따라는 `InitView` 매개 변수입니다. 가져올 수는 <xref:System.Windows.FrameworkElement> 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane.CreateUIElementPane%2A>합니다.  
  
 WPF 모드는 두 가지 방법으로 Win32 모드에서 다릅니다. 첫째, WPF 컨텍스트에서 텍스트 보기를 호스팅할 수 있습니다. WPF 창 캐스팅 하 여 액세스할 수 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElementPane> 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIElement.GetUIObject%2A>합니다. 두 번째, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetWindowHandle%2A> 여전히 반환 HWND 하지만이 HWND의 위치를 확인 하 고 포커스 설정에 사용할 수 있습니다. 되지 영향을 주므로 편집기 창의 그리는 방법을 WM_PAINT 메시지에 응답 하도록이 HWND를 사용 하지 해야 합니다. 이 HWND를이 어댑터를 사용 하 여 새 편집기 코드로의 전환을 용이 하 게 하려면만 표시 됩니다. 사용 하지 않아야 것이 좋습니다 `VIF_NO_HWND_SUPPORT` 구성 요소에서 반환 된 HWND에 대 한 제한으로 인해 작동 하도록 하는 HWND에 필요한 경우 `GetWindowHandle` 이 모드에 있는 동안 합니다.  
  
#### <a name="passing-arrays-as-parameters-in-native-code"></a>네이티브 코드의 배열을 매개 변수로 전달  
 레거시 편집기 API에서에서 배열 및 해당 개수를 포함 하는 매개 변수가 있는 여러 메서드가 있습니다. 예제입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.AppendViewOnlyMarkerTypes%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.RemoveViewOnlyMarkerTypes%2A>  
  
 네이티브 코드에서 이러한 메서드를 호출 하는 경우 한 번에 하나의 요소만 전달 해야 합니다. 둘 이상의 요소에 전달 하는 경우 호출이 거부 주 interop 구현에 문제가 있기 때문일 합니다.  
  
 문제는와 같은 방법으로 더 복잡 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx.SetIgnoreMarkerTypes%2A>합니다. 이 메서드를 호출할 때마다 단순히 3 다른 표식 유형을 통해이 메서드를 세 번 호출 하는 것이 불가능 하므로 무시 표식 유형의 이전 목록을 지웁니다. 유일한 해결 방법은 관리 되는 코드에만이 메서드를 호출 하는 것입니다.  
  
#### <a name="threading"></a>스레딩  
 버퍼 어댑터 UI 스레드에서 호출 해야 합니다. 버퍼 어댑터는 COM 마샬링에 관리 코드에서 호출을 무시 하는 전화는 자동으로 마샬링할 수 없는 UI 스레드를 의미 하는 관리 되는 개체입니다.  백그라운드 스레드에서 버퍼 어댑터를 호출 하는 경우에 사용 해야 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 또는 비슷한 메서드.  
  
#### <a name="lockbuffer-methods"></a>LockBuffer 메서드  
 모든 LockBuffer() 메서드는 사용 되지 않습니다. 예제입니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.LockBuffer%2A>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.LockBuffer%2A>  
  
#### <a name="commit-events"></a>이벤트를 커밋  
 커밋 이벤트가 지원 되지 않습니다. 이러한 이벤트에 대 한 조언 하는 메서드를 호출 하면는 메서드가 오류 코드를 반환 합니다.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPreliminaryTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFinalTextChangeCommitEvents>  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUndoRedoClusterWithCommitEvents>  
  
#### <a name="texteditorevents"></a>TextEditorEvents  
 <xref:EnvDTE.TextEditorEvents> commit ()에 더 이상 실행 됩니다. 대신 모든 텍스트 변경 시 시작 됩니다.  
  
#### <a name="text-markers"></a>텍스트 표식  
 호출 해야 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker.Invalidate%2A> 에 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarker> 개체를 제거 하면 됩니다. 이전 버전에서 릴리스 표식에만 필요 합니다.  
  
#### <a name="line-numbers"></a>줄 번호  
 다양 한 방법에 대 한 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEx>, 기본 버퍼 줄 번호에 해당 하는 줄 번호, 하지 줄 번호만 개요 및 줄 바꿈, Visual Studio 2008에서와 같이 해당 요인이 있습니다.  
  
 영향을 받는 메서드 (목록은 완전 한 목록이 아님) 하는 다음과 같습니다.  
  
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
  
#### <a name="outlining"></a>개요  
 서비스의 클라이언트가 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession> 를 사용 하 여 추가 된 개요 영역만 표시 됩니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSession.AddHiddenRegions%2A>또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextSessionEx.AddHiddenRegionsEx%2A>합니다. 되지 편집기 어댑터를 통해 추가 되지 않습니다 때문에 임시 영역이 표시 됩니다. 마찬가지로, 이러한 클라이언트는 개요 편집기 어댑터 보다는 새 편집기 코드를 사용 하는 언어 (C# 및 c + + 포함)에 의해 추가 되는 영역을 표시 되지 않습니다.  
  
#### <a name="line-heights"></a>줄 높이  
 새 편집기에서 텍스트 줄 높이가 글꼴 크기 및 다른 줄을 기준으로 해당 줄을 이동할 수 있는 가능한 줄 변환에 따라 다를 가질 수 있습니다. 줄 높이 같은 방법으로 반환 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.GetLineHeight%2A> 적용 없는 라인 변환을 사용 하 여 기본 글꼴 크기를 사용 하 여 줄의 높이 같습니다. 이 높이 되거나 보기에는 줄의 실제 높이 나타내지 않을 수도 있습니다.  
  
#### <a name="eventing-and-undo"></a>이벤트 기록 및 실행 취소  
 새 편집기에서 보기 계속 렌더링 및 실행 취소 클러스터 열릴 경우에 계속 해 서 이벤트를 발생 시키는 같은 작업을 수행 합니다. 이 동작은 실행 취소 클러스터의 닫는 지날 때까지 해당 작업을 수행 하지 않은 레거시 뷰의 다릅니다.  
  
#### <a name="intellisense"></a>IntelliSense  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.UpdateTipWindow%2A> 메서드를 구현 하지 않는 클래스에서 전달 하는 경우 사용할 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextTipWindow2> 또는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsMethodTipWindow3>합니다. 사용자 지정 Win32 소유자가 그린 팝업 이상 지원 되지 않습니다.  
  
#### <a name="smarttags"></a>스마트 태그  
 스마트 태그를 사용 하 여 만든 어댑터 지원은 없습니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagData>, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow>, 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSmartTagTipWindow2> 인터페이스입니다.  
  
#### <a name="dte"></a>DTE  
 <xref:EnvDTE80.IncrementalSearch> 구현 되지 않았습니다.  
  
## <a name="unimplemented-methods"></a>구현 되지 않은 메서드  
 텍스트 버퍼 어댑터, 텍스트 뷰 어댑터 및 텍스트 레이어 어댑터에 일부 메서드가 구현 되지 않았으므로 합니다.  
  
|인터페이스|구현 되지 않음|  
|---------------|---------------------|  
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
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewIntellisenseHost.SetSubjectFromPrimaryBuffer%2A> 개요 UI에 의해 무시 되지만 어댑터에서 구현 됩니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenRegionEx.GetBannerAttr%2A> 개요 UI에 의해 무시 되지만 어댑터에서 구현 됩니다.|
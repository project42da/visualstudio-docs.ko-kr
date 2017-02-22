---
title: "이벤트에 가입 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "실행 중인 문서에 있는 표 (RDT) 이벤트에 응답"
  - "이벤트를 구독 실행 문서 테이블 (RDT)"
ms.assetid: e94a4fea-94df-488e-8560-9538413422bc
caps.latest.revision: 35
caps.handback.revision: 33
ms.author: "gregvanl"
manager: "ghogen"
---
# 이벤트에 가입
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습을 실행 중인 document 테이블 \(RDT\)의 이벤트에 응답 하는 도구 창을 만드는 방법을 설명 합니다. 구현 하는 사용자 컨트롤을 호스트 하는 도구 창 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>합니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> 메서드 이벤트에는 인터페이스를 연결 합니다.  
  
## 사전 요구 사항  
 이 연습을 수행 하려면 Visual Studio SDK를 설치 해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하십시오.  
  
## RDT 이벤트 구독  
  
#### 확장 프로그램을 만들려면 도구 창  
  
1.  라는 프로젝트 **RDTExplorer** 라는 사용자 지정 도구 창 항목 템플릿을 추가 하 고 VSIX 템플릿을 사용 하 여 **RDTExplorerWindow**합니다.  
  
     도구 창으로 확장을 만들기에 대 한 자세한 내용은 참조 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
#### RDT 이벤트를 구독할 수  
  
1.  RDTExplorerWindowControl.xaml 파일을 열고 라는 단추를 삭제할 `button1`합니다. 추가 <xref:System.Windows.Forms.ListBox> 제어 하 고 기본 이름을 적용 합니다. Grid 요소는 다음과 같습니다.  
  
    ```xml  
    <Grid> <StackPanel Orientation="Vertical" Margin="-10,10,10,0"> <TextBlock Margin="10" HorizontalAlignment="Center">RDTExplorerWindow</TextBlock> <ListBox x:Name="listBox" Height="100" /> </StackPanel> </Grid>  
    ```  
  
2.  코드 보기에서 RDTExplorerWindow.cs 파일을 엽니다. 다음 코드를 추가 문을 사용 하 여 파일의 시작 부분에 있습니다.  
  
    ```c#  
    using Microsoft.VisualStudio; using Microsoft.VisualStudio.Shell; using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3.  수정는 `RDTExplorerWindow` 하므로 클래스에서 파생 하는 외에 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> 구현 클래스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> 인터페이스입니다.  
  
    ```c#  
    public class RDTExplorerWindow : ToolWindowPane, IVsRunningDocTableEvents {. . .}  
    ```  
  
4.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>를 구현해야 합니다.  
  
    -   인터페이스를 구현 합니다. IVsRunningDocTableEvents 이름 뒤에 커서를 놓습니다. 전구가 왼쪽된 여백에 표시 됩니다. 전구의 오른쪽에 아래쪽 화살표를 클릭 하 고 선택 **인터페이스 구현**합니다.  
  
5.  인터페이스에서 각 방법의 경우에서 줄을 바꿉니다 `throw new NotImplementedException();` 이 있습니다.  
  
    ```c#  
    return VSConstants.S_OK;  
    ```  
  
6.  쿠키 필드 RDTExplorerWindow 클래스를 추가 합니다.  
  
    ```c#  
    private uint rdtCookie;   
    ```  
  
     이 반환 되는 쿠키는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> 메서드.  
  
7.  RDT 이벤트에 등록 하는 RDTExplorerWindow initialize \(\) 메서드를 재정의 합니다. 생성자에 없는 ToolWindowPane의 initialize \(\) 메서드에서 항상 서비스를 구해야 합니다.  
  
    ```c#  
    protected override void Initialize() { IVsRunningDocumentTable rdt = (IVsRunningDocumentTable) this.GetService(typeof(SVsRunningDocumentTable)); rdt.AdviseRunningDocTableEvents(this, out rdtCookie); }  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable> 서비스를 가져오기 위해 호출 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> 인터페이스입니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> RDT 이벤트를 구현 하는 개체에 연결 하는 메서드 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>, 이 경우에 RDTExplorer 개체입니다.  
  
8.  RDTExplorerWindow의 dispose \(\) 메서드를 업데이트 합니다.  
  
    ```c#  
    protected override void Dispose(bool disposing) { // Release the RDT cookie. IVsRunningDocumentTable rdt = (IVsRunningDocumentTable) Package.GetGlobalService(typeof(SVsRunningDocumentTable)); rdt.UnadviseRunningDocTableEvents(rdtCookie); base.Dispose(disposing); }  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnadviseRunningDocTableEvents%2A> 메서드 간의 연결을 삭제 `RDTExplorer` 및 RDT 이벤트 알림.  
  
9. 본문에 다음 줄을 추가 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnBeforeLastDocumentUnlock%2A> 처리기 바로 앞의 `return` 문입니다.  
  
    ```c#  
    public int OnBeforeLastDocumentUnlock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining) { ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnBeforeLastDocumentUnlock"); return VSConstants.S_OK; }  
    ```  
  
10. 본문에 이와 유사한 줄을 추가 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterFirstDocumentLock%2A> 처리기 및 목록 상자에 표시 하려는 다른 이벤트입니다.  
  
    ```c#  
    public int OnAfterFirstDocumentLock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining) { ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnAfterFirstDocumentLock"); return VSConstants.S_OK; }  
    ```  
  
11. 프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 됩니다.  
  
12. 열기는 **RDTExplorerWindow** \(**보기 \/ 다른 창 \/ RDTExplorerWindow**\).  
  
     **RDTExplorerWindow** 빈 이벤트 목록을 사용 하 여 창이 열립니다.  
  
13. 페이지를 열거나 솔루션을 만듭니다.  
  
     으로 `OnBeforeLastDocument` 및 `OnAfterFirstDocument` 이벤트가, 각 이벤트에 대 한 알림을 표시 이벤트 목록입니다.
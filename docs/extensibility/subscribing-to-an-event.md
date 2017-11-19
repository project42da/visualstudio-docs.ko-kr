---
title: "이벤트 구독과 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running document table (RDT), responding to events
- running document table (RDT), subscribing to events
ms.assetid: e94a4fea-94df-488e-8560-9538413422bc
caps.latest.revision: "35"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3d2b5d07fb143f84b3680d51624469b9778b42a1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="subscribing-to-an-event"></a>구독 하는 이벤트
이 연습에는 실행 중인 문서 테이블 (RDT)의 이벤트에 응답 하는 도구 창을 만드는 방법을 설명 합니다. 도구 창을 구현 하는 사용자 정의 컨트롤을 호스트 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> 메서드 이벤트에는 인터페이스를 연결 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="subscribing-to-rdt-events"></a>RDT 이벤트 구독  
  
#### <a name="to-create-an-extension-with-a-tool-window"></a>확장 프로그램을 만들려면 도구 창을 사용  
  
1.  라는 프로젝트 **RDTExplorer** VSIX 서식 파일을 사용 하 고 명명 된 사용자 지정 도구 창 항목 템플릿을 추가 **RDTExplorerWindow**합니다.  
  
     도구 창을 사용 된 확장을 만드는 방법에 대 한 자세한 내용은 참조 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다.  
  
#### <a name="to-subscribe-to-rdt-events"></a>RDT 이벤트를 구독할 수  
  
1.  RDTExplorerWindowControl.xaml 파일을 열고 이라는 단추 삭제 `button1`합니다. 추가 <xref:System.Windows.Forms.ListBox> 제어 하 고 기본 이름을 적용 합니다. Grid 요소는 다음과 같이 표시 됩니다.  
  
    ```xml  
    <Grid>  
        <StackPanel Orientation="Vertical" Margin="-10,10,10,0">  
            <TextBlock Margin="10" HorizontalAlignment="Center">RDTExplorerWindow</TextBlock>  
            <ListBox x:Name="listBox" Height="100" />  
        </StackPanel>  
    </Grid>  
    ```  
  
2.  코드 뷰에서 RDTExplorerWindow.cs 파일을 엽니다. 다음 추가 문을 사용 하 여 파일의 시작 부분에 있습니다.  
  
    ```csharp  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    ```  
  
3.  수정는 `RDTExplorerWindow` 하므로 클래스에서 파생 하는 것 외에도 하는 <xref:Microsoft.VisualStudio.Shell.ToolWindowPane> 구현 클래스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> 인터페이스입니다.  
  
    ```csharp  
    public class RDTExplorerWindow : ToolWindowPane, IVsRunningDocTableEvents  
    {. . .}  
    ```  
  
4.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>를 구현해야 합니다.  
  
    -   인터페이스를 구현 합니다. IVsRunningDocTableEvents 이름 뒤에 커서를 놓습니다. 전구가 왼쪽된 여백에 표시 됩니다. 전구의 오른쪽에 아래쪽 화살표를 클릭 하 고 선택 **인터페이스 구현**합니다.  
  
5.  인터페이스에서 각 방법에서 줄을 바꿉니다 `throw new NotImplementedException();` 이:  
  
    ```csharp  
    return VSConstants.S_OK;  
    ```  
  
6.  쿠키 필드 RDTExplorerWindow 클래스를 추가 합니다.  
  
    ```csharp  
    private uint rdtCookie;   
    ```  
  
     이에서 반환 되는 쿠키는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> 메서드.  
  
7.  RDT 이벤트에 대 한 등록 하는 RDTExplorerWindow initialize () 메서드를 재정의 합니다. 항상는 ToolWindowPane initialize () 메서드를 생성자에 없는에서 서비스를 얻어야 합니다.  
  
    ```csharp  
    protected override void Initialize()  
    {  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
        this.GetService(typeof(SVsRunningDocumentTable));  
        rdt.AdviseRunningDocTableEvents(this, out rdtCookie);  
    }  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable> 서비스를 가져오기 위해 호출 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable> 인터페이스입니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> 메서드 구현 하는 개체에 RDT 이벤트 연결 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>,이 경우 RDTExplorer 개체입니다.  
  
8.  RDTExplorerWindow의 dispose () 메서드를 업데이트 합니다.  
  
    ```csharp  
    protected override void Dispose(bool disposing)  
    {  
        // Release the RDT cookie.  
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)  
            Package.GetGlobalService(typeof(SVsRunningDocumentTable));  
        rdt.UnadviseRunningDocTableEvents(rdtCookie);  
  
        base.Dispose(disposing);  
    }  
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.UnadviseRunningDocTableEvents%2A> 메서드 간의 연결을 삭제 `RDTExplorer` 및 RDT 이벤트 알림.  
  
9. 본문에 다음 줄 추가 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnBeforeLastDocumentUnlock%2A> 처리기를 바로 앞의 `return` 문.  
  
    ```csharp  
    public int OnBeforeLastDocumentUnlock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnBeforeLastDocumentUnlock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
10. 본문에 비슷한 줄을 추가 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterFirstDocumentLock%2A> 처리기 및 목록 상자에서 표시 하려는 다른 이벤트입니다.  
  
    ```csharp  
    public int OnAfterFirstDocumentLock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)  
    {  
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnAfterFirstDocumentLock");  
        return VSConstants.S_OK;  
    }  
    ```  
  
11. 프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 됩니다.  
  
12. 열기는 **RDTExplorerWindow** (**보기 / 다른 창 / RDTExplorerWindow**).  
  
     **RDTExplorerWindow** 빈 이벤트 목록을 사용 하 여 창이 열립니다.  
  
13. 페이지를 열거나 솔루션을 만듭니다.  
  
     으로 `OnBeforeLastDocument` 및 `OnAfterFirstDocument` 이벤트가, 각 이벤트에 대 한 알림을 표시 이벤트 목록입니다.
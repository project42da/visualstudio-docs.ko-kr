---
title: "명령 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "명령, 구현"
ms.assetid: c782175c-cce4-4bd0-8374-4a897ceb1b3d
caps.latest.revision: 24
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 24
---
# 명령 구현
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

명령을 vspackage에서를 구현 하려면 다음 작업을 수행 해야 합니다.  
  
1.  .Vsct 파일에 명령 그룹을 설정 하 고에 명령을 추가 합니다. 자세한 내용은 참조 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)'  
  
2.  이 명령은 Visual Studio와 함께 등록 합니다.  
  
3.  명령을 구현 합니다.  
  
 다음 섹션에 등록 하 고 명령을 구현 하는 방법을 설명 합니다.  
  
## Visual Studio 명령 등록  
 추가 해야 하는 경우 프로그램 명령이 메뉴에 표시할 이면는 <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> VSPackage 및 메뉴의 이름이 나 리소스 ID 값으로 사용  
  
```  
[ProvideMenuResource("Menus.ctmenu", 1)]  
...  
    public sealed class MyPackage : Package  
    {.. ..}  
  
```  
  
 사용 하 여 명령을 등록 해야 하는 또한는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService>합니다. 사용 하 여이 서비스를 가져올 수는 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> VSPackage에서 파생 된 경우 메서드 <xref:Microsoft.VisualStudio.Shell.Package>합니다.  
  
```  
OleMenuCommandService mcs = GetService(typeof(IMenuCommandService)) as OleMenuCommandService;  
if ( null != mcs )  
{  
    // Create the command for the menu item.  
    CommandID menuCommandID = new CommandID(guidCommandGroup, myCommandID);  
    MenuCommand menuItem = new MenuCommand(MenuItemCallback, menuCommandID );  
    mcs.AddCommand( menuItem );  
}  
  
```  
  
## 명령을 구현합니다.  
 명령을 구현 하는 방법의 여러 가지가 있습니다. 항상 동일한 방식으로 같은 메뉴에 표시 되는 명령에 있는 정적 메뉴 명령을 원하는 경우 명령을 사용 하 여 만들 <xref:System.ComponentModel.Design.MenuCommand> 이전 섹션의 예제에서와 같이 합니다. 정적 명령을 만들려면, 명령을 실행 하는 일을 담당 하는 이벤트 처리기를 제공 해야 합니다. 명령을 활성화 및 표시 항상 이기 때문에 Visual Studio로 상태를 제공할 필요가 없습니다. 특정 조건에 따라 명령의 상태를 변경 하려는 경우의 인스턴스는 명령을 만들 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 클래스 및 생성자에서 명령을 실행 하는 이벤트 처리기와 명령 상태가 변경 될 때 Visual Studio에 알리기 위해 쿼리 상태 처리기를 제공 합니다. 구현할 수도 있습니다 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 명령 클래스 이거나, 부분을 구현할 수 대로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 명령을 프로젝트의 일부로 제공 하는 경우. 두 가지 인터페이스와 <xref:Microsoft.VisualStudio.Shell.OleMenuCommand> 모든 클래스는 Visual Studio 명령, 상태 변경을 알려 주는 메서드 및 명령 실행을 제공 하는 다른 방법입니다.  
  
 명령을 명령 서비스에 추가 되 면 일련의 명령 중 하나가 됩니다. 해당 명령에만 제공 하 고 체인에 있는 다른 명령에 다른 모든 경우를 전달 하는 명령에 대 한 상태 알림 및 실행 메서드를 구현할 때 주의 하십시오. 명령 전달 하지 못하는 경우 \(일반적으로 반환 하 여 <xref:Microsoft.VisualStudio.OLE.Interop.Constants>\), Visual Studio는 제대로 작동 하지 않을 수 있습니다.  
  
## 쿼리 상태 메서드  
 중 하나를 구현 하는 경우는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> 메서드, 명령 명령 속한 집합의 GUID 확인 하 고 명령의 ID입니다. 이러한 지침을 따릅니다.  
  
-   두 메서드를 구현할을 반환 해야 하는 경우 GUID가 인식 되지 <xref:Microsoft.VisualStudio.OLE.Interop.Constants>합니다.  
  
-   메서드에서 반환 해야 하거나 메서드를 구현할 GUID를 인식 하지만 명령에 실제로 구현 하지 않은 경우 <xref:Microsoft.VisualStudio.OLE.Interop.Constants>합니다.  
  
-   GUID 및 명령에 모두에서 인식 하는 두 메서드를 구현 하는 경우 메서드는 모든 명령의 명령 플래그 필드를 설정 해야 \(에 `prgCmds` 매개 변수\)는 다음 플래그를 사용 하 여:  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 경우 명령을 사용할 수 있습니다.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 경우 명령이 표시 되어야 합니다.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 명령을에서 전환 하 고 검사를 표시 합니다.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 경우 명령이 활성화 됩니다.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 바로 가기 메뉴에 표시 되는 경우이 명령은 숨겨야 하는 경우.  
  
    -   <xref:Microsoft.VisualStudio.OLE.Interop.OLECMDF> 명령 메뉴 컨트롤러가 고을 사용 하지 않는 되지만 해당 드롭다운 메뉴 목록 비어 있지 않으면 계속 사용할 수 있습니다. \(이 플래그는 거의 사용 합니다.\)  
  
-   명령을 사용 하 여.vsct 파일에 정의 되어 있는 경우는 `TextChanges` 플래그는 다음 매개 변수를 설정 합니다.  
  
    -   설정의 `rgwz` 의 요소는 `pCmdText` 매개 변수는 새 명령 텍스트입니다.  
  
    -   설정의 `cwActual` 의 요소는 `pCmdText` 명령 문자열의 크기에 대 한 매개 변수입니다.  
  
 또한 아닌지 확인는 현재 컨텍스트 자동화 기능, 명령 특히 시간은을 자동화 기능을 처리 하지 않는 한 합니다.  
  
 특정 명령 지 나타내려면 반환 <xref:Microsoft.VisualStudio.VSConstants.S_OK>합니다. 다른 모든 명령에 대 한 반환 <xref:Microsoft.VisualStudio.OLE.Interop.Constants>합니다.  
  
 다음 예제에서는 쿼리 상태 메서드 먼저를 사용 하면 컨텍스트는 자동화 함수가 아닙니다 다음 찾습니다 올바른 명령 집합 GUID 및 명령 id입니다. 명령 자체를 활성화 하 고 지원으로 설정 됩니다. 다른 명령은 사용할 수 있습니다.  
  
```  
public int QueryStatus(ref Guid pguidCmdGroup, uint cCmds, OLECMD[] prgCmds, IntPtr pCmdText)  
{  
    if (!VsShellUtilities.IsInAutomationFunction(m_provider.ServiceProvider))  
    {  
        if (pguidCmdGroup == VSConstants.VSStd2K && cCmds > 0)  
        {  
            // make the Right command visible   
            if ((uint)prgCmds[0].cmdID == (uint)VSConstants.VSStd2KCmdID.RIGHT)  
            {  
                prgCmds[0].cmdf = (int)Microsoft.VisualStudio.OLE.Interop.Constants.MSOCMDF_ENABLED | (int)Microsoft.VisualStudio.OLE.Interop.Constants.MSOCMDF_SUPPORTED;  
                return VSConstants.S_OK;  
            }  
        }  
        return Constants.OLECMDERR_E_NOTSUPPORTED;  
    }  
}  
  
```  
  
## 실행 메서드  
 Execute 메서드를 구현을 유사 상태 쿼리 메서드를 구현 합니다. 첫째, 컨텍스트 되지 않았는지 자동화 기능을 확인 합니다. 다음 GUID 및 명령 id입니다. 둘 다에 대 한 테스트 경우 GUID 또는 명령 ID를 인식할 수 없습니다, 반환 <xref:Microsoft.VisualStudio.OLE.Interop.Constants>합니다.  
  
 를 처리 하기 위해 명령을 실행 하 고 반환 <xref:Microsoft.VisualStudio.VSConstants.S_OK> 실행에 성공 합니다. 명령 담당 오류 검색 및 알림. 따라서 실행에 실패 하는 경우 오류 코드를 반환 합니다. 다음 예제에서는 실행 메서드를 구현 해야 하는 방법을 보여 줍니다.  
  
```  
public int Exec(ref Guid pguidCmdGroup, uint nCmdID, uint nCmdexecopt, IntPtr pvaIn, IntPtr pvaOut)  
{  
    if (!VsShellUtilities.IsInAutomationFunction(m_provider.ServiceProvider))  
    {  
        if (pguidCmdGroup == VSConstants.GUID_VSStandardCommandSet97)  
        {  
             if (nCmdID ==(uint) uint)VSConstants.VSStd2KCmdID.RIGHT)  
            {  
                //execute the command  
                return VSConstants.S_OK;  
            }  
        }  
    }  
    return Constants.OLECMDERR_E_NOTSUPPORTED;  
}  
  
```  
  
## 참고 항목  
 [Vspackage에서 사용자 인터페이스 요소를 추가 하는 방법](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
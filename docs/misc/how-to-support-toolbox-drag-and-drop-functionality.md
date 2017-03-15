---
title: "방법: 도구 상자 끌어서 놓기 기능 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "끌어서 놓기, 도구 상자에서 지원"
  - "도구 상자[Visual Studio SDK], 클라이언트"
  - "도구 상자[Visual Studio SDK], 끌어서 놓기"
ms.assetid: 2f73a03c-1eb1-4b88-9c1b-d63ba0e2ac90
caps.latest.revision: 18
caps.handback.revision: 18
manager: "douge"
---
# 방법: 도구 상자 끌어서 놓기 기능 지원
> [!NOTE]
>  도구 상자에 사용자 지정 컨트롤을 추가하기 위해 권장되는 방법은 Visual Studio 10 SDK와 함께 제공되는 도구 상자 컨트롤 템플릿을 사용하는 것이며 이는 끌어서 놓기 기능을 지원합니다. 이 항목은 이전 버전과의 호환성을 위해서만 유지되며 기존 컨트롤 사용을 위한 것입니다.  
>   
>  템플릿을 사용하여 도구 상자 컨트롤을 만드는 방법에 대한 자세한 내용은 [방법: Windows Forms를 사용하는 도구 상자 컨트롤 만들기](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) 및 [WPF 도구 상자 컨트롤 만들기](../extensibility/creating-a-wpf-toolbox-control.md)를 참조하세요.  
  
 VSPackage가 편집기 또는 디자이너와 같은 문서 보기에서 **도구 상자**  컨트롤을 사용하려면 끌어서 놓기 지원을 구현해야 합니다.  
  
 기본적으로 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 자동으로 투명하게 파생된 모든 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 개체는 **도구 상자** 컨트롤 사용을 위한 지원을 제공하며 아래 설명된 프로시저는 필요하지 않습니다. 디자이너를 만들면 기본 기능을 확장할 수 있습니다.  
  
 자세한 내용은 [Windows Forms 개요](../Topic/Windows%20Forms%20Overview.md) 및 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)를 참조하세요.  
  
### 기본 끌어서 놓기 기능을 구현하려면  
  
1.  보기 개체에서 <xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>을 구현하면 끌어서 놓기가 지원됩니다. 이렇게 하면 OLE 끌어서 놓기 기능과 컨트롤 serialization을 사용할 수 있는 보기가 제공됩니다.  
  
     끌어서 놓기 기능 구현에 대한 자세한 내용은 [끌어서 놓기\(OLE\)](/visual-cpp/mfc/drag-and-drop-ole)을 참조하세요.  
  
     놓기 대상은 클립보드 항목 또는 디자이너에 끌어 놓는 컨트롤이 될 수 있습니다.[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **도구 상자**에서 지원하는 표준 클립보드 형식에 대한 자세한 내용은 [도구 상자 확장](../misc/extending-the-toolbox.md)를 참조하세요.  
  
2.  문서 보기에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> 인터페이스의 기본 구현을 제공합니다.  
  
     사용자가 보기에 도구 상자 컨트롤을 끌어 오려고 할 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셸이 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> 인터페이스가 구현되었는지 확인하기 위해 보기의 VSPackage를 쿼리합니다.  
  
    1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser.IsSupported%2A>를 구현하여 놓기 대상이 지원하는 해당 **도구 상자** 형식에 대한 <xref:Microsoft.VisualStudio.VSConstants.S_OK>를 반환합니다. 아래 예제에서는 데이터 개체가 사용자 지정 클립보드 형식\(`CF_CUSTOM_FORMAT`\)인지, ActiveX 컨트롤인지 여부를 확인합니다.  
  
        ```cpp#  
        STDMETHODIMP CustTbxUser::IsSupported(IDataObject* pDO) { HRESULT hr; STGMEDIUM stm; if (!pDO) return E_POINTER; // Determine if the data object is in the Custom clip board format // fetc is the dialog editor toolbox item template. FORMATETC fetc = { m_CF_CUSTOM_FORMAT, //Value set with RegisterClipboardFormat NULL, DVASPECT_CONTENT, // DVASCPECT_ICON might be better -1, TYMED_HGLOBAL }; if (FAILED(hr = pDO->GetData(&fetc, &stm))) { // Determine if the object is in the class-id clipboard format ... this // would be the case if the control is an activeX toolbox item. FORMATETC xfetc = { m_CF_CLSID, NULL, DVASPECT_CONTENT, // DVASCPECT_ICON might be better -1, TYMED_HGLOBAL }; if (SUCCEEDED(hr = pDO->GetData(&xfetc,&stm))) { USES_CONVERSION; GUID guid; LPSTR pData = (LPSTR)GlobalLock(stm.hGlobal); if (pData) { // Convert from the string format to a binary GUID. if (CLSIDFromString(A2W(pData), &guid) != S_OK) return E_FAIL; // HTML data objects could have CLSID format ... so any data object could // be returned as a NULL guid ... fail on null guid, obviously they are // not active X controls. if (guid == GUID_NULL) return E_FAIL; } } } return hr; }  
        ```  
  
         보기 창이 처음 로드될 때 및 사용자가 IDE의 **사용자 지정 도구 상자** 대화 상자를 통해 **도구 상자**를 다시 설정한 이후 모든 보기 창이 활성화될 때마다 이 정보에 대한 IDE를 확인합니다. 일반적으로 **도구 상자**는 지원되지 않는 **도구 상자** 항목을 표시하지 않습니다.  
  
         사용자가 모든 도구 상자 페이지가 항상 표시되도록 옵션을 설정할 수 있습니다. 이 경우 환경은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser.IsSupported%2A>에 대해 편집기를 쿼리하지 않습니다.  
  
    2.  <xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget> 구현\(예: 위에서 설명한 항목\)으로 끌어 놓은 구성 요소를 성공적으로 처리한 후 보기 개체에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2.DataUsed%2A>을 호출하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 환경에 알려야 합니다.  
  
     원하는 경우 VSPackage는 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> 구현을 확장함으로써 끌어서 놓기 지원을 확장할 수 있습니다.  
  
3.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> 구현은 마우스 작업이 아닌 선택 작업으로 **도구 상자** 항목을 창으로 끌 수 있습니다. 즉, **도구 상자** 항목을 두 번 클릭하거나 한 번 클릭한 다음 \<ENTER\> 키를 누르면 항목 끌기가 수행됩니다. 이렇게 하려면 다음을 수행합니다.  
  
    1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser.ItemPicked%2A> 메서드를 구현합니다.  
  
         IDE에서 호출하는 이 메서드는 한 번 클릭 또는 \<ENTER\> 키를 눌러 선택됩니다.  
  
         메서드는 **도구 상자** 항목을 대상 창으로 삽입합니다.  
  
    2.  선택 작업으로 구현을 지원하지 않으려면 메서드는 <xref:Microsoft.VisualStudio.VSConstants.S_FALSE>을 반환합니다.  
  
         아래 예제에서는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser.ItemPicked%2A> 메서드 구현이 선택한 개체가 지원되는지 확인하고 지원되면 코드로 역직렬화합니다.  
  
        ```cpp#  
        STDMETHODIMP CustTbxUser::ItemPicked(IDataObject* pDataObject) { if (!pDataObject) return E_POINTER; UINT nIDTool; if (IsSupported(pDataObject) == S_OK) { SetToolCursor(); m_pDataObject = pDataObject; nIDTool = DeserializeObject(); // Get the focus back m_pResObject->m_spWndFrame->Show(); return S_OK; } }  
        ```  
  
4.  응용 프로그램에 적절한 포커스가 유지되도록 하려면 다음 단계를 수행합니다.  
  
    1.  편집기 창이 서로 다른 두 개의 보기가 아니라 서로 다른 두 개의 창을 구현하면 편집기 창 내에서 창을 활성화로 전환할 때 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2.UpdateToolboxUI%2A> 메서드를 호출합니다. 창 내에서 활성화 변경이 발생하는 시점은 사용자만 압니다.  
  
    2.  제대로 창을 활성화시키고 명령 라우팅을 업데이트하려면 구성 요소에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 메서드를 호출해야 합니다. 편집기처럼 도구 상자와 관련된 끌어서 놓기 작업으로 만들거나 수정한 구성 요소 창으로 포커스를 설정할 경우 이 작업을 수행해야 합니다.  
  
 VSPackage는 끌기 작업에서 개입하거나 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxActiveUserHook> 인터페이스를 통해 끌어 놓은 항목을 수정해야 할 수 있습니다.  
  
 예를 들어 VSPackage는 **도구 상자**에 새로운 **도구 상자** 컨트롤을 명시적으로 추가하기보다는 끌어 놓고 사용자 지정 구현으로 바꿀 때 표준 **도구 상자**를 가로챌 수 있습니다.  
  
### 도구 상자 컨트롤을 동적으로 수정하려면  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxActiveUserHook> 메서드를 구현합니다.  
  
     **도구 상자** 항목을 선택하거나 끌어 놓을 때마다 **도구 상자**는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxActiveUserHook> 인터페이스를 지원하는지, <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxActiveUserHook.InterceptDataObject%2A> 메서드를 호출하는지 확인하기 위해 놓기 대상을 쿼리합니다.  
  
2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxActiveUserHook.InterceptDataObject%2A> 메서드는 원래 <xref:Microsoft.VisualStudio.OLE.Interop.IDataObject> 대신 사용되는 새 <xref:Microsoft.VisualStudio.OLE.Interop.IDataObject> 개체를 반환해야 합니다.  
  
     놓기 대상이 데이터 개체를 재정의할 필요가 없으면 해당 입력을 반환합니다.  
  
 VSPackage는 CTRL\+SHIFT\+V를 눌러 클립보드의 내용을 순환시킬 수 있습니다.  
  
### 클립보드 링을 지원하려면  
  
1.  다음을 사용하여 `CMDIDPasteNextTBXCBItem` 명령에 대한 처리기를 구현합니다.  
  
    -   interop 어셈블리 기반 VSPackage의 경우 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>  
  
    -   관리되는 패키지 프레임워크 기반 VSPackage의 경우 <xref:Microsoft.VisualStudio.Shell.OleMenuCommandService><xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxClipboardCycler> 인터페이스  
  
2.  명령 처리기에서 순환할 클립보드 개체가 있는지 확인하기 위해 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxClipboardCycler.AreDataObjectsAvailable%2A> 메서드를 구현합니다.  
  
    1.  도구 상자 클립보드에 항목이 없으면 환경은 시스템 클립보드에 항목이 있는지 확인합니다.  
  
    2.  도구 상자 클립보드에는 없지만 시스템 클립보드에 항목이 있으면 시스템 항목으로 클립보드 링을 채웁니다.  
  
    3.  목록에서 다음 항목을 선택하려면 구현이 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxClipboardCycler.GetAndSelectNextDataObject%2A> 메서드를 호출합니다.  
  
    4.  클립보드 순환의 시작으로 돌아가려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxClipboardCycler.BeginCycle%2A> 메서드를 호출합니다.  
  
## 참고 항목  
 [도구 상자 확장](../misc/extending-the-toolbox.md)   
 [방법: Interop 어셈블리를 사용하여 사용자 지정 도구 상자 항목 제공](../misc/how-to-provide-custom-toolbox-items-by-using-interop-assemblies.md)   
 [고급 도구 상자 컨트롤 개발](../misc/advanced-toolbox-control-development.md)   
 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)   
 [도구 상자 관리](../misc/managing-the-toolbox.md)
---
title: "방법: Interop 어셈블리를 사용하여 사용자 지정 도구 상자 항목 제공 | Microsoft Docs"
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
  - "도구 상자[Visual Studio SDK], interop 어셈블리를 사용하여 항목 추가"
ms.assetid: c3e8b404-7086-4e08-9d07-ab9c509963ca
caps.latest.revision: 33
caps.handback.revision: 33
manager: "douge"
---
# 방법: Interop 어셈블리를 사용하여 사용자 지정 도구 상자 항목 제공
> [!NOTE]
>  도구 상자에 사용자 지정 컨트롤을 추가할 때 권장되는 방법은 Visual Studio 10 SDK에서 제공하는 도구 상자 컨트롤 템플릿을 사용하는 것입니다. 이 항목은 기존 컨트롤을 도구 상자에 추가하는 내용이며, 이전 버전과의 호환성을 위해서만 유지됩니다.  
>   
>  템플릿을 사용하여 도구 상자 컨트롤을 만드는 방법에 대한 자세한 내용은 [방법: Windows Forms를 사용하는 도구 상자 컨트롤 만들기](../misc/how-to-create-a-toolbox-control-that-uses-windows-forms.md) 및 [WPF 도구 상자 컨트롤 만들기](../extensibility/creating-a-wpf-toolbox-control.md)를 참조하세요.  
  
 interop 어셈블리를 기반으로 하는 VSPackage는 ActiveX 컨트롤을 추가하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **도구 상자** 기능을 확장할 수 있습니다.  
  
 표준 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 도구 상자 클립보드 형식의 목록은 [도구 상자 확장](../misc/extending-the-toolbox.md)를 참조하세요.  
  
 VSPackage에서 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)]를 사용하여 **도구 상자**를 관리하는 방법은 [도구 상자 관리](../misc/managing-the-toolbox.md)를 참조하세요.  
  
 자동화를 통해 **도구 상자**를 관리하는 방법은 [How to: Control the Toolbox](../Topic/How%20to:%20Control%20the%20Toolbox.md)를 참조하세요.  
  
## 절차  
 항목을 추가하는 VSPackage가 **도구 상자** 항목 공급자의 역할을 하는 경우\(새 형식에 대한 구현 지원 제공\) 이외에는 **도구 상자**에 추가되는 항목은 표준 **도구 상자** 클립보드 형식을 지원해야 합니다.  
  
#### 도구 상자 컨트롤을 구현하려면  
  
-   관리되지 않는 코드에서 구현된 VSPackage가 제공하는 **도구 상자** 항목은 `IDataObject` 개체를 구현하거나 ActiveX 컨트롤\(여기에서 환경이 `IDataObject` 개체를 가져옴\)이어야 합니다.  
  
     **도구 상자**를 지원하기 위해 `IDataObject` 개체를 구현하는 방법에 대한 자세한 내용은 <xref:System.Runtime.InteropServices.ComTypes.IDataObject>, <xref:Microsoft.VisualStudio.Shell.Interop.TBXITEMINFO>, <xref:System.Runtime.InteropServices.ComTypes.FORMATETC> 등을 참조하세요.  
  
#### interop 어셈블리 기반 컨트롤을 도구 상자에 추가하려면  
  
1.  다음의 인스턴스를 가져옵니다.  
  
    1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>, 를 지 원하는 컨트롤 및 섹션 \(탭\)에 추가 도구 상자 의 다른 측면을 제어 하 고는 도구 상자 구성 합니다.  
  
    2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> \- 지역화 및 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 유지에 대한 지원 제공  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox> 인터페이스에서 상속됩니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3>은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>에서 파생되지 않으며 해당 메서드를 구현하지도 않습니다.  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>는 `SID_SVsToolbox`의 서비스 ID를 사용하여 <xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox> 서비스에 대해 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> 메서드를 호출하여 가져옵니다.  
  
     인터페이스 ID `IID_IVSToolbox2`를 사용하여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2>를 가져오며 인터페이스 ID `IID_IVSToolbox3`은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3>을 반환합니다.  
  
     아래 샘플에서는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> 인터페이스에서 `QueryInterface`를 호출하여 `QueryService` 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> 인터페이스로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> 인터페이스를 가져옵니다.  
  
    ```cpp  
    extern CComModule _Module;  
    CComPtr<IVsToolbox2> srpTbx2;  
    CComPtr<IVsToolbox3> srpTbx3;  
    hr = _Module.QueryService(SID_SVsToolbox, IID_IVsToolbox2, (void**) &srpTbx2));  
    hr = srpTbx2->QueryInterface( IID_IVsToolbox3, (void **)&srpTbx3)  
    ```  
  
2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> 인터페이스의 인스턴스를 사용하여 **도구 상자**에 탭\(섹션\)과 컨트롤을 추가합니다.  
  
     아래 샘플에서는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2.AddTab%2A> 메서드를 사용하여 이름이 지역화된 새 탭을 추가합니다.  
  
     이 지역화된 이름은 고정이 아니므로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3.SetIDOfTab%2A> 메서드 호출을 통해 지역화되지 않은 고정 이름\(이 경우 `L"HTML"`\)을 설정합니다.  
  
     도구 상자 탭이 이미 있으면 `AddTab2`는 E\_FAIL을 반환합니다. 이 경우 고정 이름의 검색을 시도하기 전에 탭이 제대로 추가된 것으로 가정됩니다.  
  
     탭이 성공적으로 추가되면 <xref:System.Runtime.InteropServices.ComTypes.IDataObject> 기반 컨트롤이 **도구 상자**에 추가되고 추가되지 않은 경우에는 오류가 반환됩니다.  
  
    ```cpp  
    CComBSTR sbstrID;  
    hr = srpTbx2->AddTab2((WCHAR*)szwDisplayTabName, *pclsidPackage);  
    if ( hr == S_OK) {  
        sbstrID =L"HTML";  
        hr = srpTbx3->SetIDOfTab( (WCHAR*)szwDisplayTabName, sbstrID);  
    }else{  
        hr = S_OK;  
        hr = srpTbx3->GetIDOfTab( (WCHAR*)szwDisplayTabName, &sbstrID );  
  
    }  
    if ( hr = S_OK){  
        hr=srpTbx2->AddItem(tbxItem, &tinfo, bstrLabel);  
    }  
    return hr;  
    ```  
  
 **도구 상자** 자체에 추가하는 것 이외에도 VSPackage는 **도구 상자** 데이터 공급자로 구성할 수 있으며 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE의 끌어서 놓기 지원을 확장하는 데 사용할 수 있습니다. 이를 통해 임의의 클립보드 형식을 **도구 상자** 및 편집기에 노출할 수 있습니다.  
  
#### VSPackage를 도구 상자 항목 공급자로 구성하려면  
  
1.  interop 기반 VSPackage를 **도구 상자** 항목 공급자로 등록합니다.  
  
     **도구 상자** 공급자로 등록하는 방법에 대한 자세한 내용은 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)을 참조하세요.  
  
2.  지원 사용자 지정 **도구 상자** 클립보드 형식으로 등록합니다.  
  
     모든 표준 **도구 상자** 클립보드 형식을 구현하지 않거나 사용자 지정 **도구 상자** 클립보드 형식을 지원하는 Interop 기반 VSPackage 지원 컨트롤은 다음을 수행해야 합니다.  
  
    1.  지원하는 도구 상자 클립보드 형식을 등록해야 합니다. 자세한 내용은 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)을 참조하십시오.  
  
    2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2> 인터페이스를 구현하는 클래스를 만들어야 합니다.  
  
        > [!NOTE]
        >  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2> 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> 인터페이스를 구현하는 동일한 클래스에서 구현되면 안 됩니다.  
  
    3.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider2> 인터페이스의 특정 구현은 동일한 메서드 인 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProviderRegistry.RegisterDataProvider%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox.RegisterDataProvider%2A> 중 하나를 통해 사용자 지정 데이터 형식에 대한 지원을 제공한다는 것을 도구 상자에 프로그래밍 방식으로 알립니다.  
  
         <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox.RegisterDataProvider%2A> 메서드 호출은 일반적으로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> 메서드의 구현 또는 VSPackage가 활성화될 때를 위한 <xref:Microsoft.VisualStudio.Shell.WindowPane.OnCreate%2A> 처리기 메서드에서 수행됩니다.  
  
        ```cpp  
        CComPtr<IVsToolboxDataProviderRegistry> pTB;  
        if (SUCCEEDED (hr = pServiceProvider->QueryService(SID_SVsToolboxDataProviderRegistry, IID_IVsToolboxDataProviderRegistry, (PVOID*)&pTB)) && pTB != NULL)  
        {  
            CustToolboxDataProvider* pDP = new CustToolboxDataProvider;  
            if (pDP)  
            {  
                pDP->AddRef();  
                VSCOOKIE dwDPCookie; //UNDONE: pass NULL instead of ptr to the cookie when RegisterDataProvider allows it.  
                pTB->RegisterDataProvider((IVsToolboxDataProvider*)pDP, &dwDPCookie);  
                pDP->Release();  
            }  
            else  
            {  
                hr = E_OUTOFMEMORY;  
            }  
        }  
        ```  
  
 표준 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **도구 상자** 클립보드 형식의 목록에 대해서는 [도구 상자 확장](../misc/extending-the-toolbox.md)를 참조하세요.  
  
## 참고 항목  
 [도구 상자 확장](../misc/extending-the-toolbox.md)   
 [도구 상자 연습](../misc/toolbox-walkthroughs.md)   
 [도구 상자 지원 기능 등록](../misc/registering-toolbox-support-features.md)   
 [고급 도구 상자 컨트롤 개발](../misc/advanced-toolbox-control-development.md)   
 [도구 상자 관리](../misc/managing-the-toolbox.md)   
 [How to: Control the Toolbox](../Topic/How%20to:%20Control%20the%20Toolbox.md)
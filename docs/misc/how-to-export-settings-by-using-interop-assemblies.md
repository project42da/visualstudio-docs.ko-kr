---
title: "방법: Interop 어셈블리를 사용하여 설정 내보내기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDE 설정, interop 어셈블리를 사용하여 내보내기"
  - "사용자 설정[Visual Studio SDK], interop 어셈블리를 사용하여 내보내기"
  - "IDE, interop 어셈블리를 사용하여 설정 내보내기"
ms.assetid: d470d4f9-3006-40c3-99db-21abcd5003b8
caps.latest.revision: 23
caps.handback.revision: 23
manager: "douge"
---
# 방법: Interop 어셈블리를 사용하여 설정 내보내기
VSPackage는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)에서 설정을 내보낼 수 있습니다. IDE에서는 VSPackage의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스 구현을 사용합니다. 패키지에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettingsQuery> 인터페이스도 제공하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettingsQuery> 인터페이스를 사용하여 VSPackage의 구성이 저장되는 방법을 결정합니다.  
  
> [!NOTE]
>  MPF\(관리되는 패키지 프레임워크\)에서는 Visual Studio 확장 생성을 돕는 일련의 관리 클래스를 제공합니다. MPF를 사용하여 이 작업을 수행하려면 [설정 내보내기](../misc/exporting-settings.md)를 참조하세요.  
  
### VSPackage에서 설정 내보내기를 구현하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 메커니즘에 대한 기본 지원을 구현합니다.  
  
    -   하나 이상의 사용자 지정 설정 지점을 정의하여 VSPackage에서 설정 메커니즘을 지원하도록 등록합니다.  
  
         자세한 내용은 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md)을 참조하세요.  
  
    -   VSPackage에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings>를 구현한다는 것을 선언합니다. 원하는 경우 VSPackage에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettingsQuery> 인터페이스를 구현할 수도 있습니다. 예:  
  
        ```  
        public class MyPackage : IVsPackage, IVsUserSettings, IVsUserSettingsQuery  
        ```  
  
    -   `IID_IVsUserSettings`를 사용하여 호출할 때 VSPackage의 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 메서드 구현은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스를 제공합니다.  
  
         `IID_IVsUserSettingsQuery` 인터페이스를 사용하여 호출할 때 필요에 따라 `QueryInterface`에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettingsQuery> 인터페이스를 제공할 수 있습니다.  
  
        ```  
        STDMETHODIMP MyPackage::QueryInterface(THIS_ REFIID riid, LPVOID FAR* ppvObj) { if (ppvObj == NULL) return E_POINTER; *ppvObj = NULL; if (riid == IID_IUnknown) *ppvObj = (LPVOID)(IUnknown *)(IClassFactory*)this; else if (riid == IID_IClassFactory) *ppvObj = (LPVOID)(IClassFactory *)this; else if (riid == IID_IVsPackage) *ppvObj = (LPVOID)(IVsPackage *)this; else if (riid == IID_IVsPersistSolutionOpts) *ppvObj = (LPVOID)(IVsPersistSolutionOpts *)this; else if (riid == IID_IVsPersistSolutionProps) *ppvObj = (LPVOID)(IVsPersistSolutionProps *)this; else if (riid == IID_IVsComponentSelectorProvider) *ppvObj = (LPVOID)(IVsComponentSelectorProvider *)this; else if (riid == IID_IVsUserSettings) *ppvObj = (LPVOID)(IVsUserSettings *)this; else if (riid == IID_IVsUserSettingsQuery) *ppvObj = (LPVOID)(IVsUserSettingsQuery *)this; if (*ppvObj) { AddRef(); return NOERROR; } return E_NOINTERFACE; }  
        ```  
  
2.  또는 IDE에 특정 설정을 내보내야 한다고 경고할 수도 있습니다.  
  
     VSPackage는 조건에 따라 사용자 지정 설정 지점 상태에서 정의하는 설정을 저장하도록 선택할 수 있습니다. 예를 들어 사용자가 저장할 설정을 명시적으로 지정한 경우에만 저장합니다.  
  
     이 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettingsQuery> 인터페이스를 구현해야 합니다.  
  
     VSPackage에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettingsQuery>를 구현하지 않는 경우 설정 내보내기 중 해당 상태 정보가 모두 저장됩니다.  
  
     VSPackage는 둘 이상의 사용자 지정 설정 지점\(설정 범주\)을 지원할 수 있습니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettingsQuery.NeedExport%2A> 메서드 구현에서는 제공된 사용자 지정 설정 지점의 GUID 또는 설정 범주 인수를 확인하여 특정 설정 그룹을 저장해야 하는지 결정합니다.  
  
     아래 예제에서 VSPackage는 항상 해당 명령 모음 상태가 저장되도록 요청하지만 해당 키 바인딩 상태는 플래그가 설정된 경우에만 저장되도록 요청합니다.  
  
3.  설정 파일에 설정 데이터를 씁니다.  
  
     설정 내보내기를 지원하려면 VSPackage에서 항상 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> 메서드를 구현해야 합니다.  
  
     구현에서는 IDE에서 전달한 인수, 해당 사용자 지정 설정 지점 범주의 GUID 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 인터페이스를 처리해야 합니다.  
  
    1.  VSPackage는 둘 이상의 사용자 지정 설정 지점\(설정 범주\)을 지원할 수 있습니다. 다음 예제에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> 메서드는 영구적 키 바인딩 상태가 아닌 영구적 명령 모음 상태에 대한 다른 구현을 호출합니다.  
  
    2.  VSPackage는 제공된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 인터페이스를 사용하여 데이터를 설정 파일에 저장해야 합니다.  
  
         `interface IVsSettingsWriter : IUnknown`  
  
         `{`  
  
         `HRESULT WriteSettingString( LPCOLESTR pszSettingName, LPCOLESTR pszSettingValue);`  
  
         `HRESULT WriteSettingLong( LPCOLESTR pszSettingName, long lSettingValue);`  
  
         `HRESULT WriteSettingBoolean( LPCOLESTR pszSettingName, BOOL fSettingValue);`  
  
         `HRESULT WriteSettingBytes( LPCOLESTR pszSettingName, BYTE *pSettingValue, long lDataLength);`  
  
         `HRESULT WriteSettingAttribute( LPCOLESTR pszSettingName, LPCOLESTR pszAttributeName, LPCOLESTR pszSettingValue);`  
  
         `HRESULT WriteSettingXml( IUnknown *pIXMLDOMNode);`  
  
         `HRESULT WriteSettingXmlFromString( LPCOLESTR szXML);`  
  
         `HRESULT ReportError( LPCOLESTR pszError, VSSETTINGSERRORTYPES dwErrorType);`  
  
         `};`  
  
         <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 인터페이스에 제공된 `pszSettingName` 인수의 값은 설정 범주 내에 저장된 각 데이터 요소를 고유하게 식별해야 합니다.  
  
        > [!NOTE]
        >  IDE는 해당 GUID 및 `pszSettingName` 값을 사용하여 저장된 각 설정을 식별하므로 이름이 사용자 지정 설정 지점 내에서 고유해야 합니다.`pszSettingName` 값이 동일한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsWriter> 메서드를 둘 이상 호출한 경우 설정 파일의 원래 값을 덮어씁니다.  
  
         설정 파일은 임의의 데이터 액세스를 지원합니다. 따라서 읽기 및 쓰기 설정 작업의 순서는 중요하지 않습니다.  
  
         이러한 내용은 아래 예제의 내보내기 및 가져오기 명령 모음 상태\(`ExportSettings_CommandBa`r 및 `ImportSettings_CommandBar`\)에 설명되어 있습니다.  
  
         구현에서 지원되는 4개 형식 중 하나로 데이터를 매핑할 수 있는 경우 쓸 수 있는 데이터 형식 또는 데이터의 양에는 제한이 없습니다.  
  
        > [!NOTE]
        >  API 설정에는 명시적으로 기록되고 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> 구현에 투명한 데이터 외에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전 정보도 저장됩니다. 저장된 설정은 설정 가져오기 중 이를 생성한 IDE 버전과 비교할 수 있습니다.  
  
## 예제  
 다음 예제에서는 설정 데이터를 가져오고 내보내는 방법을 보여 줍니다.  
  
```  
// -------------------------------------------------------------------------- //    IVsUserSettings methods used for configuration export. //    Delegate to the right shell object based on the category GUID. // -------------------------------------------------------------------------- static const WCHAR c_szFirstSettingName[] = L"FirstSettingName"; static const WCHAR c_szRandomTrashBytes[] = L"RandomTrashBytes"; static const WCHAR c_szRandomTrashLength[] = L"RandomTrashLength"; static const WCHAR c_szBreakPointWindow[] = L"Breakpoints Window"; // Export Settings. STDMETHOD(NeedExport)(WCHAR* pszCategoryGUID, BOOL *pfNeedExport) { if (!pfNeedExport) return E_INVALIDARG; CLSID clsidCategory; HRESULT hr= S_OK; hr = CLSIDFromString(pszCategoryGUID, &clsidCategory); IfFailGo(hr); if (GUID_Profiles_CommandBars == clsidCategory) { *pfNeedExport = TRUE; //Always export Command Bar Configuration }else if (GUID_Profiles_KeyBindings == clsidCategory) { *pfNeedExport = FALSE; //By Default don't export key bindings if (m_fMake_Permanent) *pfNeedExport = TRUE; //Export if user wants current configuration saved. }else{ hr = E_UNEXPECTED; } Error: return hr; } STDMETHOD(ExportSettings)(WCHAR *pszCategoryGUID, IVsSettingsWriter *pSettings) { CLSID clsidCategory; HRESULT hr; hr = CLSIDFromString(pszCategoryGUID, &clsidCategory); IfFailGo(hr); // Delegate to the right internal implementation based on // the requested category. if (GUID_Profiles_CommandBars == clsidCategory) { hr = ExportSettings_CommandBars(pSettings); }else if (GUID_Profiles_KeyBindings == clsidCategory) { hr = ExportSettings_KeyBindings(pSettings); }else{ hr = E_UNEXPECTED; } Error: return hr; }; HRESULT ExportSettings_CommandBars(IVsSettingsWriter *pSettings) { if (!pSettings) return E_INVALIDARG; hr = pSettings->WriteSettingString(c_szFirstSettingName, L"Value1"); IfFailGo(hr); int cRandomTrash = 12345; BYTE *pRandomTrash = (BYTE *)VSAlloc(cRandomTrash); if (pRandomTrash){ hr = pSettings->WriteSettingBytes(c_szRandomTrashBytes, pRandomTrash, cRandomTrash); IfFailGo(hr); hr = pSettings->WriteSettingLong(c_szRandomTrashLength, cRandomTrash); IfFailGo(hr); } Error: return hr; }; HRESULT ExportSettings_KeyBindings(IVsSettingsWriter *pSettings) { if (!pSettings) return E_INVALIDARG; hr = pSettings->WriteSettingString(c_szBreakPointWindow, L"Ctrl + Alt + B"); IfFailGo(hr); Error: return hr; }; STDMETHOD(ImportSettings)(WCHAR *pszCategoryGUID, IVsSettingsReader *pSettings, UserSettingsFlags flags, BOOL *pfRestartRequired) { CLSID clsidCategory; HRESULT hr; hr = CLSIDFromString(pszCategoryGUID, &clsidCategory); IfFailGo(hr); // Delegate to the right internal implementation based on // the requested category. if (GUID_Profiles_CommandBars == clsidCategory) { hr = ImportSettings_CommandBars(, pSettings, flags, pfRestartRequired); } else if (GUID_Profiles_KeyBindings == clsidCategory) { hr = ImportSettings_KeyBindings( pSettings, flags, pfRestartRequired); } else { hr = E_UNEXPECTED; } Error: return hr; }; // Import Settings. HRESULT ImportSettings_CommandBars(IVsSettingsReader *pSettings, UserSettingsFlags flags, BOOL *pfRestartRequired) { if (!pSettings) return E_INVALIDARG; if (pfRestartRequired) { *pfRestartRequired = FALSE; //Nobody should require a restart!! } CComBSTR bstrFirstSettingName; long lTrashLength = 0; BYTE *pTrashBytes = NULL; // Determines whether to treat import as an additive operation, or a reset all settings operation. BOOL fResetCompletely = FALSE; if (flags & USF_ResetOnImport) fResetCompletely = TRUE; hr = pSettings->ReadSettingString(c_szFirstSettingName, &bstrFirstSettingName); IfFailGo(hr); hr = pSettings->ReadSettingLong(c_szRandomTrashLength, &lTrashLength); IfFailGo(hr); if (lTrashLength > 0) { pTrashBytes = (BYTE*)VSAlloc(lTrashLength); IfNullMemGo(pTrashBytes); long lDataRead = 0; hr = pSettings->ReadSettingBytes(c_szRandomTrashLength, pTrashBytes, &lDataRead, lTrashLength); IfFailGo(hr); if (lDataRead != lTrashLength) { hr = E_UNEXPECTED; goto Error; } } // Note: before returning, these settings should immediately //             be applied to your personal settings store, //             whether in the registry or the file system. // This write-through cache methodology is essential to to work //             in multi-instance IDE scenarios. hr = UpdateState_CommandBar(bstrFirstSettingName,lTrashLength,pTrashBytes,lDataRead); Error: return hr; }; HRESULT ImportSettings_KeyBindings(IVsSettingsReader *pSettings, UserSettingsFlags flags, BOOL *pfRestartRequired) { if (!pSettings) return E_INVALIDARG; if (pfRestartRequired) { *pfRestartRequired = FALSE; //Nobody should require a restart!! } CComBSTR bstrBreakPointWindow; // Determines whether import can be treated as an additive // operation, or a reset all settings operation. BOOL fResetCompletely = FALSE; if (flags & USF_ResetOnImport) fResetCompletely = TRUE; hr = pSettings->ReadSettingString(c_szBreakPointWindow, &bstrBreakPointWindow); IfFailGo(hr); // Note: Before returning, these settings should immediately //             be applied to your personal settings //             store, whether in the registry or the file system. // This write-through cache methodology is essential to allow us //             to work in multi-instance IDE scenarios. hr = UpdateState_KeyBindings(bstrBreakPointWindow); Error: return hr; }  
```  
  
## 참고 항목  
 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md)   
 [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)   
 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [방법: Interop 어셈블리를 사용하여 설정 가져오기](../misc/how-to-use-interop-assemblies-to-import-settings.md)
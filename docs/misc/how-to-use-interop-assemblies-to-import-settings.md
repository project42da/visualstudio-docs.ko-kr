---
title: "방법: Interop 어셈블리를 사용하여 설정 가져오기 | Microsoft Docs"
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
  - "IDE 설정, interop 어셈블리를 사용하여 가져오기"
  - "IDE, interop 어셈블리를 사용하여 설정 가져오기"
  - "사용자 설정[Visual Studio SDK], interop 어셈블리를 사용하여 가져오기"
ms.assetid: 8a43dbe2-fdc0-471b-8235-3f489b77db0f
caps.latest.revision: 26
caps.handback.revision: 26
manager: "douge"
---
# 방법: Interop 어셈블리를 사용하여 설정 가져오기
VSPackage는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)에서 설정을 가져올 수 있습니다. IDE는 VSPackage의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스 구현을 사용하여 VSPackage 구성을 가져오는 방법을 결정합니다.  
  
> [!NOTE]
>  MPF\(관리되는 패키지 프레임워크\)에서는 Visual Studio 확장 생성을 돕는 일련의 관리 클래스를 제공합니다. MPF를 사용하여 이 작업을 수행하려면 [설정 가져오기](../misc/importing-settings.md)를 참조하세요.  
  
### VSPackage에서 설정 가져오기를 구현하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설정 메커니즘에 대한 기본 지원을 구현합니다.  
  
    -   하나 이상의 사용자 지정 설정 지점을 정의하여 VSPackage에서 설정 메커니즘을 지원하도록 등록합니다.  
  
         자세한 내용은 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md)을 참조하세요.  
  
    -   다음과 같이 VSPackage에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스를 구현하도록 선언합니다.  
  
        ```  
        public class MyPackage : IVsPackage, IVsUserSettings, IVsUserSettingsQuery  
        ```  
  
    -   `IID_IVsUserSettings`를 사용하여 호출할 때 VSPackage의 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 메서드 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스를 제공하는지 확인합니다. 예:  
  
        ```  
        STDMETHODIMP MyPackage::QueryInterface(THIS_ REFIID riid, LPVOID FAR* ppvObj) { if (ppvObj == NULL) return E_POINTER; *ppvObj = NULL; if (riid == IID_IUnknown) *ppvObj = (LPVOID)(IUnknown *)(IClassFactory*)this; else if (riid == IID_IClassFactory) *ppvObj = (LPVOID)(IClassFactory *)this; else if (riid == IID_IVsPackage) *ppvObj = (LPVOID)(IVsPackage *)this; else if (riid == IID_IVsPersistSolutionOpts) *ppvObj = (LPVOID)(IVsPersistSolutionOpts *)this; else if (riid == IID_IVsPersistSolutionProps) *ppvObj = (LPVOID)(IVsPersistSolutionProps *)this; else if (riid == IID_IVsComponentSelectorProvider) *ppvObj = (LPVOID)(IVsComponentSelectorProvider *)this; else if (riid == IID_IVsUserSettings) *ppvObj = (LPVOID)(IVsUserSettings *)this; else if (riid == IID_IVsUserSettingsQuery) *ppvObj = (LPVOID)(IVsUserSettingsQuery *)this; if (*ppvObj) { AddRef(); return NOERROR; } return E_NOINTERFACE; }  
        ```  
  
2.  설정 정보를 검색합니다.  
  
     설정 정보 검색을 지원하려면 VSPackage에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드를 구현해야 합니다.  
  
     데이터를 읽으려면 VSPackage의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> 인터페이스 구현에서 IDE에 의해 전달된 처음 두 개의 인수\(사용자 지정 설정 지점 범주의 GUID 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader> 인터페이스\)를 사용해야 합니다.  
  
    1.  VSPackage의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드 구현에서는 전달된 범주 GUID를 확인하고 상태 검색에 대한 올바른 메커니즘을 선택해야 합니다.  
  
         다음 예제에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드는 키 바인딩 상태 검색이 아닌 명령 모음 상태 검색에 대한 다른 구현을 호출합니다.  
  
    2.  VSPackage는 제공된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader> 인터페이스를 사용하여 데이터를 설정 파일로 가져와야 합니다.  
  
        > [!NOTE]
        >  설정 정보가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전의 함수로 변경된 경우 데이터를 읽어 IDE 버전을 검사하기 전에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드의 VSPackage 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader.ReadFileVersion%2A> 메서드를 사용해야 합니다.  
  
         인터페이스는 설정 파일에서 다양한 데이터 형식을 읽기 위한 메서드를 제공합니다.  
  
         `interface IVsSettingsReader : IUnknown`  
  
         `{`  
  
         `HRESULT ReadSettingString(WCHAR *pszSettingName, BSTR *pbstrSettingValue);`  
  
         `HRESULT ReadSettingLong(WCHAR *pszSettingName, long *plSettingValue);`  
  
         `HRESULT ReadSettingBoolean(WCHAR *pszSettingName, BOOL *pfSettingValue);`  
  
         `HRESULT ReadSettingAttribute(LPCOLESTR pszSettingName,LPCOLESTR pszAttributeName, BSTR *pbstrSettingValue);  //Internal use only`  
  
         `HRESULT ReadSettingBytes(WCHAR *pszSettingName, BYTE *pSettingValue, long *plDataLength, long lDataMax);`  
  
         `HRESULT ReadVersion(int *pnMajor, int *pnMinor, int *pnBuild);`  
  
         `HRESULT ReportError(WCHAR *pszError);`  
  
         `};`  
  
     설정 읽기 및 쓰기 작업의 순서는 중요하지 않으므로 설정 파일은 임의 데이터 액세스를 지원합니다.  
  
     이러한 내용은 아래 예제 구현의 명령 모음 상태 내보내기 및 가져오기\(`ExportSettings_CommandBa`r 및 `ImportSettings_CommandBar`\)에 설명되어 있습니다.  
  
3.  검색된 데이터의 유효성을 검사합니다.  
  
     설정 정보는 수동으로 편집할 수 있는 XML 파일에 포함되어 있습니다.  
  
> [!IMPORTANT]
>  설정 정보가 디스크에서 손상되거나, 버전 관련 설정이 포함되거나, 악의적인 공격의 수단으로 사용될 수 있습니다.<xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader> 메서드에서 반환된 각 데이터 항목의 유효성을 검사해야 합니다.  
  
-   가져온 설정을 생성하기 위해 사용된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 버전 지원 여부를 확인하려면 버전을 가져올 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader.ReadFileVersion%2A> 메서드를 호출합니다.  
  
-   VSPackage는 가져온 데이터 요소가 유효하지 않은 것을 IDE가 사용자에게 알리기 위해 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader.ReportError%2A> 메서드를 호출합니다.  
  
1.  설정 정보를 적용합니다.  
  
    1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드의 구현은 IDE에서 전달된 세 번째 인수의 값을 준수해야 합니다. 지원되는 값은 <xref:Microsoft.VisualStudio.Shell.Interop.__UserSettingsFlags> 열거형의 멤버입니다. 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.__UserSettingsFlags>을 참조하세요.  
  
         아래 예제에서는 명령 모음 설정 가져오기에 대한 구현\(`ImportSettings_Commandbar`\)에서 이 인수의 값을 사용하여 설정을 적용하는 데 기존 값을 덮어쓸지 또는 추가로 업데이트할지 여부를 결정합니다.  
  
    2.  가져온 설정을 적용할 때 동시 쓰기 캐시 방법을 구현해야 합니다.  
  
         레지스트리 또는 파일 시스템의 상태 정보는 IDE에 설정이 적용될 때 함께 업데이트되어야 합니다. 그렇게 해야 구성 일관성이 보장되고 다중 인스턴스 IDE 시나리오가 지원됩니다.  
  
2.  IDE에 설정 가져오기를 처리하는 방법을 알립니다.  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드의 반환된 `pfRestartRequired` 인수를 사용하여 가져온 설정을 적용하기 위해 다시 시작해야 하는지를 IDE에 알립니다.  
  
     <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> 메서드의 VSPackage 구현에서 `true`를 반환하는 경우 사용자에게 IDE를 다시 시작하라는 메시지가 표시됩니다.  
  
## 예제  
 이 예제에서는 설정 데이터를 가져오고 내보내는 방법을 보여 줍니다.  
  
```  
static const WCHAR c_szFirstSettingName[] = L"FirstSettingName"; static const WCHAR c_szRandomTrashBytes[] = L"RandomTrashBytes"; static const WCHAR c_szRandomTrashLength[] = L"RandomTrashLength"; static const WCHAR c_szBreakPointWindow[] = L"Breakpoints Window"; // -------------------------------------------------------------------------- //    IVsUserSettings methods used for configuration export and import //    Delegate to the right shell object based on the category GUID // -------------------------------------------------------------------------- static const WCHAR c_szFirstSettingName[] = L"FirstSettingName"; static const WCHAR c_szRandomTrashBytes[] = L"RandomTrashBytes"; static const WCHAR c_szRandomTrashLength[] = L"RandomTrashLength"; static const WCHAR c_szBreakPointWindow[] = L"Breakpoints Window"; // Export Settings. STDMETHOD(NeedExport)(WCHAR* pszCategoryGUID, BOOL *pfNeedExport) { if (!pfNeedExport) return E_INVALIDARG; CLSID clsidCategory; HRESULT hr= S_OK; hr = CLSIDFromString(pszCategoryGUID, &clsidCategory); IfFailGo(hr); if (GUID_Profiles_CommandBars == clsidCategory) { *pfNeedExport = TRUE; //Always export Command Bar Configuration }else if (GUID_Profiles_KeyBindings == clsidCategory) { *pfNeedExport = FALSE; //By Default don't export key bindings if (m_fMake_Permanent) *pfNeedExport = TRUE; //Export if user wants current configuration saved. }else{ hr = E_UNEXPECTED; } Error: return hr; } STDMETHOD(ExportSettings)(WCHAR *pszCategoryGUID, IVsSettingsWriter *pSettings) { CLSID clsidCategory; HRESULT hr; hr = CLSIDFromString(pszCategoryGUID, &clsidCategory); IfFailGo(hr); // Delegate to the right internal implementation based on the requested category. if (GUID_Profiles_CommandBars == clsidCategory) { hr = ExportSettings_CommandBars(pSettings); }else if (GUID_Profiles_KeyBindings == clsidCategory) { hr = ExportSettings_KeyBindings(pSettings); }else{ hr = E_UNEXPECTED; } Error: return hr; }; HRESULT ExportSettings_CommandBars(IVsSettingsWriter *pSettings) { if (!pSettings) return E_INVALIDARG; hr = pSettings->WriteSettingString(c_szFirstSettingName, L"Value1"); IfFailGo(hr); int cRandomTrash = 12345; BYTE *pRandomTrash = (BYTE *)VSAlloc(cRandomTrash); if (pRandomTrash){ hr = pSettings->WriteSettingBytes(c_szRandomTrashBytes, pRandomTrash, cRandomTrash); IfFailGo(hr); hr = pSettings->WriteSettingLong(c_szRandomTrashLength, cRandomTrash); IfFailGo(hr); } Error: return hr; }; HRESULT ExportSettings_KeyBindings(IVsSettingsWriter *pSettings) { if (!pSettings) return E_INVALIDARG; hr = pSettings->WriteSettingString(c_szBreakPointWindow, L"Ctrl + Alt + B"); IfFailGo(hr); Error: return hr; }; STDMETHOD(ImportSettings)(WCHAR *pszCategoryGUID, IVsSettingsReader *pSettings, UserSettingsFlags flags, BOOL *pfRestartRequired) { CLSID clsidCategory; HRESULT hr; hr = CLSIDFromString(pszCategoryGUID, &clsidCategory); IfFailGo(hr); // Delegate to the right internal implementation based on the requested category. if (GUID_Profiles_CommandBars == clsidCategory) { hr = ImportSettings_CommandBars(, pSettings, flags, pfRestartRequired); } else if (GUID_Profiles_KeyBindings == clsidCategory) { hr = ImportSettings_KeyBindings( pSettings, flags, pfRestartRequired); } else { hr = E_UNEXPECTED; } Error: return hr; }; // Import Settings. HRESULT ImportSettings_CommandBars(IVsSettingsReader *pSettings, UserSettingsFlags flags, BOOL *pfRestartRequired) { if (!pSettings) return E_INVALIDARG; if (pfRestartRequired) { *pfRestartRequired = FALSE; //Nobody should require a restart!! } CComBSTR bstrFirstSettingName; long lTrashLength = 0; BYTE *pTrashBytes = NULL; // Determines whether to import as an additive operation, or a reset all settings operation. BOOL fResetCompletely = FALSE; if (flags & USF_ResetOnImport) fResetCompletely = TRUE; hr = pSettings->ReadSettingString(c_szFirstSettingName, &bstrFirstSettingName); IfFailGo(hr); hr = pSettings->ReadSettingLong(c_szRandomTrashLength, &lTrashLength); IfFailGo(hr); if (lTrashLength > 0) { pTrashBytes = (BYTE*)VSAlloc(lTrashLength); IfNullMemGo(pTrashBytes); long lDataRead = 0; hr = pSettings->ReadSettingBytes(c_szRandomTrashLength, pTrashBytes, &lDataRead, lTrashLength); IfFailGo(hr); if (lDataRead != lTrashLength) { hr = E_UNEXPECTED; goto Error; } } // Note: before returning these settings should immediately be applied to your personal //            settings store, whether in the registry or the file system. // This write-thru cache methodology is essential to work in multi-instance IDE scenarios. hr = UpdateState_CommandBar(bstrFirstSettingName,lTrashLength,pTrashBytes,lDataRead); Error: return hr; }; HRESULT ImportSettings_KeyBindings(IVsSettingsReader *pSettings, UserSettingsFlags flags, BOOL *pfRestartRequired) { if (!pSettings) return E_INVALIDARG; if (pfRestartRequired) { *pfRestartRequired = FALSE; //Nobody should require a restart!! } CComBSTR bstrBreakPointWindow; // Determines whether to import as an additive operation or a reset all settings operation. BOOL fResetCompletely = FALSE; if (flags & USF_ResetOnImport) fResetCompletely = TRUE; hr = pSettings->ReadSettingString(c_szBreakPointWindow, &bstrBreakPointWindow); IfFailGo(hr); // Note: before returning these settings should immediately be applied to your personal //            settings store, whether in the registry or the file system. // This write-thru cache methodology is essential to work in multi-instance IDE scenarios. hr = UpdateState_KeyBindings(bstrBreakPointWindow); Error: return hr; }  
```  
  
## 참고 항목  
 [방법: Interop 어셈블리를 사용하여 설정 내보내기](../misc/how-to-export-settings-by-using-interop-assemblies.md)   
 [사용자 설정에 대 한 지원](../extensibility/internals/support-for-user-settings.md)   
 [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)   
 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)
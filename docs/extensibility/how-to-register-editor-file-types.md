---
title: "방법: 편집기 파일 형식을 등록 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-파일 형식을 등록합니다."
ms.assetid: 54846779-8290-48de-90ab-81011559d9a5
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 편집기 파일 형식을 등록 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

등록의 일부로 서 제공 된 특성을 사용 하 여 파일 형식 편집기를 등록 하는 가장 쉬운 방법은 되는 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 관리 패키지 \(MPF\) 프레임 워크 클래스입니다.  기본 패키지를 구현 하는 경우 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)], 편집기와 연결 된 확장을 등록 하는 레지스트리 스크립트를 작성할 수도 있습니다.  
  
## MPF 클래스를 사용 하 여 등록  
  
#### MPF 클래스를 사용 하 여 편집기 파일 형식을 등록 하려면  
  
1.  제공은 <xref:Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute> 클래스를 편집기를 VSPackage 클래스에 대 한 적절 한 매개 변수를 사용 합니다.  
  
    ```  
    [Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute(typeof(EditorFactory), ".Sample", 32,   
         ProjectGuid = "{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3}",   
         TemplateDir = "..\\..\\Templates",   
         NameResourceID = 106)]  
    ```  
  
     여기서 ".샘플"등록 된이 편집기에 대 한 확장명입니다 및"32"우선 순위 수준입니다.  
  
     `projectGuid` 에 정의 된 기타 파일 형식에 대 한 guid와 <xref:Microsoft.VisualStudio.VSConstants.CLSID_MiscellaneousFilesProject>.  결과 파일은 빌드 프로세스의 일부로 될 것입니다 수 있도록 기타 파일 형식이 제공 됩니다.  
  
     `TemplateDir`관리 되는 기본 편집기 샘플에 포함 된 템플릿 파일을 포함 하는 폴더를 나타냅니다.  
  
     `NameResourceID`BasicEditorUI 프로젝트의 Resources.h 파일에 정의 하 고 편집기 "내 편집기"로 식별 합니다.  
  
2.  <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드를 재정의합니다.  
  
     구현에는 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드, 호출을 <xref:Microsoft.VisualStudio.Shell.Package.RegisterEditorFactory%2A> 메서드 및 가공 공장으로 편집기의 인스턴스를 보여 주는 아래.  
  
    ```  
    protected override void Initialize()  
    {  
        Trace.WriteLine (string.Format(CultureInfo.CurrentCulture,   
        "Entering Initialize() of: {0}", this.ToString()));  
        base.Initialize();  
           //Create Editor Factory  
        editorFactory = new EditorFactory(this);  
        base.RegisterEditorFactory(editorFactory);  
    }  
    ```  
  
     이 이렇게 편집기 팩터리와 편집기 파일 확장명을 등록합니다.  
  
3.  편집기 팩터리를 등록 취소 합니다.  
  
     편집기 팩터리 있는 VSPackage 삭제 될 때 자동으로 등록 하지 않습니다.  편집기 팩터리 개체를 구현 하는 경우는 <xref:System.IDisposable> 인터페이스의 `Dispose` 메서드 호출로 공장 등록 취소 했습니다 후 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## 레지스트리 스크립트를 사용 하 여 등록  
 편집기 팩터리 및 파일 형식에 대 한 기본 등록 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 수행 됩니다 windows 레지스트리에 쓰려고 하 여 다음 그림과 같이 레지스트리 스크립트를 사용 합니다.  
  
#### 레지스트리 스크립트를 사용 하 여 편집기 파일 형식을 등록 하려면  
  
1.  레지스트리 스크립트 편집기 팩터리와 GUID 문자열 편집기 팩터리와 같이 정의 `GUID_BscEditorFactory` 섹션에 다음과 같은 레지스트리 스크립트입니다.  또한, 확장 및 편집기 확장의 우선 순위를 정의 합니다.  
  
    ```  
  
                NoRemove Editors     {         %GUID_BscEditorFactory% = s 'RTF Editor'         {             val Package = s '%CLSID_Package%'             val DisplayName = s 'An RTF Editor'             val ExcludeDefTextEditor = d 1             val AcceptBinaryFiles = d 0  
  
            LogicalViews  
            {  
                val %LOGVIEWID_TextView% = s ''  
            }  
  
            OpenWithEntries  
            {  
            }  
  
            Extensions             {                 val rtf = d 50             }  
        }  
    }  
    ```  
  
     이 예제에서 편집기 파일 확장명 ".rtf"로 식별 되 고 우선 순위를 "50"입니다.  GUID 문자열은 BscEdit 예제 프로젝트의 Resource.h 파일에 정의 됩니다.  
  
2.  있는 Vspackage를 등록 합니다.  
  
3.  편집기 팩터리를 등록 합니다.  
  
     편집기 팩터리 등록 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors.RegisterEditor%2A> 구현 합니다.  
  
    ```  
    // create editor factory.  
    if (m_srpEdFact == NULL)   
    {  
        CComObject<CBscEditorFactory> *pEdFact = new CComObject<CBscEditorFactory>;  
        if (NULL == pEdFact)  
          return E_OUTOFMEMORY;  
  
        if (!pEdFact->FInit(this))  
          return E_UNEXPECTED;  
  
        m_srpEdFact = (IVsEditorFactory *) pEdFact;    // Note: assignment to a smart pointer does an AddRef()  
    }  
    // Query service for IVsRegisterEditors, register the editor factory  
    CComPtr<IVsRegisterEditors> srpRegEd;  
    if ((SUCCEEDED(m_srpPkgSiteSP->QueryService(SID_SVsRegisterEditors, IID_IVsRegisterEditors,(void **)&srpRegEd ))) && (srpRegEd != NULL))  
      {  
        ATLTRACE(TEXT(">> CVsPackage, registering editor factory.\n"));  
          if (FAILED(srpRegEd->RegisterEditor(GUID_BscEditorFactory,  
                      m_srpEdFact, &m_dwEditorCookie)))   
          {  
             ATLTRACE(TEXT(">> CVsPackage, RegisterEditor() failed.\n"));  
            return E_FAIL;  
          }  
      }  
        return S_OK;  
    }  
    ```  
  
     GUID 문자열 BscEdit 프로젝트의 Resource.h 파일에 정의 됩니다.
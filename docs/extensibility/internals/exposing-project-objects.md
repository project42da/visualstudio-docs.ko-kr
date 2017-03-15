---
title: "프로젝트 개체 노출 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "노출 하는 프로젝트 개체"
  - "확장성, 프로젝트 개체"
ms.assetid: 5bb24967-434a-4ef4-87a0-2f3250c9e22d
caps.latest.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 17
---
# 프로젝트 개체 노출
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자 지정 프로젝트 형식은 자동화 인터페이스를 사용 하 여 프로젝트에 대 한 액세스를 허용 하기 위해 자동화 개체를 제공할 수 있습니다. 모든 프로젝트 형식은 표준 제공할 예정입니다 <xref:EnvDTE.Project> 에서 액세스할 수 있는 자동화 개체 <xref:EnvDTE.Solution>, 는 IDE에 열려 있는 모든 프로젝트 컬렉션을 포함 합니다. 프로젝트의 각 항목을 표시 해야 예상 되는 <xref:EnvDTE.ProjectItem> 개체를 사용 하 여 액세스 <xref:Project.ProjectItems>합니다. 이러한 표준 자동화 개체 외에도 프로젝트 프로젝트 관련 자동화 개체를 제공 하도록 선택할 수 있습니다.  
  
 개체를 만들려면 사용자 지정 루트 수준의 자동화 액세스할 수 있는 사용 하 여 루트 DTE 개체에서 런타임에 바인딩 `DTE.<customeObjectName>` 또는 `DTE.GetObject(“<customObjectName>”)`합니다. 예를 들어, Visual c \+ \+ DTE를 사용 하 여 액세스할 수 있는 "VCProjects"를 호출 하는 c \+ \+ 프로젝트에 특정 프로젝트 컬렉션을 만듭니다. VCProjects 또는 DTE 합니다. GetObject\("VCProjects"\) 합니다. 또한 ProjectItem.Object와는 ProjectItem.FileCodeModel 표시 하는 프로젝트 항목의 가장 많이 파생 된 개체에 대 한 쿼리 될 수 있는 한 Project.CodeModel 프로젝트 형식에 대해 고유한 Project.Object를 만들 수 있습니다.  
  
 사용자 지정, 프로젝트 관련 프로젝트 컬렉션을 노출 하는 프로젝트에 대 한 일반적인 규칙은 예를 들어 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] c \+ \+ 특정 프로젝트 컬렉션을 사용 하 여 액세스할 수 있습니다 만듭니다 `DTE.VCProjects` 또는 `DTE.GetObject("VCProjects")`합니다. 만들 수도 있습니다는 `Project.Object`, 프로젝트 형식에 대 한 고유한는 `Project.CodeModel`, 해당 가장 많이 파생 된 개체에 대해 쿼리할 수 있습니다는 `ProjectItem`, 를 노출 하 `ProjectItem.Object`, 및 `ProjectItem.FileCodeModel`합니다.  
  
### 프로젝트에 대 한 VSPackage 관련 개체를 기여 합니다.  
  
1.  VSPackage의.pkgdef 파일에 적절 한 키를 추가 합니다.  
  
     예를 들어 다음은 c \+ \+ 언어 프로젝트에 대 한.pkgdef 설정입니다.  
  
    ```  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\Automation] "VCProjects"="" [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\AutomationEvents] "VCProjectEngineEventsObject"=""  
    ```  
  
2.  코드를 구현할는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 메서드를 다음 예제와 같이 합니다.  
  
    ```cpp  
    STDMETHODIMP CVsPackage::GetAutomationObject( /* [in]  */ LPCOLESTR       pszPropName, /* [out] */ IDispatch **    ppIDispatch) { ExpectedPtrRet(pszPropName); ExpectedPtrRet(ppIDispatch); *ppIDispatch = NULL; if (m_fZombie) return E_UNEXPECTED; if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0) { return GetAutomationProjects(ppIDispatch); } else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0) { return CAutomationEvents::GetAutomationEvents(ppIDispatch); } else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0) { return CAutomationEvents::GetAutomationEvents(ppIDispatch); } return E_INVALIDARG; }   
    ```  
  
     코드에서 `g_wszAutomationProjects` 프로젝트 컬렉션의 이름입니다.`GetAutomationProjects` 메서드를 구현 하는 개체를 만듭니다는 `Projects` 인터페이스와 반환은 `IDispatch` 다음 코드 예제에 나온 것 처럼 호출 개체에 대 한 포인터입니다.  
  
    ```cpp  
    HRESULT CVsPackage::GetAutomationProjects(/* [out] */ IDispatch ** ppIDispatch) { ExpectedPtrRet(ppIDispatch); *ppIDispatch = NULL; if (!m_srpAutomationProjects) { HRESULT hr = CACProjects::CreateInstance(&m_srpAutomationProjects); IfFailRet(hr); ExpectedExprRet(m_srpAutomationProjects != NULL); } return m_srpAutomationProjects.CopyTo(ppIDispatch); }  
    ```  
  
     자동화 개체에 대 한 고유한 이름을 선택 해야 합니다. 이름 충돌 예측 가능 하지 않으며 충돌로 발생할 임의로 발생 여러 프로젝트 형식에 동일한 이름을 사용 하는 경우에 충돌 하는 개체 이름. 회사 이름 또는 몇 가지 독특한 점은 자동화 개체의 이름으로 해당 제품 이름을 포함 해야 합니다.  
  
     사용자 지정 `Projects` 컬렉션 개체는 프로젝트 자동화 모델의 나머지 부분에 대 한 편의 시작 지점입니다. 프로젝트 개체에서 액세스할 수 있는 이기도 <xref:EnvDTE.Solution> 프로젝트 컬렉션입니다. 소비자를 제공 하는 적절 한 코드 및 레지스트리 항목을 만든 후 `Projects` 개체 컬렉션, 프로젝트 모델에 대 한 표준 개체 남은 구현을 제공 해야 합니다. 자세한 내용은 [모델링 프로젝트](../../extensibility/internals/project-modeling.md)을 참조하세요.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>
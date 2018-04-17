---
title: 프로젝트 개체를 노출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project objects, exposing
- extensibility, project objects
ms.assetid: 5bb24967-434a-4ef4-87a0-2f3250c9e22d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4eaa2a5e8c5c153698069084b9f0cfe406cad7db
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="exposing-project-objects"></a>프로젝트 개체 노출
사용자 지정 프로젝트 형식을 자동화 인터페이스를 사용 하 여 프로젝트에 대 한 액세스를 허용 하기 위해 자동화 개체를 제공할 수 있습니다. 모든 프로젝트 형식을 표준 제공 될 <xref:EnvDTE.Project> 에서 액세스 되는 자동화 개체 <xref:EnvDTE.Solution>, IDE에서 열려 있는 모든 프로젝트의 컬렉션이 들어 있는입니다. 프로젝트의 각 항목을 표시 해야 사용할 수는 <xref:EnvDTE.ProjectItem> 개체를 사용 하 여 액세스할 `Project.ProjectItems`합니다. 이러한 표준 자동화 개체 외에도 프로젝트 프로젝트 관련 자동화 개체를 제공 하도록 선택할 수 있습니다.  
  
 개체를 만들려면 사용자 지정 루트 수준의 자동화 액세스할 수 있는 사용 하 여 루트 DTE 개체에서 런타임에 바인딩 `DTE.<customeObjectName>` 또는 `DTE.GetObject("<customObjectName>")`합니다. 예를 들어, Visual c + + DTE를 사용 하 여 액세스할 수 있는 "VCProjects"를 호출 하는 c + + 프로젝트 관련 프로젝트 컬렉션을 만듭니다. VCProjects 또는 DTE 합니다. GetObject("VCProjects") 합니다. Project.CodeModel ProjectItem.Object 및는 ProjectItem.FileCodeModel 노출 ProjectItem, 가장 많이 파생 된 개체에 대 한 쿼리 가능한 프로젝트 형식에 대 한 고유한는 Project.Object를 만들 수 있습니다.  
  
 사용자 지정, 프로젝트 관련 프로젝트 컬렉션을 노출 하는 프로젝트에 대 한 일반적인 변환 합니다. 예를 들어 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] c + +의 특정 프로젝트 컬렉션을 사용 하 여 액세스할 수 있습니다 만듭니다 `DTE.VCProjects` 또는 `DTE.GetObject("VCProjects")`합니다. 만들 수도 있습니다는 `Project.Object`, 하는 프로젝트 형식에 대 한 고유는 `Project.CodeModel`, 가장 많이 파생 된 개체에 대해 쿼리할 수 있습니다는 `ProjectItem`를 노출 하 `ProjectItem.Object`, 및 `ProjectItem.FileCodeModel`합니다.  
  
### <a name="to-contribute-a-vspackage-specific-object-for-a-project"></a>프로젝트에 대 한 VSPackage 관련 개체 작업에 기여  
  
1.  VSPackage의.pkgdef 파일에 적절 한 키를 추가 합니다.  
  
     예를 들어 다음은 c + + 언어 프로젝트에 대 한.pkgdef 설정입니다.  
  
    ```  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\Automation]  
    "VCProjects"=""  
    [$RootKey$\Packages\{F1C25864-3097-11D2-A5C5-00C04F7968B4}\AutomationEvents]  
    "VCProjectEngineEventsObject"=""  
    ```  
  
2.  코드를 구현는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> 다음 예제와 같이 메서드를 합니다.  
  
    ```cpp  
    STDMETHODIMP CVsPackage::GetAutomationObject(  
    /* [in]  */ LPCOLESTR       pszPropName,   
    /* [out] */ IDispatch **    ppIDispatch)  
    {  
    ExpectedPtrRet(pszPropName);  
    ExpectedPtrRet(ppIDispatch);  
    *ppIDispatch = NULL;  
  
        if (m_fZombie)  
            return E_UNEXPECTED;  
  
        if (_wcsicmp(pszPropName, g_wszAutomationProjects) == 0)  
        {  
            return GetAutomationProjects(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        else if (_wcsicmp(pszPropName, g_wszAutomationProjectItemsEvents) == 0)  
        {  
            return CAutomationEvents::GetAutomationEvents(ppIDispatch);  
        }  
        return E_INVALIDARG;  
    }   
    ```  
  
     코드에서 `g_wszAutomationProjects` 프로젝트 컬렉션의 이름입니다. `GetAutomationProjects` 메서드 구현 하는 개체를 만듭니다.는 `Projects` 인터페이스와 반환은 `IDispatch` 다음 코드 예제에서와 같이 호출 개체에 대 한 포인터입니다.  
  
    ```cpp  
    HRESULT CVsPackage::GetAutomationProjects(/* [out] */ IDispatch ** ppIDispatch)  
    {  
        ExpectedPtrRet(ppIDispatch);  
        *ppIDispatch = NULL;  
  
        if (!m_srpAutomationProjects)  
        {  
            HRESULT hr = CACProjects::CreateInstance(&m_srpAutomationProjects);  
            IfFailRet(hr);  
            ExpectedExprRet(m_srpAutomationProjects != NULL);  
        }  
        return m_srpAutomationProjects.CopyTo(ppIDispatch);  
    }  
    ```  
  
     자동화 개체에 대 한 고유한 이름을 선택 해야 합니다. 이름 충돌 예측 가능 하지 않으며 충돌로 발생할를 여러 프로젝트 형식에 동일한 이름을 사용 하는 경우 임의로 throw 충돌 하는 개체 이름입니다. 회사 이름 또는 자동화 개체의 이름에 제품 이름의 몇 가지 고유한 측면을 포함 해야 합니다.  
  
     사용자 지정 `Projects` 컬렉션 개체는 프로젝트 자동화 모델의 나머지 부분에 대 한 편의 시작 지점입니다. 프로젝트 개체에서 액세스할 수 있는 이기도 <xref:EnvDTE.Solution> 프로젝트 컬렉션입니다. 소비자를 제공 하는 적절 한 코드 및 레지스트리 항목을 만든 후 `Projects` 컬렉션 개체를 표준 개체 프로젝트 모델에 대 한 남은 구현을 제공 해야 합니다. 자세한 내용은 참조 [프로젝트 모델링](../../extensibility/internals/project-modeling.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A>
---
title: "프로젝트 하위 초기화 시퀀스 | Microsoft Docs"
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
  - "하위 프로젝트 초기화 시퀀스"
ms.assetid: f657f8c3-5e68-4308-9971-e81e3099ba29
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 하위 초기화 시퀀스
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기본 프로젝트 공장 구현을 호출 하 여 환경 프로젝트를 생성 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>.  환경 프로젝트 파일 확장명을 프로젝트 형식 GUID 목록 비어 있지 않은지 확인 하는 경우 하위 프로젝트의 구조를 시작 합니다.  프로젝트 인지 프로젝트 파일 확장명과 프로젝트 GUID 지정은 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 형식.  예를 들어,.vbproj 확장 {F184B08F\-C81C\-45F6\-A57F\-5ABD9991F28F}이 식별 하는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트.  
  
## 하위 프로젝트의 환경 초기화  
 다음은 프로젝트 시스템에서 다중 프로젝트 하위 집계에 대 한 초기화 시퀀스를 자세히 설명 합니다.  
  
1.  기본 프로젝트의 환경 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>, 및 프로젝트의 프로젝트 파일을 구문 분석 하는 동안 Guid 목록 집계 프로젝트 형식이 아님을 발견 `null`.  직접 그 프로젝트를 만들고 프로젝트 중단 됩니다.  
  
2.  프로젝트 통화 `QueryService` 에서 <xref:Microsoft.VisualStudio.Shell.Interop.SVsCreateAggregateProject> 의 환경 구현을 사용 하 여 하위 프로젝트를 만들려면 서비스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> 메서드.  이 메서드 내에서 환경 재귀 함수 호출을 구현 중에 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A>, `M:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject(System.Object)` 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A> 프로젝트의 목록을 따라 이동 되는 동안 방법을 가장 바깥쪽 프로젝트 하위 형식으로 시작 하는 Guid를 입력 합니다.  
  
     다음 초기화 단계에 자세히 설명 합니다.  
  
    1.  환경 구현에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> 메서드 호출 `HrCreateInnerProj```메서드를 다음 함수 선언 사용:  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
         때이 함수가 호출 처음으로, 즉 가장 바깥쪽 프로젝트 하위 형식에 대 한 매개 변수 `pOuter` 및 `pOwner` 로 전달 된 `null` 함수는 가장 바깥쪽 프로젝트 하위 형식을 설정 하 고 `IUnknown` 에 `pOuter`.  
  
    2.  그런 다음 환경 호출 `HrCreateInnerProj` 함수를 목록에서 두 번째 프로젝트 형식 GUID 사용 합니다.  이 GUID 집계 시퀀스에서 기본 프로젝트를 향한 단계별 실행 두 번째 내부 프로젝트 하위 형식에 해당 합니다.  
  
    3.  `pOuter` 이제 가리키는 `IUnknown` 가장 바깥쪽 프로젝트 하위 유형의 및 `HrCreateInnerProj` 의 구현을 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> 의 구현에 대 한 호출 다음에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A>.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> 메서드에 전달 제어에 `IUnknown` 의 가장 바깥쪽 프로젝트 하위 `pOuter`.  소유 프로젝트 \(내부 프로젝트 하위 형식\) 여기는 집계 프로젝트 개체를 만드는 데 필요 합니다.  에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A> 의 포인터를 전달 하면 메서드 구현에 `IUnknown` 집계 중인 내부 프로젝트의.  이 두 메서드는 집계 개체를 만드는 및 구현 프로젝트 하위 참조 수가 자신을 걸어 종료 되지 않도록 하려면 COM 집계 규칙을 준수 해야 합니다.  
  
    4.  `HrCreateInnerProj`구현을 호출 합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A>.  이 방법에서는 프로젝트 하위 형식 초기화 작업을 수행합니다.  예를 들어, 솔루션 이벤트에 등록할 수, <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A>.  
  
    5.  `HrCreateInnerProj`목록에 있는 마지막 GUID \(기본 프로젝트\)에 도달할 때까지 재귀적으로 호출 됩니다.  각 이러한 호출에 대 한 d\-c 단계를 반복 합니다.  `pOuter`가장 바깥쪽 프로젝트 하위 형식으로 가리키는 `IUnknown` 각 수준에 집계 합니다.  
  
 다음 예제에서는 프로그래밍 방식으로 프로세스의 대략적인 표현 정보를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> 메서드는 환경에 의해 구현 됩니다.  코드는 예일 뿐입니다. 컴파일할 수는 없습니다 및 쉽게 구별할 수 있도록 모든 오류 검사 제거 되었습니다.  
  
## 예제  
  
### 코드  
  
```  
HRESULT CreateAggregateProject  
(  
    LPCOLESTR lpstrGuids,   
    LPCOLESTR pszFilename,   
    LPCOLESTR pszLocation,  
    LPCOLESTR pszName,   
    VSCREATEPROJFLAGS grfCreateFlags,   
    REFIID iidProject,   
    void **ppvProject)  
{  
    HRESULT hr = NOERROR;  
    CComPtr<IUnknown> srpunkProj;  
    CComPtr<IVsAggregatableProject> srpAggProject;  
    CComBSTR bstrGuids = lpstrGuids;  
    BOOL fCanceled = FALSE;  
    *ppvProject = NULL;  
  
    HrCreateInnerProj(  
         bstrGuids, NULL, NULL, pszFilename, pszLocation,   
         pszName, grfCreateFlags, &srpunkProj, &fCanceled);  
    srpunkProj->QueryInterface(  
        IID_IVsAggregatableProject, (void **)&srpAggProject));  
    srpAggProject->OnAggregationComplete();  
    srpunkProj->QueryInterface(iidProject, ppvProject);  
}  
  
HRESULT HrCreateInnerProj  
(  
    WCHAR *pwszGuids,   
    IUnknown *pOuter,   
    IVsAggregatableProject *pOwner,   
    LPCOLESTR pszFilename,   
    LPCOLESTR pszLocation,  
    LPCOLESTR pszName,   
    VSCREATEPROJFLAGS grfCreateFlags,   
    IUnknown **ppInner,   
    BOOL *pfCanceled  
)  
{  
    HRESULT hr = NOERROR;  
    CComPtr<IUnknown> srpInner;  
    CComPtr<IVsAggregatableProject> srpAggInner;  
    CComPtr<IVsProjectFactory> srpProjectFactory;  
    CComPtr<IVsAggregatableProjectFactory> srpAggPF;  
    GUID guid = GUID_NULL;  
    WCHAR *pwszNextGuids = wcschr(pwszGuids, L';');  
    WCHAR wszText[_MAX_PATH+150] = L"";  
  
    if (pwszNextGuids)  
    {  
        *pwszNextGuids++ = 0;  
    }  
  
    CLSIDFromString(pwszGuids, &guid);  
    GetProjectTypeMgr()->HrGetProjectFactoryOfGuid(  
        guid, &srpProjectFactory);  
    srpProjectFactory->QueryInterface(  
        IID_IVsAggregatableProjectFactory,   
        (void **)&srpAggPF);  
    srpAggPF->PreCreateForOuter(pOuter, &srpInner);  
    srpInner->QueryInterface(  
        IID_IVsAggregatableProject, (void **)&srpAggInner);  
  
    if (pOwner)  
    {  
        IfFailGo(pOwner->SetInnerProject(srpInner));  
    }  
  
    if (pwszNextGuids)  
    {  
        CComPtr<IUnknown> srpNextInner;  
        HrCreateInnerProj(  
            pwszNextGuids, pOuter ? pOuter : srpInner,   
            srpAggInner, pszFilename, pszLocation, pszName,   
            grfCreateFlags, &srpNextInner, pfCanceled);  
    }  
  
    return srpAggInner->InitializeForOuter(  
        pszFilename, pszLocation, pszName, grfCreateFlags,   
        IID_IUnknown, (void **)ppInner, pfCanceled);  
}  
```  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Flavor>   
 [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)
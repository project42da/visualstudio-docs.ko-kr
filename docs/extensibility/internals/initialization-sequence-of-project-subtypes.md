---
title: 프로젝트 하위 형식의 초기화 순서 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project subtypes, initialization sequence
ms.assetid: f657f8c3-5e68-4308-9971-e81e3099ba29
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fe7e7a574d04ec9a49252e32e0fbb8b5685778aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="initialization-sequence-of-project-subtypes"></a>프로젝트 하위 형식의 초기화 순서
기본 프로젝트 팩터리 구현을 호출 하 여 프로젝트를 생성 하는 환경 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>합니다. 프로젝트 파일의 확장에 대 한 프로젝트 형식 GUID 목록 비어 있지는 환경에 따라 결정 프로젝트 하위 형식 생성이 시작 됩니다. 프로젝트 파일 확장명과 프로젝트 GUID 프로젝트 인지 지정는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 유형입니다. 예를 들어.vbproj 확장 및 식별 하는 {F184B08F-C81C-45F6-A57F-5ABD9991F28F}는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트.

## <a name="environments-initialization-of-project-subtypes"></a>환경의 프로젝트 하위 형식 초기화
 다음 절차에는 여러 프로젝트 하위 형식에서 집계 프로젝트 시스템에 대 한 초기화 시퀀스 자세히 설명 합니다.

1.  환경 기본 프로젝트의 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory.CreateProject%2A>, 및을 프로젝트의 프로젝트 파일의 구문 분석 하는 동안 집계 프로젝트 형식이 Guid 목록 아닌지 검색 `null`합니다. 프로젝트의 프로젝트를 직접 만드는 것을 중단 합니다.

2.  프로젝트를 호출 하 여 `QueryService` 에 <xref:Microsoft.VisualStudio.Shell.Interop.SVsCreateAggregateProject> 의 환경의 구현을 사용 하 여 프로젝트 하위 유형을 만들 서비스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> 메서드. 이 메서드 내에서 환경에서는 사용자 구현에 대 한 재귀 함수 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A> 메서드 프로젝트 목록이 순환 되는 동안 가장 바깥쪽 프로젝트 하위 형식으로 시작 하는 Guid를 입력 합니다.

     다음 초기화 단계에 설명 합니다.

    1.  환경의 구현의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> 메서드 호출에서 `HrCreateInnerProj` 다음 함수 선언 된 메서드:

         <CodeContentPlaceHolder>0</CodeContentPlaceHolder>

         이 함수가 호출 될 때 처음으로, 즉 가장 바깥쪽 프로젝트 하위 형식에 대 한 매개 변수 `pOuter` 및 `pOwner` 변수로 저장 되어 `null` 가장 바깥쪽 프로젝트 하위 형식을 설정 하는 함수 및 `IUnknown` 를 `pOuter`합니다.

    2.  다음 호출 하는 환경 `HrCreateInnerProj` 함수 목록에 두 번째 프로젝트 형식의 GUID입니다. 이 GUID는 두 번째 내부 프로젝트 하위 형식 집계 시퀀스에서 기본 프로젝트에서 단계별 실행에 해당 합니다.

    3.  `pOuter` 이제 가리키는 `IUnknown` 가장 바깥쪽 프로젝트 하위 형식의 및 `HrCreateInnerProj` 의 구현이 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> 구현에 대 한 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A> 제어용 전달 메서드 `IUnknown` 가장 바깥쪽 프로젝트 하위 형식의 `pOuter`합니다. 소유 프로젝트 (내부 프로젝트 하위 형식) 여기에 해당 집계 프로젝트 개체를 만들어야 합니다. 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.SetInnerProject%2A> 메서드 구현에 대 한 포인터에 전달 된 `IUnknown` 집계 되는 내부 프로젝트의 합니다. 이러한 두 가지 방법 집계 개체를 만들고 프로젝트 하위 형식 자체에 대 한 참조 횟수를 보유를 끝나지 않습니다을 보장 하는 COM 집계 규칙에 따라를 구현 해야 합니다.

    4.  `HrCreateInnerProj` 구현이 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProjectFactory.PreCreateForOuter%2A>합니다. 이 메서드를 프로젝트 하위 형식 자체 초기화 작업을 수행 합니다. 예를 들어 솔루션에는 이벤트를 등록할 수, 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAggregatableProject.InitializeForOuter%2A>합니다.

    5.  `HrCreateInnerProj` 목록에서 마지막 GUID (기본 프로젝트)에 도달할 때까지 재귀적으로 호출 됩니다. 이러한 호출의 각 단계를 통해 d, c 반복 됩니다. `pOuter` 가장 바깥쪽 프로젝트 하위 형식 가리키는 `IUnknown` 각 집계 수준에 대 한 합니다.

## <a name="example"></a>예제

다음 예제에서는의 대략적인 표현에 프로그래밍 방식으로 프로세스를 자세히 설명 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject.CreateAggregateProject%2A> 메서드를 환경에 의해 구현 됩니다. 코드는 예 시일 뿐입니다. 컴파일하지 않을 적합 하지 않습니다와 쉽게 구별할 수 있도록 제거 된 모든 오류 검사 합니다.

```cpp
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

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualStudio.Shell.Flavor>
- [프로젝트 하위 형식](../../extensibility/internals/project-subtypes.md)
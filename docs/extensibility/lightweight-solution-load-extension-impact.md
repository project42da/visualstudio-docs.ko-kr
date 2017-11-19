---
redirect_url: /visualstudio/extensibility/what-s-new-in-the-visual-studio-2017-sdk/
ms.openlocfilehash: 5706797ed88dce5b2f481b17d99e9501b960ddca
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
제목: "간단한 솔루션 로드 (LSL) | Microsoft Docs "ms.custom:" "ms.date:" 01/17/2017 "ms.reviewer:" "ms.suite:" "ms.technology: 
  - "vs ide sdk" ms.tgt_pltfrm: "" ms.topic: helpviewer_keywords "문서": 
  - "Vspackage, 간단한 솔루션 로드"
  - "Vspackage, 빠른 솔루션 로드" ms.assetid: 0a71d91e-dc71-4d6b-bbfe-9e4ecd9e5fd1 caps.latest.revision: 만든이 1 명이: "gregvanl" ms.author: "gregvanl" 관리자: ghogen
---
# <a name="lightweight-solution-load-lsl"></a>간단한 솔루션 로드 (LSL)

## <a name="background-information-on-lsl"></a>LSL 대 한 배경 정보

간단한 솔루션 로드는 신속 하 게 생산성을 높일 수 있도록 솔루션 로드 시간을 크게 줄일 있습니다 VS 2017의 새로운 기능입니다. LSL를 사용 하는 경우 Visual Studio 로드 되지 않습니다 완벽 하 게 프로젝트와 작업을 시작 하기 전 까지는.

LSL Visual Studio 확장에 영향을 줄 수 있습니다. 확장 로드 되도록 프로젝트에 종속 된 기능 작동 하거나이 문서에에서 자세히 설명 하는 지침을 따르지 않고 제대로 작동 하지 않을 수 있습니다.

추가 대 한 배경 LSL, 다음 링크를 사용 합니다.

* [간단한 솔루션 부하 블로그](https://blogs.msdn.microsoft.com/visualstudio/2016/10/11/shorter-solution-load-time-in-visual-studio-15)
* 질문? 문의 하세요.[lslsupport@microsoft.com](mailto:lslsupport@microsoft.com)

## <a name="enable-the-setting-to-load-projects-in-deferred-mode"></a>프로젝트 "지연된" 모드에서 로드할 설정을 사용 하도록 설정

1. 모든 현재 열려 있는 솔루션을 닫습니다.
2. 로 이동 **도구** > **옵션** > **프로젝트 및 솔루션** > **일반** 설정 페이지입니다.
3. 확인 된 **간단한 솔루션 로드** 상자 설정을 사용 하도록 설정 합니다.

켜져 위의 설정을 사용 하 여 솔루션을 열면 IDE는 프로젝트의 일반 뷰를 표시 하지만 프로젝트는 로드 되지 않습니다.

## <a name="differences-between-deferred-load-and-regular-load-of-projects"></a>지연 된 로드 및 프로젝트의 일반 로드 간의 차이점

Lightweight 솔루션 로드 된 프로젝트는 솔루션을 열 때 로드 되지 않습니다. 프로젝트에 대 한 이러한"지연", 스텁 계층 생성 됩니다. 솔루션 탐색기 표시가 없습니다 UI 모드"지연된"에 있는 일부 또는 모든 프로젝트 아이콘 및 프로젝트의 이름을 사용 하 여 예상된 뷰를 보여 줍니다.

LSL 활성화와 확장 기대할 수 있는 더 이상 작업이 트리거될 때 필요한 프로젝트가 이미 완전히 로드 됩니다. 호출자는 로드 된 프로젝트에 종속성 있는지 확인 해야 합니다. 확장 해야 지연 된 프로젝트의에서 정보를 확장은 다음을 수행 합니다.

1. 필요에 따라 프로젝트를 로드 합니다.
2. 새로운 **작업 영역 Api** 로드 하지 않고 지연 된 프로젝트에서 정보를 가져올 수 있습니다.

새 **작업 영역 Api** 확장에서 지연 된 프로젝트에서 소스 파일의 모든 지정된 된 프로젝트에 대 한 소스 파일은 소유 프로젝트 등의 정보를 가져올 수 있습니다. 경우에 따라 제한 된 집합의 프로젝트 로드 해야 합니다. 적절 한 옵션은 작업의 빈도, 다른 방법 및 전체 사용자 경험의 용이성 간의 균형입니다.

모든 프로젝트 및 솔루션 로드 이벤트는 여전히 LSL 모드에서 발생 됩니다. 이렇게 하면 구성 요소를 VS에서 예상 되는 동작을 가져올 수 있습니다.을 프로젝트 로드 되는 시기와 같은 방식으로 동작 합니다. 프로젝트 로드 관련 솔루션 작업 하지만 감소 현저 하 게 됩니다.

## <a name="ui-requirements-and-changes"></a>UI 요구 사항 및 변경 내용

모든 UI를 동일 하 고 지연 된 로드 된 프로젝트를 처리 해야 합니다. 즉, 로드 된 프로젝트에서 수행할 수 있는 모든 작업 몇 가지 예외가 지연 된 프로젝트에 적용할 수 있어야 합니다. 이 기능을 위해 새로운 Api 소개 뿐만 아니라 일부 기존 플랫폼 Api에 변경 사항이 있습니다.

### <a name="expectations-for-ui"></a>UI에 대 한 기대

1. 기능은 시각적 프로젝트 로드 되거나 지연 되는 경우에 따라 차이점 표시 해야 합니다.
2. 모든 목록 또는 솔루션의 로드 된 프로젝트를 통해 열거형 지연 된 프로젝트를 포함 해야 합니다.
3. 지연 된 프로젝트에 대해 로드 된 프로젝트에 대해 사용 가능한 모든 동작 해야 합니다.
4. 기능을 반드시 로드 요청을 경우에만 프로젝트:
  * 기능을 통해 직접 사용자 상호 작용이 있습니다. 프로젝트를 미리 로드 하지 않습니다.
  * 사용자가 "참조 더 결과" 제스처가 이루어집니다. 이 UI 지침 아래를 참조 하십시오.
  * 동작을 충족 하지 완전히 로드 된 프로젝트에만 사용할 수 있습니다. LSL 및 가능한 경우 항상 열기 프로젝트 Api를 사용 하 고 기능 요청에서 요구 하는 기능이 없는 보냅니다.

### <a name="changes-in-platform-apis-to-help-drive-ui"></a>플랫폼 UI 드라이브 수 있도록 Api의에서 변경 내용

1. Lightweight 솔루션 로드 모드와 프로젝트의 수는 지연 된 상태에서 열린 경우 솔루션을 요청 하는 새로운 Api 제공 됩니다.
2. 지연 된 모든 프로젝트를 솔루션에 로드 하는 경우 새 이벤트에 대 한 제공 됩니다.
3. 지연 된 경우에 프로젝트를 요청 하는 새로운 Api 제공 됩니다.
4. 기존 Api 로드 된 프로젝트를 요청 하는 경우 지연 된 프로젝트를 포함 하도록 업데이트 됩니다.
5. 기존 Api 업데이트 되어 빠른 솔루션은 완전히 로드 된 솔루션을 연 후 합니다.

### <a name="how-to-add-see-more-results-for-a-feature"></a>기능에 대 한 "참조 더 결과"를 추가 하는 방법입니다.

프로젝트의 내용에 쿼리를 수행 하는 기능에는 지연 된 프로젝트의 영향을 고려해 야 합니다. 경우에 따라 기능은 지연 된 프로젝트에 대 한 LSL 및 작업 영역 Api에서 해당 쿼리의 결과 얻을 수 있습니다. 다른 경우에는 기능 제한 프로젝트를 로드 해야 합니다. 이러한 경우 모두 사용자가 완전히 프로젝트와 다시 쿼리를 로드할 수 있도록 하는 새 "참조 더 결과" 제스처를 제공 해야 합니다. 이 제스처 프로젝트는 실제로 로드 하는 경우 완벽 한 결과 얻을 수 있는 방법 사용자에 게 제공 하는 동안 지연 된 프로젝트는 때 최적의 근사값을 제공 하는 기능을 사용할 수 있습니다.

기능에 대 한 일반 알고리즘 같아야 합니다.

### <a name="when-the-query-is-performed-over-a-single-project"></a>쿼리는 단일 한 프로젝트를 통해 수행 될 때

```csharp
// IsInDeferredState() and EnsureProjectIsLoadedHelper() in this sample can be found in the "Helpful code snippets" section of this document
public void Query(IVsHierarchy projectToQuery)
{
    // 1. Perform calculation/query
    DoQuery(projectToQuery);

    // 2. Present results to the user
    ShowResults();

    // 3. If the project was deferred, then present a "See More Results" UI element
    if (IsInDeferredState(projectToQuery))
    {
        ShowSeeMoreResults();
    }
}

public void OnClick_SeeMoreResults()
{
    // 1. Ask ask for the project to be loaded
    IVsHierarchy projectFromLastQuery = GetProjectFromLastQuery();
    IVsHierarchy loadedProject = EnsureProjectIsLoadedHelper(projectFromLastQuery);

    if (loadedProject != null)
    {
        // 2. Re-run the query on the loaded projects
        Query(loadedProject);
    }
    else
    {
        ShowErrorMessage();
    }
}
```

### <a name="when-the-query-is-performed-over-the-whole-solution"></a>쿼리가 전체 솔루션을 통해 수행 될 때

```csharp
// Requires Microsoft.VisualStudio.Shell.Interop.15.0.DesignTime.dll
public void Query()
{
    // 1. Perform calculation/query
    DoQuery();

    // 2. Present results to the user
    ShowResults();

    // 3. If there were deferred projects, then present a "See More Results from all projects" UI element
    var solution = // the solution
    object deferredCount = 0;
    int hr = ((IVsSolution)solution).GetProperty((int)__VSPROPID7.VSPROPID_DeferredProjectCount, out deferredCount);
    if (ErrorHandler.Succeeded(hr) && ((int)deferredCount > 0))
    {
        ShowSeeMoreResults();
    }
}

public void OnClick_SeeMoreResults()
{
    // 1. Force the solution to load, as requested by the user. This brings up a UI with a "Cancel" button (unless supppresed with __VSBSLFLAGS.VSBSLFLAGS_NotCancelable)
    var solution = // get IVsSolution4
    int hr = ((IVsSolution4)solution).EnsureSolutionIsLoaded((uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    if (ErrorHandler.Succeeded(hr))
    {
        // 2. Re-run the query
        Query();
    }
    else
    {
        ShowErrorMessage();
    }
}
```

## <a name="api-changes"></a>API 변경 내용

### <a name="new-api"></a>새 API

IVsSolution7.IsSolutionLoadDeferred (out 지연 bool)

현재 솔루션 지연 된 모드에서 로드 된 경우 true를 반환 합니다. 솔루션 지연 된 모든 프로젝트는 결국 하는 경우에 처음 지연 된 모드에서 로드 된 경우 로드 (명시적 사용자 제스처로 인 한 또는 작업에 의해 강제)는 현재 세션에서이 속성을 true를 반환 계속 합니다.

__VSPROPID7 합니다. VSPROPID_DeferredProjectCount

지연 된 모드에서 현재 프로젝트의 수를 반환합니다. 이 속성에는 [0, VSPROPID_ProjectCount] 범위에 값을 갖습니다.

__VSHPROPID9 합니다. VSHPROPID_IsDeferred

프로젝트 계층 구조 지연 된 로드 상태에 있으면 true를 반환 합니다.

__VSENUMPROJFLAGS3 EPF_DEFERRED과 EPF_NOTDEFERRED 값으로 사용

이러한 플래그에 전달 될 수 [IVsSolution.GetProjectEnum()](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivssolution.getprojectenum.aspx) 지연 되 고 지연 되지 않은 프로젝트에 대 한 반복 합니다.

### <a name="new-events"></a>새 이벤트

IVsSolutionEvents7.OnAfterLoadAllDeferredProjects()

이 이벤트는 모든 지연 된 프로젝트 로드 된 후에 발생 합니다. 이 시점에서 VSPROPID_DeferredProjectCount은 0과 같습니다. 이 이벤트는 하지 않습니다 솔루션 로드의 일부로 발생 하 고 세션에서 전혀 발생 하지 않을 수 있습니다. 지연 된 모든 프로젝트 로드 된 경우에 실행 됩니다.

### <a name="changes-to-existing-api"></a>기존 API의 변경 내용

* 전달 [__VSENUMPROJFLAGS](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vsenumprojflags.aspx)합니다. EPF_LOADEDINSOLUTION [IVsSolution.GetProjectEnum()](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.ivssolution.getprojectenum.aspx) 반환 프로젝트를 지연 합니다.
* 전달 [__VSENUMPROJFLAGS](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vsenumprojflags.aspx)합니다. EPF_UNLOADEDINSOLUTION 지연 된 프로젝트를 반환 하지 않습니다.
* [KnownUIContexts.SolutionExistsAndFullyLoadedContext](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.knownuicontexts.solutionexistsandfullyloadedcontext.aspx) 로 설정 된 솔루션에 true입니다. 지연 된 프로젝트는 대부분이 컨텍스트가 설정 되어 있으므로 로드 된 것으로 처리 됩니다 LSL 아닌 모드에서 보다 이전입니다.
* [__VSPROPID](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.shell.interop.__vspropid.aspx)합니다. VSPROPID_ProjectCount 로드 및 지연 된 프로젝트의 합계를 반환 합니다.

## <a name="helpful-code-snippets"></a>유용한 코드 조각

### <a name="check-if-a-solution-was-opened-in-deferred-load-mode"></a>지연 된 로드 모드에서 솔루션이 열려 있는지 확인

```csharp
/// <summary>
/// Checks if the solution was opened in LSL mode.
/// </summary>
/// <returns>True if the solution was opened in LSL mode, false otherwise.</returns> public static bool IsSolutionLoadDeferred()
{
    IVsSolution7 vsSolution = ServiceProvider.GlobalProvider.GetService(typeof(SVsSolution)) as IVsSolution7;
    Assumes.Present(vsSolution);

    return vsSolution.IsSolutionLoadDeferred();
}
```

### <a name="check-if-a-project-is-deferred"></a>프로젝트 지연 됩니다 확인

```csharp
/// <summary>
/// Checks to see if a project is deferred.
/// </summary>
/// <param name="projectsToLoad">A set of deferred and/or loaded projects to ensure are loaded.</param>
/// <returns>True if the project is deferred. False if it is any other state, such as loaded, unloaded, or virtual.</returns>
/// <remarks>Requires Microsoft.VisualStudio.Shell.Interop.15.0.DesignTime.dll</remarks>
public static bool IsInDeferredState(IVsHierarchy vsHierarchy)
{
    object deferred;
    int hr = vsHierarchy.GetProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID9.VSHPROPID_IsDeferred, out deferred);

    if (ErrorHandler.Succeeded(hr))
    {
        return (bool)deferred;
    }

    return false;
}
```

### <a name="load-a-project"></a>프로젝트 로드

```csharp
/// <summary>
/// Ensures a project is fully loaded.
/// </summary> /// <param name="projectToLoad">A deferred or loaded project to ensure is loaded.</param>
/// <remarks>Requires Microsoft.VisualStudio.Shell.15.0.dll and Microsoft.VisualStudio.Shell.Interop.dll</remarks>
public static IVsHierarchy EnsureProjectIsLoadedHelper(IVsHierarchy projectToLoad)
{
    int hr = VSConstants.S_OK;
    var solution = // get the solution

    // 1. Ask the solution to load the required project. To reduce wait time,
    //    we load only the project we need, not the entire solution.
    hr = projectToLoad.GetGuidProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_ProjectIDGuid, out projectGuid);
    hr = ErrorHandler.ThrowOnFailure(hr);
    hr = ((IVsSolution4)solution).EnsureProjectIsLoaded(projectGuid, (uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    hr = ErrorHandler.ThrowOnFailure(hr);

    // 2. After the project is loaded, grab the latest IVsHierarchy object.
    IVsHierarchy loadedProject = null;
    hr = ((IVsSolution)solution).GetProjectOfGuid(projectGuid, out loadedProject);
    hr = ErrorHandler.ThrowOnFailure(hr);

    return loadedProject;
}
```

### <a name="load-a-set-of-projects"></a>프로젝트를 로드 합니다.

```csharp
/// <summary>
/// Ensures a collection of IVsHierarchys are loaded. To be used when deferred projects absolutely cannot be used.
/// </summary>
/// <param name="projectsToLoad">A set of deferred and/or loaded projects to ensure are loaded.</param>
/// <remarks>Requires Microsoft.VisualStudio.Shell.15.0.dll and Microsoft.VisualStudio.Shell.Interop.dll</remarks>
public static IReadOnlyCollection<IVsHierarchy> EnsureProjectsAreLoadedHelper(IReadOnlyCollection<IVsHierarchy> projectsToLoad)
{
    if (projectsToLoad == null || projectsToLoad.Count == 0)
        return projectsToLoad;

    int hr = VSConstants.S_OK;
    List<Guid> projectGuids = new List<Guid>(projectsToLoad.Count);
    List<IVsHierarchy> loadedProjects = new List<IVsHierarchy>(projectsToLoad.Count);
    var solution = // get the solution

    // 1. Collect projects to force load
    foreach (var project in projectsToLoad)
    {
        Guid projectGuid;
        hr = project.GetGuidProperty((uint)VSConstants.VSITEMID.Root, (int)__VSHPROPID.VSHPROPID_ProjectIDGuid, out projectGuid)
        hr = ErrorHandler.ThrowOnFailure(hr);
        projectGuids.Add(projectGuid);
    }

    // 2. Ask the solution to load the required projects. To reduce wait time,
    //    we load only the projects we need, not the entire solution.
    hr = ((IVsSolution4)solution).EnsureProjectsAreLoaded(projectCount, projectGuids.ToArray(), (uint)__VSBSLFLAGS.VSBSLFLAGS_None);
    hr = ErrorHandler.ThrowOnFailure(hr);

    // 3. After the projects are loaded, grab the latest IVsHierarchy objects
    foreach (var projectGuid in projectGuids)
    {
        IVsHierarchy loadedProject = null;
        hr = ((IVsSolution)solution).GetProjectOfGuid(projectGuid, out loadedProject);
        hr = ErrorHandler.ThrowOnFailure(hr);
        loadedProjects.Add(loadedProject);
    }

    return loadedProjects;
}
```

### <a name="checks-if-the-solution-has-deferred-projects"></a>솔루션에 프로젝트를 지연 하는 경우 확인

```csharp
/// <summary>
/// Checks if the solution has deferred projects
/// </summary>
/// <returns>True if the solution has deferred projects, false otherwise.</returns>
public static bool SolutionHasDeferredProjects()
{
    IVsSolution vsSolution = ServiceProvider.GlobalProvider.GetService(typeof(SVsSolution)) as IVsSolution;
    Assumes.Present(vsSolution);
    object varHasDeferredProjects;
    if (ErrorHandler.Succeeded(vsSolution.GetProperty(
        (int)__VSPROPID7.VSPROPID_DeferredProjectCount, out varHasDeferredProjects)))
    {
        return (int)varHasDeferredProjects != 0;
    }

    return false;
}
```

## <a name="getting-detailed-information-with-workspace-apis"></a>작업 영역 Api와 자세한 정보

### <a name="how-to-get-detailed-info-on-a-lsl-solution"></a>LSL 솔루션에 대해 자세한 정보를 가져오는 방법

새 작업 영역 Api는 솔루션에 대 한 세부 정보를 검색할 수 있도록 IVsSolutionWorkspaceService를 통해 노출 됩니다.

이러한 Api의 작업 영역에 대 한 인덱스 서비스 뿐만 아니라 현재 작업 영역, 활성 솔루션, 관리 되는 명령 줄 정보를 가져오는 데 사용할 수 있습니다. 이러한 Api 추가 서비스를 사용할 수는 인덱스 예를 들어 자세한 데이터를 가져오려면 모든 프로젝트는 현재 솔루션에 포함 된 모든 P2P 참조 등 프로젝트에 프로젝트를 소스 파일의 소유 하는 프로젝트의 모든 소스 파일입니다.

다음 코드 조각은 작업 영역 Api의 사용법을 보여 줍니다.

### <a name="get-ivssolutionworkspaceservice-initially"></a>처음 IVsSolutionWorkspaceService 가져오기

>**참고:** 만 받으세요 IVsSolutionWorkspaceService LSL 시나리오 작업 영역 API 패키지를 로드 하지 않도록 합니다.

```csharp
private readonly Lazy<IVsSolutionWorkspaceService> _solutionWorkspaceService;

[ImportingConstructor]
public DeferredProjectWorkspaceService(SVsServiceProvider serviceProvider)
{
    _solutionWorkspaceService = new Lazy<IVsSolutionWorkspaceService>(
        () => (IVsSolutionWorkspaceService)serviceProvider.GetService(typeof(SVsSolutionWorkspaceService)));
}
```

>**참고:** 다음 조각 _solutionWorkspaceService 이미 지연 초기화 될 것으로 가정 합니다.

### <a name="get-managed-command-line-info-for-deferred-projects-for-active-solution-configuration"></a>활성 솔루션 구성에 대 한 지연 된 프로젝트에 대 한 관리 되는 명령줄 정보 얻기

```csharp
/// <summary>
/// Get the managed command line info for active solution configuration
/// </summary>
/// <param name="cancellationToken"> the cancellation token</param>
/// <returns></returns>
public async Task<IReadOnlyDictionary<string, ManagedCommandLineInfo>> GetManagedCommandLineInfoForConfigurationAsyn(CancellationToken cancellationToken)
{
    var dte = ServiceProvider.GetGlobalService(typeof(EnvDTE.DTE)) as EnvDTE.DTE;
    var solutionConfig = (EnvDTE80.SolutionConfiguration2)dte.Solution.SolutionBuild.ActiveConfiguration;

    // Solution configuration is something like "Debug|Any CPU"
    return await _solutionWorkspaceService.Value.GetManagedCommandLineInfoAsync(
        $"{solutionConfig.Name}|{solutionConfig.PlatformName}", cancellationToken).ConfigureAwait(false);
}
```

### <a name="get-the-active-solution-file-in-lsl"></a>LSL에서 활성 솔루션 파일 가져오기

```csharp
/// <summary>
/// Get the active solution file.
/// </summary>
/// <returns>The solution file.</returns>
public string GetActiveSolutionFile()
{
    return _solutionWorkspaceService.Value.SolutionFile;
}
```

### <a name="get-the-owning-project-of-a-source-file"></a>소스 파일의 소유 하는 프로젝트 가져오기

```csharp
/// <summary>
/// Get the owning projects of a source file.
/// </summary>
/// <param name="filePath">the source file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetOwningProjectAsync(string filePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var result = await indexService.GetFileDependantsAsync(filePath, null, String.Empty, (int)FileReferenceInfoType.Source);
    return result.Select(f => f.Path);
}
```

### <a name="get-all-source-files-from-a-project"></a>프로젝트에서 모든 소스 파일 가져오기

```csharp
/// <summary>
/// Get all source files from a project.
/// </summary>
/// <param name="projectFilePath">the project file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetFileReferenceAsync(string projectFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var fileReferenceResult = await indexService.GetFileReferencesAsync(projectFilePath, referenceTypes: (int)FileReferenceInfoType.Source);
    return fileReferenceResult.Select(f => f.Path);
}
```

### <a name="get-the-p2p-references-in-a-project"></a>프로젝트에서 P2P 참조를 가져옵니다.

```csharp
/// <summary>
/// Get outputs of project.
/// </summary>
/// <param name="projectFilePath">the project file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetFileReferenceAsync(string projectFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();
    var fileReferenceResult = await indexService.GetFileReferencesAsync(projectFilePath, context: "Debug|AnyCPU", referenceTypes: (int)FileReferenceInfoType.Output);
    return fileReferenceResult.Select(f => f.Path);
}
```

### <a name="get-all-the-projects-in-a-solution"></a>솔루션의 모든 프로젝트 가져오기

```csharp
/// <summary>
/// Get the projects in a solution.
/// </summary>
/// <param name="solutionFilePath">the solution file path.</param>
/// <returns></returns>
public async Task<IEnumerable<string>> GetProjectsInSolutionAsync(string solutionFilePath)
{
    var workspace = _solutionWorkspaceService.Value.CurrentWorkspace;
    var indexService = workspace.GetIndexWorkspaceService();

    // Passing the configuration|Platform that projects apply to; passing null will return projects with all configurations.
    var result = await indexService.GetFileReferencesAsync(solutionFilePath, context: "Debug|AnyCPU", referenceTypes: (int)FileReferenceInfoType.ProjectReference);
    return result.Select(f => f.Path);
}
```

## <a name="troubleshooting"></a>문제 해결

LSL 특성상 의도적으로 사용자가 로드 및 지연 된 프로젝트 간의 차이 볼 수는 있습니다. 이 어려울 수 있습니다 기능 개발 및 테스트 합니다.

다음을 수행 하 여 지연 된 프로젝트에 대 한 UI에 대 한 시각적 힌트를 사용할 수 있습니다.

1. Visual Studio를 닫습니다.
2. Regedit.exe
3. HKLM 선택
4. 파일 > 하이브 로드
5. `%localappdata%\microsoft\visualstudio\15.0_<instance ID>\privateregistry.bin`
6. 키 이름으로 "visual Studio"를 입력 합니다.
7. 설정 `HKLM\VisualStudio\Software\Microsoft\VisualStudio\15.0_<instanceID>\FeatureFlags\Solution\Loading\Deferred\Hint\Value=1` (DWORD)
8. HKLM\VisualStudio 선택
9. 파일 > 하이브 언로드
10. Visual Studio를 시작 합니다.

모든 추가 질문에 대 한 연락 하세요 [ lslsupport@microsoft.com ](mailto:lslsupport@microsoft.com)합니다.







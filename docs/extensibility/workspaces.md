---
title: Visual Studio에서 작업 영역 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 3489592a-dc0c-4cd3-9b08-cd367626980a
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 0230201677fd2422817ca1fbeab6679a424e5c05
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="workspaces"></a>작업 영역

Visual Studio에 있는 파일의 모든 컬렉션을 나타내는 방법 작업 영역은 [폴더 열기](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md), 하며으로 표시 됩니다는 <xref:Microsoft.VisualStudio.Workspace.IWorkspace> 유형입니다. 자체적으로 작업 영역 콘텐츠나 폴더 내의 파일에 관련 된 기능을 인식 하지 못하는 합니다. 대신, 일반 집합이 생성 하 고 다른 사용자가 작업할 수 있는 데이터를 사용할 기능 및 확장에 대 한 Api 제공 합니다. 생산자를 통해 구성 됩니다.는 [Managed Extensibility Framework](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) MEF ()를 사용 하 여 다양 한 특성을 내보냅니다.

## <a name="workspace-providers-and-services"></a>작업 영역 공급자 및 서비스

작업 영역 공급자와 서비스 데이터와 작업 영역의 내용에 대응 하는 기능을 제공 합니다. 상황에 맞는 파일 정보, 소스 파일의에서 기호를 제공 하거나 기능을 빌드할 수 있습니다.

사용 하 여 두 개념은 [팩터리 패턴](https://en.wikipedia.org/wiki/Factory_method_pattern) 작업 영역에서 MEF를 통해 가져옵니다. 내보내기 특성을 모두 구현 `IProviderMetadataBase` 또는 `IWorkspaceServiceFactoryMetadata`만 확장 내보낸된 형식에 사용 해야 하는 구체적인 형식 있습니다.

공급자와 서비스 간의 한 가지 차이점은의 관계 작업 영역에 있습니다. 작업 영역에서 특정 형식의 여러 공급자를 가질 수 있습니다 하지만 작업 영역당 하나의 서비스는 특정 유형의 만들어집니다. 예를 들어, 작업 영역을 많은 파일 스캐너 공급자 갖지만 작업 영역에는 작업 영역 마다 하나의 인덱싱 서비스.

또 다른 주요 차이점은 데이터 공급자 및 서비스를 소비 합니다. 작업 영역에는 몇 가지 이유로 공급자에서 데이터를 가져올 수 요소입니다. 첫째, 공급자는 일반적으로 일부 좁은 자신이 만든 데이터 집합을 가집니다. 데이터는 C# 소스 파일에 대 한 기호를 수 있습니다. 하거나 빌드에 대 한 파일 컨텍스트는 _CMakeLists.txt_ 파일입니다. 작업 영역에는 요청에 맞춰 해당 메타 데이터 공급자에 대 한 소비자의 요청과 일치 합니다. 일부 시나리오는 대부분에 대 한 허용 되는 둘째, 우선 순위가 가장 높은 공급자를 사용 하는 시나리오를 다른 요청에 기여 하는 공급자입니다.

반면, 확장의 인스턴스를 가져오고 작업 영역 서비스와 직접 상호 작용할 수 있습니다. 에 대 한 확장 메서드 `IWorkspace` 와 같은 Visual Studio에서 제공 하는 서비스에 사용할 수 있는 <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetFileWatcherService%2A>합니다. 확장 프로그램 사용 하는 다른 확장에 대 한 확장 프로그램 내에서 구성 요소에 대 한 작업 영역 서비스를 제공할 수 있습니다. 소비자가 사용 해야 <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetServiceAsync%2A> 또는에 제공 하는 확장 메서드는 `IWorkspace` 유형입니다.

>[!WARNING]
> Visual Studio와 충돌 하는 서비스를 만들지 마십시오. 예기치 않은 문제가 발생할 수 있습니다.

## <a name="disposal-on-workspace-closure"></a>작업 영역 닫기 전 삭제

작업 영역 닫기 전, extender를 삭제 하지만 비동기 호출 해야 할 수 코드입니다. <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable> 인터페이스를 쉽게이 코드를 작성할 수 있습니다.

## <a name="related-types"></a>관련된 형식

- <xref:Microsoft.VisualStudio.Workspace.IWorkspace> 열려 있는 폴더 처럼는 열린된 작업 영역에 대 한 중앙 엔터티입니다.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceProviderFactory`1> 인스턴스화된 작업 영역당 공급자를 만듭니다.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspaceServiceFactory> 인스턴스화된 작업 영역당 서비스를 만듭니다.
- <xref:Microsoft.VisualStudio.Threading.IAsyncDisposable> 공급자 및 삭제 하는 동안 비동기 코드를 실행 해야 하는 서비스에서 구현 되어야 합니다.
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper> 잘 알려진 서비스 또는 임의의 서비스에 액세스 하기 위한 도우미 메서드를 제공 합니다.

## <a name="workspace-settings"></a>작업 영역 설정

작업 영역에 있는 한 <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager> 간단 하지만 강력한 작업 영역을 제어할 수 있는 서비스입니다. 설정의 기본적인 개요를 참조 하십시오. [빌드 사용자 지정 하 고 작업을 디버그](../ide/customize-build-and-debug-tasks-in-visual-studio.md)합니다.

가장에 대 한 설정을 `SettingsType` 유형은 _.json_ 파일, _VSWorkspaceSettings.json_ 및 _tasks.vs.json_합니다.

작업 영역 설정의 "범위"는 내 작업 영역에서 단순히 경로 중심으로 합니다. 소비자가 호출 하는 경우 <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A>, 요청 된 경로 및 설정 유형을 포함 하는 모든 범위 집계 됩니다. 범위 집계 우선 순위는 다음과 같습니다.

1. 로컬 "설정" 작업 영역 루트는 일반적으로 `.vs` 디렉터리입니다.
1. 자체는 요청 된 경로입니다.
1. 요청한 경로의 부모 디렉터리입니다.
1. 모든 디렉터리 및 작업 영역 루트까지 추가 부모.
1. "전역 설정"을 사용자 디렉터리에 있습니다.

결과의 인스턴스가 <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings>합니다. 이 개체를 특정 형식에 대 한 설정을 보유 하 고로 저장 된 키 이름 설정에 대해 쿼리할 수 있습니다 `string`합니다. <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings.GetProperty%2A> 메서드 및 <xref:Microsoft.VisualStudio.Workspace.Settings.WorkspaceSettingsExtensions> 확장 메서드는 호출자가 요청 된 설정 값의 형식을 알 수를 예상 합니다. 대부분의 설정 파일으로 유지 됩니다 _.json_ 파일, 많은 호출 ´ ֲ `string`, `bool`, `int`, 및 이러한 형식의 배열이 있습니다. 개체 유형에 지원 됩니다. 이러한 경우에 사용할 수 있습니다 `IWorkspaceSettings` 자체는 형식 인수입니다. 예를 들어:

```json
{
  "intValue": 1,
  "stringValue": "s",
  "boolValue": true,
  "stringArray": [
    "s1",
    "s2"
  ],
  "nestedIWorkspaceSettings": {
    "nestedString": "ns"
  }
}
```

사용자의에 있던 이러한 설정 가정 _VSWorkspaceSettings.json_로 데이터를 액세스할 수 있습니다.

```csharp
using System.Collections.Generic;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static void ReadSettings(IWorkspace workspace)
{
    IWorkspaceSettingsManager settingsManager = workspace.GetSettingsManager();
    IWorkspaceSettings settings = settingsManager.GetAggregatedSettings(SettingsTypes.Generic);

    // result == WorkspaceSettingsResult.Success
    WorkspaceSettingsResult result = settings.GetProperty("intValue", out int intValue);
    result = settings.GetProperty("stringValue", out string stringValue);
    result = settings.GetProperty("boolValue", out bool boolValue);
    result = settings.GetProperty("stringArray", out string[] stringArray);
    result = settings.GetProperty("nestedIWorkspaceSettings", out IWorkspaceSettings nestedIWorkspaceSettings);
    result = nestedIWorkspaceSettings.GetProperty("nestedString", out string nestedString);

    // Extension method alternative using default values.
    int intValueOrDefault = settings.Property("intValue", /* default */ 42);

    // Missing key. result == WorkspaceSettingsResult.Undefined
    result = settings.GetProperty("missing", out string missing);

    // Wrong type for a key. result == WorkspaceSettingsResult.Error
    result = settings.GetProperty("intValue", out IWorkspaceSettings notSettings);

    // Special ability to union "stringArray" across all scopes.
    IEnumerable<string> allStringArray = settings.UnionPropertyArray<string>("stringArray");
}
```

>[!NOTE]
>이러한 설정은 Api에서 사용할 수 있는 Api에 관련이 없는 `Microsoft.VisualStudio.Settings` 네임 스페이스입니다. 호스트의 영향을 받지 않습니다 하 고 작업 영역 설정 파일 또는 동적 설정 공급자를 사용 하는 작업 영역 설정 합니다.

### <a name="providing-dynamic-settings"></a>동적 설정 제공

확장을 제공할 수 <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProvider>s입니다. 이러한 메모리 내 공급자 설정을 추가 하거나 다른 사용자를 재정의 하는 확장을 허용 합니다.

내보내기는 `IWorkspaceSettingsProvider` 다른 작업 영역 공급자 다릅니다. 공장 않습니다 `IWorkspaceProviderFactory` 및 특수 특성 형식이 없습니다. 대신, 구현 <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsProviderFactory> 사용 `[Export(typeof(IWorkspaceSettingsProviderFactory))]`합니다.

```csharp
// Common workspace provider factory pattern
[ExportFeatureProvider(some, args, to, export)]
internal class MyProviderFactory : IWorkspaceProviderFactory<IFeatureProvider>
{
     IFeatureProvider CreateProvider(IWorkspace workspace) => new Provider(workspace);
}

// IWorkspaceSettingsProvider pattern
[Export(typeof(IWorkspaceSettingsProviderFactory))]
internal class MySettingsProviderFactory : IWorkspaceSettingsProviderFactory
{
    // 100 is typically the value used by built-in settings providers. Lower value is higher priority.
    int Priority => 100;

    IWorkspaceSettingsProvider CreateSettingsProvider(IWorkspace workspace) => new MySettingsProvider(workspace);
}
```

>[!TIP]
>반환 하는 메서드를 구현 하는 경우 `IWorkspaceSettingsSource` (같은 `IWorkspaceSettingsProvider.GetSingleSettings`), 인스턴스를 반환 `IWorkspaceSettings` 대신 `IWorkspaceSettingsSource`합니다. `IWorkspaceSettings` 일부 설정 집계 중에 유용할 수 있는 자세한 정보를 제공 합니다.

### <a name="settings-related-apis"></a>설정 관련 Api

- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager> 작업 영역에 대 한 읽기 및 집계 설정입니다.
- <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetSettingsManager%2A> 가져옵니다는 `IWorkspaceSettingsManager` 작업 영역에 대 한 합니다.
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettingsManager.GetAggregatedSettings%2A> 지정된 된 범위에서 모든 겹치는 범위 집계에 대 한 설정을 가져옵니다.
- <xref:Microsoft.VisualStudio.Workspace.Settings.IWorkspaceSettings> 특정 범위에 대 한 설정을 포함합니다.

## <a name="workspace-suggested-practices"></a>작업 영역 제안 사례

- 개체를 반환 `IWorkspaceProviderFactory.CreateProvider` 또는 비슷한 Api를 기억 하는 해당 `Workspace` 컨텍스트를 만들 때. 공급자 인터페이스는이 개체 만들기에 유지 될 예상 기록 됩니다.
- 작업 영역 캐시 또는 설정 작업 영역의 "로컬 설정" 경로 내에 저장 합니다. 사용 하 여 파일에 대 한 경로 만들기 `Microsoft.VisualStudio.Workspace.WorkspaceHelper.MakeRootedUnderWorkingFolder` Visual Studio 2017 15.6 이후 버전에에서 있습니다. 버전 15.6 이전 버전의 경우 다음 코드 조각을 사용 합니다.

```csharp
using System.IO;
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Settings;

private static string MakeRootedUnderWorkingFolder(IWorkspace workspace, string relativePath)
{
    string workingFolder = workspace.GetSettingsManager().GetAggregatedSettings(SettingsTypes.WorkspaceControlSettings).Property<string>("WorkingFolder");
    return Path.Combine(workingFolder, relativePath);
}
```

## <a name="solution-events-and-package-auto-load"></a>솔루션 이벤트 및 패키지 자동 로드

로드 된 패키지를 구현할 수 `IVsSolutionEvents7` 호출 `IVsSolution.AdviseSolutionEvents`합니다. 열고 닫는 Visual Studio에서 폴더에 대 한 이벤트 포함 됩니다.

패키지를 자동으로 로드 UI 컨텍스트를 사용할 수 있습니다. 값이 `4646B819-1AE0-4E79-97F4-8A8176FDD664`인 경우

## <a name="troubleshooting"></a>문제 해결

### <a name="the-sourceexplorerpackage-package-did-not-load-correctly"></a>SourceExplorerPackage 패키지가 올바르게 로드 되지 않았습니다.

작업 영역 확장성 과도 하 게 MEF 기반 이며 컴퍼지션 오류는 패키지를 로드 하지 못하도록 폴더 열기 호스팅 발생 합니다. 예를 들어 확장 형식을 내보냅니다 `ExportFileContextProviderAttribute`만 구현 하지만 `IWorkspaceProviderFactory<IFileContextActionProvider>`, Visual Studio에서 폴더를 열려고 할 때 오류가 발생 합니다. 오류 세부 정보에서 확인할 수 있습니다 _%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_id\ComponentModelCache\Microsoft.VisualStudio.Default.err_합니다. 확장 프로그램에 의해 구현 되는 형식에 대 한 모든 오류를 해결 합니다.

## <a name="next-steps"></a>다음 단계

* [파일 컨텍스트](workspace-file-contexts.md) -파일 컨텍스트 공급자를 통해 폴더 열기 작업 영역을 코드 intelligence 합니다. 
* [인덱싱](workspace-indexing.md) -작업 영역 인덱싱를 수집 하 고 작업 영역에 대 한 정보를 유지 합니다.

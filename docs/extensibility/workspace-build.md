---
title: Visual Studio에서 작업 영역 빌드 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 813f7a5e-f298-4469-9f4c-a5bddf5a6e14
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 258a64794712da92b881f3798255efc60cfdbe5c
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="workspace-build"></a>작업 영역 빌드

빌드 지원 [폴더 열기](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) 시나리오는 extender를 제공할 필요 [인덱싱된](workspace-indexing.md) 및 [파일 컨텍스트](workspace-file-contexts.md) 에 대 한 데이터는 [작업 영역](workspaces.md),으로 뿐만 아니라 실행 하는 빌드 작업입니다.

다음은 확장 필요한 항목의 개요입니다.

## <a name="build-file-context"></a>파일 컨텍스트 빌드

- 공급자 팩터리
  - `ExportFileContextProviderAttribute` 특성이 `supportedContextTypeGuids` 적용 가능한 모든 같이 `string` 상수 `BuildContextTypes`
  - 구현 `IWorkspaceProviderFactory<IFileContextProvider>`
  - 파일 컨텍스트 공급자
    - 반환 된 `FileContext` 각각에 대 한 빌드 작업 및 구성 지원
      - `contextType` 보낸 사람 <xref:Microsoft.VisualStudio.Workspace.Build.BuildContextTypes>
      - `context` 구현 <xref:Microsoft.VisualStudio.Workspace.Build.IBuildConfigurationContext> 와 `Configuration` 빌드 구성으로 속성 (예를 들어 `"Debug|x86"`, `"ret"`, 또는 `null` 적용할 수 없는 경우). 또는의 인스턴스를 사용 하 여 <xref:Microsoft.VisualStudio.Workspace.Build.BuildConfigurationContext>합니다. 구성 값 **해야** 인덱싱되는 파일 데이터 값에서 구성과 일치 합니다.

## <a name="indexed-build-file-data-value"></a>파일 데이터 값이 인덱싱된 빌드

- 공급자 팩터리
  - `ExportFileScannerAttribute` 특성이 `IReadOnlyCollection<FileDataValue>` 지원 되는 형식으로
  - 구현 `IWorkspaceProviderFactory<IFileScanner>`
- 파일 검색 `ScanContentAsync<T>`
  - 데이터를 반환 하면 `FileScannerTypeConstants.FileDataValuesType` 는 형식 인수
  - 생성 된 각 구성에 대 한 파일 데이터 값을 반환 합니다.
    - `type` 으로 `BuildConfigurationContext.ContextTypeGuid`
    - `context` 빌드 구성으로 (예를 들어 `"Debug|x86"`, `"ret"`, 또는 `null` 적용할 수 없는 경우). 이 값 **해야** 파일 컨텍스트에서 구성과 일치 합니다.

## <a name="build-file-context-action"></a>빌드 파일 상황에 맞는 작업

- 공급자 팩터리
  - `ExportFileContextActionProvider` 특성이 `supportedContextTypeGuids` 적용 가능한 모든 같이 `string` 상수 `BuildContextTypes`
  - 구현 `IWorkspaceProviderFactory<IFileContextActionProvider>`
- 에 작업 공급자 `IFileContextActionProvider.GetActionsAsync`
  - 반환 된 `IFileContextAction` 와 일치 하는 지정 된 `FileContext.ContextType` 값
- 파일 상황에 맞는 작업
  - 구현 `IFileContextAction` 및 <xref:Microsoft.VisualStudio.Workspace.Extensions.VS.IVsCommandItem>
  - `CommandGroup` 속성 반환 `16537f6e-cb14-44da-b087-d1387ce3bf57`
  - `CommandId` `0x1000` 빌드에 대해 `0x1010` 다시 작성에 대 한 또는 `0x1020` 에 대 한 정리

>[!NOTE]
>이후는 `FileDataValue` 인덱싱해야, 몇 가지 작업 영역을 열고 파일 전체 빌드 기능에 대 한 검사가 실행 지점 간의 시간 차이 됩니다. 지연 된 첫 번째 열기에 폴더의 이전에 캐시 된 인덱스가 없기 때문에 표시 됩니다.

## <a name="reporting-messages-from-a-build"></a>빌드 로부터 메시지를 보고합니다.

빌드 수 화면 정보, 경고 및 오류 메시지 사용자에 게 두 가지 방법 중 하나입니다. 간단한 방법을 사용 하는 것은 <xref:Microsoft.VisualStudio.Workspace.Build.IBuildMessageService> 설명과 <xref:Microsoft.VisualStudio.Workspace.Build.BuildMessage>, 같이:

```csharp
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Build;

private static void OutputBuildMessage(IWorkspace workspace)
{
    IBuildMessageService buildMessageService = workspace.GetBuildMessageService();

    if (buildMessageService != null)
    {
      // Example error build message. See the documentation for BuildMessage for more information.
      var message = new BuildMessage()
      {
          Type = BuildMessage.TaskType.Error,
          Code = "MY1001",
          TaskText = "This is a sample error",
          ProjectFile = "buildfile.bld",
          File = "sourcefile.src"
          LogMessage = $"This is sample text that will only go to the Build output window pane.\n"

          // And any other properties to set
      };

      buildMessageService.ReportBuildMessages(new BuildMessage[] { message });
    }
}
```

`BuildMessage.Type` 및 `BuildMessage.LogMessage` 의 사용자에 게 정보를 제공 하는 동작을 제어 합니다. 모든 `BuildMessage.TaskType` 이외의 값 `None` 생성 됩니다는 **오류 목록** 항목 지정된 세부 정보를 사용 합니다. `LogMessage` 항상 출력 합니다는 **빌드** 의 창은 **출력** 도구 창입니다.

또한 확장 직접 상호 작용할 수는 **오류 목록** 또는 **빌드** 창. Visual Studio 2017 버전 15.7 이전 버전에서는 하는 버그가 있습니다. 여기서는 `pszProjectUniqueName` 의 인수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane2.OutputTaskItemStringEx2*> 는 무시 됩니다.

>[!WARNING]
>호출자에 게 `IFileContextAction.ExecuteAsync` 에 대 한 임의의 기본 구현을 제공할 수는 `IProgress<IFileContextActionProgressUpdate>` 인수입니다. 실행 하지 않도록 `IProgress<IFileContextActionProgressUpdate>.Report(IFileContextActionProgressUpdate)` 직접 합니다. 현재이 인수를 사용 하 여에 대 한 일반적인 지침은 없습니다도 있지만 이러한 지침은 변경 될 수 있습니다.

## <a name="build-related-apis"></a>빌드 관련 Api

- <xref:Microsoft.VisualStudio.Workspace.Build.IBuildConfigurationContext> 빌드 구성 세부 정보를 제공합니다.
- <xref:Microsoft.VisualStudio.Workspace.Build.IBuildMessageService> 표시 <xref:Microsoft.VisualStudio.Workspace.Build.BuildMessage>사용자에 게 s입니다.

## <a name="tasksvsjson-and-launchvsjson"></a>tasks.vs.json 및 launch.vs.json

에 대 한 내용은 tasks.vs.json 또는 launch.vs.json 파일 작성, [빌드 사용자 지정 하 고 작업을 디버그](../ide/customize-build-and-debug-tasks-in-visual-studio.md)합니다.

## <a name="next-steps"></a>다음 단계

* [언어 서버 프로토콜](language-server-protocol.md) -Visual Studio로 언어 서버를 통합 하는 방법을 알아봅니다.
---
title: Visual Studio에서 작업 영역 파일 컨텍스트 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 7aaa0e65-f492-49ea-a845-35bd14910ca7
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: cdb013bb10c72041b03fce43e115806ecb3faeac
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="workspace-file-contexts"></a>작업 영역 파일 컨텍스트

에 대 한 모든 정보 [폴더 열기](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) 작업 영역 "파일 상황에 맞는" 구현 하는 공급자에 의해 생성 된는 <xref:Microsoft.VisualStudio.Workspace.IFileContextProvider> 인터페이스입니다. 패턴 폴더에 표시 되는 이러한 확장명 또는 파일을 MSBuild 파일 및 메이크파일, 읽을 파일 컨텍스트를 정의 하는 데 필요한 정보를 누적 하기 위해 패키지 종속 파일 등을 검색 합니다. 단독으로 파일 컨텍스트 작업을 수행 하지 않지만 대신 다른 확장 한 다음 작업을 수행할 수 있는 데이터를 제공 합니다.

각 <xref:Microsoft.VisualStudio.Workspace.FileContext> 에 `Guid` 연결 된 데이터의 형식을 식별 하는 것가 수행 합니다. 이 작업 영역을 사용 하 여 `Guid` 를 통해 데이터를 사용 하는 확장명과 일치 하는 나중에 <xref:Microsoft.VisualStudio.Workspace.FileContext.Context> 속성입니다. 파일 컨텍스트 공급자는 파일 컨텍스트를 식별 하는 메타 데이터를 사용 하 여 내보낸 `Guid`s에 데이터를 생성할 수 있습니다.

를 정의한 후 파일 컨텍스트를 파일 또는 작업 영역에서 폴더의 여러 연결할 수 있습니다. 지정 된 파일 또는 폴더를 모든 파일 컨텍스트 수와 연결할 수 있습니다. 다 대 다 관계입니다.

빌드, 디버그 및 언어 서비스 컨텍스트에 파일에 대 한 가장 일반적인 시나리오 관련 되어 있습니다. 자세한 내용은 이러한 시나리오와 관련 된 다른 항목을 참조 하십시오.

## <a name="file-context-lifecycle"></a>파일 컨텍스트 수명 주기

에 대 한 수명 주기에 `FileContext` 명확 하지 않습니다. 언제 든 지는 구성 요소는 일부 컨텍스트 형식에 대 한 비동기적으로 요청할 수 있습니다. 요청 컨텍스트 형식의의 일부 하위 집합을 지 원하는 공급자는은 쿼리할 수 있습니다. `IWorkspace` 인스턴스 역할을 통해 공급자와 소비자 간의 중간 인용은 <xref:Microsoft.VisualStudio.Workspace.IWorkspace.GetFileContextsAsync%2A> 메서드. 소비자는 컨텍스트를 요청 하 고 다른 컨텍스트를 요청 하 고 장기적인된 참조를 유지 관리 될 수 있습니다는 컨텍스트에 따라 단기 일부 작업을 수행할 수 있습니다. 

못할 파일 컨텍스트 하는 파일에 변경 내용이 발생할 수 있습니다. 공급자에서 이벤트를 발생 시킬 수는 `FileContext` 업데이트의 사용자에 게 있습니다. 예를 들어, 일부 파일에 대 한 빌드 컨텍스트를 제공 하는 경우, 해당 상황을 무효화 하는 디스크에 변경 후 처음 만든 사람이 호출할 수 이벤트. 여전히 참조 하는 모든 소비자 `FileContext` 다시 다음 새 쿼리 수 `FileContext`합니다.

>[!NOTE]
>모델은 없으므로 푸시 소비자에 게 합니다. 소비자에 게 알림이 발송 되지 않습니다는 공급자의 새로운 `FileContext` 요청 후 합니다.

## <a name="expensive-file-context-computations"></a>비용 파일 컨텍스트 계산

디스크에서 읽기 파일 내용을 공급자 파일 간의 관계를 해결 해야 할 때 특히 비용이 많이 들 수 있습니다. 예를 들어 일부 소스 파일의 파일 컨텍스트 공급자를 쿼리할 수 있는 있지만 파일 컨텍스트 프로젝트 파일에서 메타 데이터에 따라 달라 집니다. 프로젝트 파일을 구문 분석 하거나 msbuild 평가 듭니다. 대신, 확장 프로그램 내보낼 수는 `IFileScanner` 만들려는 `FileDataValue` 작업 영역을 인덱싱하는 동안 데이터입니다. 이제 파일 컨텍스트, 요청 될 때의 `IFileContextProvider` 해당 인덱싱된 데이터에 대해 빠르게 쿼리할 수 있습니다. 인덱싱에 자세한 내용은 참조는 [작업 영역 인덱싱](workspace-indexing.md) 항목입니다.

>[!WARNING]
>다른 방법에 주의 해야 프로그램 `FileContext` 계산 비용이 많이 들 수 있습니다. 일부 UI 상호 작용은 동기적 이며 많은 양의 의존 `FileContext` 요청 합니다. 편집기 탭을 열고 열기를 예로 **솔루션 탐색기** 상황에 맞는 메뉴입니다. 이러한 작업 요청을 입력 하는 많은 빌드 컨텍스트를 확인 합니다.

## <a name="file-context-related-apis"></a>파일 컨텍스트 관련 Api

- <xref:Microsoft.VisualStudio.Workspace.FileContext> 데이터 및 메타 데이터를 보유합니다.
- <xref:Microsoft.VisualStudio.Workspace.IFileContextProvider> 및 <xref:Microsoft.VisualStudio.Workspace.IFileContextProvider`1> 파일 컨텍스트를 만듭니다.
- <xref:Microsoft.VisualStudio.Workspace.ExportFileContextProviderAttribute> 파일 컨텍스트 공급자를 내보냅니다.
- <xref:Microsoft.VisualStudio.Workspace.IWorkspace.GetFileContextsAsync%2A> 소비자에 대 한 파일 컨텍스트를 가져오는 데 사용 됩니다.
- <xref:Microsoft.VisualStudio.Workspace.Build.BuildContextTypes> 폴더 열기을 사용 하면 빌드 컨텍스트 형식을 정의 합니다.

## <a name="file-context-actions"></a>파일 상황에 맞는 작업

동안는 `FileContext` 자체는 일부 파일에 대 한 정당한 데이터는 <xref:Microsoft.VisualStudio.Workspace.IFileContextAction> express 및 해당 데이터 작업을 수행 하는 방법이 있습니다. `IFileContextAction` 사용법에 유연 합니다. 빌드 및 디버깅은 가장 일반적인 경우 그 중 두 가지입니다.

## <a name="reporting-progress"></a>진행률 보고

<xref:Microsoft.VisualStudio.Workspace.IFileContextActionBase.ExecuteAsync%2A> 메서드에 전달 됩니다 `IProgress<IFileContextActionProgressUpdate>`, 하지만 해당 형식으로 인수를 사용할 수 없습니다. `IFileContextActionProgressUpdate` 빈 인터페이스를 호출 하는 방식 `IProgress<IFileContextActionProgressUpdate>.Report(IFileContextActionProgressUpdate)` 스트림이 `NotImplementedException`합니다. 대신,는 `IFileContextAction` 인수 시나리오에 대해 필요에 따라 다른 형식으로 캐스팅 해야 합니다.

Visual Studio에서 제공 하는 형식에 대 한 내용은 해당 하는 시나리오의 설명서를 참조 합니다.

## <a name="file-context-action-related-apis"></a>파일 상황에 맞는 작업 관련 Api

- <xref:Microsoft.VisualStudio.Workspace.IFileContextAction> 일부 동작에 따라 실행 되는 `FileContext`합니다.
- <xref:Microsoft.VisualStudio.Workspace.IFileContextActionProvider> 인스턴스를 만드는 `IFileContextAction`합니다.
- <xref:Microsoft.VisualStudio.Workspace.ExportFileContextActionProviderAttribute> 형식을 내보냅니다 `IWorkspaceProviderFactory<IFileContextActionProvider>`합니다.

## <a name="file-watching"></a>파일 감시

작업 영역에 파일 변경 알림을 수신 하 고 제공 된 <xref:Microsoft.VisualStudio.Workspace.IFileWatcherService> 통해 <xref:Microsoft.VisualStudio.Workspace.WorkspaceServiceHelper.GetFileWatcherService%2A>합니다. "ExcludedItems" 설정이 일치 하는 파일에서 파일 알림 이벤트를 생성 하지 않습니다. 이벤트 사이의 임계값 알림 단순화 하 고 중복 감소에 사용 됩니다. 파일 변경에 반응 해야 할 때이 서비스에 가입 해야 합니다.

>[!TIP]
>작업 공간의 [인덱싱 서비스](workspace-indexing.md) 기본적으로 파일 이벤트를 구독 합니다. 파일 추가 및 수정 관련 하면 `IFileScanner`의이벤트를 해당 파일에 대 한 새 데이터에 대 한 호출입니다. 파일 삭제는 인덱싱된 데이터가 제거 됩니다. 구독 않아도 프로그램 `IFileScanner` 파일 감시자 서비스입니다.

## <a name="next-steps"></a>다음 단계

* [인덱싱](workspace-indexing.md) -작업 영역 인덱싱를 수집 하 고 작업 영역에 대 한 정보를 유지 합니다.
* [작업 영역](workspaces.md) -작업 영역 개념 및 저장소 설정 검토 합니다.

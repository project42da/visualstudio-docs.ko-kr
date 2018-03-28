---
title: Visual Studio에서 인덱싱 작업 영역 | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3163e98c-1c79-48a7-813f-7923be894ba1
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 9bf3a094184e2d57b4a066234d84a6ab6380510b
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="workspace-indexing"></a>작업 영역 인덱싱

솔루션에서 프로젝트 시스템은 빌드에 대 한 기능을 제공 하는 일을 담당, 디버깅 **GoTo** 기호 검색 및 더 합니다. 프로젝트 시스템 관계와 프로젝트 내의 파일의 기능에 이해 하기 때문에이 작업을 수행 합니다. [폴더 열기](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) 작업 영역에 풍부한 IDE 기능을 제공 하려면 동일한 통찰력 필요 합니다. 컬렉션과이 데이터의 영구 저장소에 작업 영역 인덱싱 호출 프로세스입니다. 비동기 Api 집합을 통해이 인덱싱된 데이터를 쿼리할 수 있습니다. Extender를 제공 하 여 인덱싱 프로세스에 참여할 수 <xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScanner>특정 형식의 파일을 처리 하는 방법을 알고 있는 s입니다.

## <a name="types-of-indexed-data"></a>인덱싱된 데이터의 형식

인덱싱되는 데이터의 세 가지 종류가 있습니다. 참고 파일 스캐너에서 예상 되는 형식 인덱스에서 deserialize 할 형식과에서 다릅니다.

|데이터|파일 검색 프로그램 유형|인덱스 쿼리 결과 형식|관련된 형식|
|--|--|--|--|
|참조|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfo>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileReferenceInfoType>|
|기호|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinition>|<xref:Microsoft.VisualStudio.Workspace.Indexing.SymbolDefinitionSearchResult>|<xref:Microsoft.VisualStudio.Workspace.Indexing.ISymbolService> 대신 사용 해야 `IIndexWorkspaceService` 쿼리에 대 한|
|데이터 값|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataValue>|<xref:Microsoft.VisualStudio.Workspace.Indexing.FileDataResult`1>||

## <a name="querying-for-indexed-data"></a>인덱싱된 데이터에 대 한 쿼리

에 영구 데이터에 액세스할 수 있는 비동기 형식은 두 가지가 있습니다. 통해 첫 번째는 <xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceData>합니다. 단일 파일에 대 한 기본 액세스를 제공 `FileReferenceResult` 및 `FileDataResult` 에 결과 캐시 합니다. 두 번째는는 <xref:Microsoft.VisualStudio.Workspace.Indexing.IIndexWorkspaceService> 는 캐싱을 사용 하지 않는 되지만 보조 데이터베이스가 더 많은 쿼리 기능에 대 한 합니다.

```csharp
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Indexing;

private static IIndexWorkspaceData GetCachedIndexedData(IWorkspace workspace)
{
    // Gets access to indexed data wrapped in a cache.
    return workspace?.GetIndexWorkspaceDataService()?.CreateIndexWorkspaceData();
}

private static IIndexWorkspaceService GetDirectIndexedData(IWorkspace workspace)
{
    // Gets direct access to indexed data.
    // Can also be casted to IIndexWorkspaceService2.
    return workspace?.GetIndexWorkspaceService();
}
```

## <a name="participating-in-indexing"></a>인덱싱에 참여 하 고

다음 순서에 따라 약 작업 영역 인덱싱:

1. 검색 및 지 속성 (처음 열면 검색)에 대해서만 작업 영역에 있는 파일 시스템 엔터티를 제공 합니다.
1. 파일당 가장 높은 우선 순위와 일치 하는 공급자를 검색 하 라는 메시지가 표시 `FileReferenceInfo`s입니다.
1. 파일당 가장 높은 우선 순위와 일치 하는 공급자를 검색 하 라는 메시지가 표시 `SymbolDefinition`s입니다.
1. 파일당 모든 공급자에 대 한 요청 `FileDataValue`s입니다.

확장을 구현 하 여 스캐너를 내보낼 수 `IWorkspaceProviderFactory<IFileScanner>` 및 사용 하 여 형식 내보내기 <xref:Microsoft.VisualStudio.Workspace.Indexing.ExportFileScannerAttribute>합니다. `SupportedTypes` 특성 인수에서 하나 이상의 값이 있어야 <xref:Microsoft.VisualStudio.Workspace.Indexing.FileScannerTypeConstants>합니다. 예제 스캐너를 VS SDK를 참조 하십시오. [샘플](https://github.com/Microsoft/VSSDK-Extensibility-Samples/blob/master/Open_Folder_Extensibility/C%23/SymbolScannerSample/TxtFileSymbolScanner.cs)합니다.

> [!WARNING]
> 지 원하는 파일 스캐너를 내보내지 않습니다는 `FileScannerTypeConstants.FileScannerContentType` 유형입니다. Microsoft 내부용으로 사용 됩니다.

고급 시나리오에서는 확장 임의의 파일 형식 집합을 동적으로 지원할 수 있습니다. MEF 내보내지 않고도 `IWorkspaceProviderFactory<IFileScanner>`, 확장 프로그램 내보낼 수 `IWorkspaceProviderFactory<IFileScannerProvider>`합니다. 이 팩터리 유형은 되며 가져올 인스턴스화된 되며가 인덱싱 시작 되 면 해당 <xref:Microsoft.VisualStudio.Workspace.Indexing.IFileScannerProvider.GetSymbolScannersAsync%2A> 메서드를 호출 합니다. `IFileScanner` 모든 값을 지 원하는 인스턴스 `FileScannerTpeConstants` 기호 뿐 아니라, 적용 됩니다.

## <a name="next-steps"></a>다음 단계

* [작업 영역 및 언어 서비스](workspace-language-services.md) -언어 서비스는 폴더 열기 작업 영역에 통합 하는 방법에 알아봅니다.
* [작업 영역 빌드](workspace-build.md) -MSBuild 및 메이크파일 등 시스템을 구축 하는 열려 있는 폴더를 지원 합니다.
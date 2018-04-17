---
title: 원본 제어 구성 세부 정보 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], configuration details
ms.assetid: adbee9fc-7a2e-4abe-a3b8-e6615bcd797f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fc10c7602f3298b532b4af76e66b43d469416ba5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="source-control-configuration-details"></a>소스 제어에 대 한 구성 세부 정보
소스 제어를 구현 하려면 프로젝트 시스템 또는 다음을 수행 하는 편집기를 올바르게 구성 하려면 필요 합니다.

-   변경 된 상태로 전환 권한 요청

-   파일을 저장할 수 있는 권한을 요청

-   추가, 제거 또는 프로젝트의 파일 이름을 바꿀 수 있는 권한을 요청합니다

## <a name="request-permission-to-transition-to-changed-state"></a>변경 된 상태로 전환 권한 요청
 프로젝트 또는 편집기를 호출 하 여 변경 된 (dirty) 상태로 전환 수 있는 권한을 요청 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>합니다. 구현 하는 각 편집기 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A> 호출 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 반환 하기 전에 환경에서 문서를 변경 하려면 승인을 받 및 `True` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A>합니다. 프로젝트는 기본적으로 프로젝트 파일에 대 한 편집기 및 결과적으로, 해당 파일에 대 한 텍스트 편집기 처럼 프로젝트 파일에 대 한 상태 변경 추적을 구현 하는 것에 대 한 동일한 책임을 했습니다. 환경 처리 솔루션의 상태가 변경된 하지만 솔루션 참조 하지만 해당 항목 또는 프로젝트 파일을 저장 하지 않으므로 모든 개체의 변경된 된 상태를 처리 해야 합니다. 일반적으로 프로젝트 또는 편집기는 관리 항목에 대 한 지 속성을 다음 있는지 상태 변경 추적을 구현 해야 합니다.

 에 대 한 응답에서 `IVsQueryEditQuerySave2::QueryEditFiles` 호출, 환경에는 다음을 수행할 수:

-   변경에 대 한 호출을 거부,이 경우 편집기 또는 프로젝트 유지 되어야 합니다 (새로) 상태가 변경 안 됨된.

-   문서 데이터를 다시 로드할 것인지를 나타냅니다. 프로젝트에 대 한 환경에서 프로젝트에 대 한 데이터를 다시 로드 됩니다. 편집기를 통해 디스크에서 데이터를 다시 로드 해야 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> 구현 합니다. 두 경우 모두에서 데이터를 다시 로드 프로젝트 또는 편집기에서 상황에 맞는 변경할 수 있습니다.

 적절 한 영어를 복잡 하 고 어려운 작업 `IVsQueryEditQuerySave2::QueryEditFiles` 기존 코드 베이스를 호출 합니다. 결과적으로, 프로젝트 또는 편집기를 만드는 동안 이러한 호출을 통합 해야 합니다.

## <a name="request-permission-to-save-a-file"></a>파일을 저장할 수 있는 권한을 요청
 프로젝트 또는 편집기 파일을 저장 하기 전에 호출 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>합니다. 프로젝트 파일에 대해 이러한 호출은 프로젝트 파일을 저장 하는 시기를 알고 있는 솔루션에서 자동으로 완료 됩니다. 편집기는 하지 않는 한 이러한 호출을 수행 하는 일을 담당 편집기 구현 `IVsPersistDocData2` 도우미 함수를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>합니다. 편집기를 구현 하는 경우 `IVsPersistDocData2` 이러한 방식으로 다음에 대 한 호출에서 `IVsQueryEditQuerySave2::QuerySaveFile` 또는 `IVsQueryEditQuerySave2::QuerySaveFiles` 만들어집니다.

> [!NOTE]
>  항상 이러한 호출을 선점 하 여 확인-즉, 편집기가 취소를 받을 수는 경우 한 번에 있습니다.

## <a name="request-permission-to-add-remove-or-rename-files-in-the-project"></a>추가, 제거 또는 프로젝트의 파일 이름을 바꿀 수 있는 권한을 요청합니다
 프로젝트 추가 수, 이름 바꾸기 또는 파일이 나 디렉터리를 제거 하기 전에 적절 한 호출 해야 `IVsTrackProjectDocuments2::OnQuery*` 환경에서 권한 요청 하는 메서드. 권한이 부여 되 면 프로젝트 작업을 완료 한 다음 적절 한를 호출 해야 `IVsTrackProjectDocuments2::OnAfter*` 작업이 완료 되는 환경에 알리기 위해 메서드. 프로젝트의 메서드를 호출 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 모든 파일 (예를 들어 특수 파일) 및 뿐 아니라 부모 파일에 대 한 인터페이스입니다. 파일 호출은 필수 이지만 디렉터리 호출 옵션입니다. 프로젝트 디렉터리 정보에 경우 적절 한 호출 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 메서드 하지만이 정보가 없는 경우 환경을 디렉터리 정보를 유추 합니다.

 프로젝트의 메서드를 호출 하지 않아야 `IVsTrackProjectDocuments2` 프로젝트에서 열기 또는 닫기 합니다. 시작 시이 정보를 수신기에 대 한까지 대기할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A> 이벤트 고 필요한 정보를 찾기 위해 솔루션 전체를 반복 합니다. 이 정보는 종료 필요 하지 않습니다. `IVsTrackProjectDocuments2` 제공 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>합니다.

 각 추가, 이름 바꾸기 및 제거 작업에 대 한 없는 `OnQuery*` 메서드 및 `OnAfter*` 메서드. 호출 된 `OnQuery*` 를 추가할 수 있는 권한을 요청 하는 메서드 이름을 바꾸거나 파일 또는 디렉터리를 제거 합니다. 호출 된 `OnAfter*` 메서드, 파일 또는 디렉터리가 추가 또는 이름이 바뀌었거나, 제거 되었습니다. 새 상태를 반영 하는 프로젝트 상태 후입니다.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>
- [소스 제어 지원](../../extensibility/internals/supporting-source-control.md)
---
title: "소스 제어에 대 한 구성 세부 정보 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 [Visual Studio SDK] 구성 세부 정보"
ms.assetid: adbee9fc-7a2e-4abe-a3b8-e6615bcd797f
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 소스 제어에 대 한 구성 세부 정보
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어를 구현 하기 위해 올바르게 프로젝트 시스템 또는 편집기에는 다음 작업을 수행을 구성 해야 합니다.  
  
-   변경 된 상태로 전환 하려면 사용 권한 요청  
  
-   파일을 저장 하려면 사용 권한 요청  
  
-   추가, 제거 또는 프로젝트의에서 파일 이름을 바꿀 수 있는 권한을 요청 합니다.  
  
## 변경 된 상태로 전환 하려면 사용 권한 요청  
 프로젝트 또는 편집기 전환 변경 된 \(더티\) 상태에 대 한 사용 권한을 호출 하 여 요청 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>.  구현 하는 각 편집기 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty%2A> 를 호출 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> 수신 승인을 반환 하기 전에 해당 환경에서 문서를 변경 하 고 `True` 에 대 한 `M:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData.IsDocDataDirty(System.Int32@)`.  프로젝트 편집기 프로젝트 파일에 대 한 기본적으로 하 고 그 결과 해당 파일을 텍스트 편집기에서 프로젝트 파일에 대 한 상태 변경 추적을 구현 같은 책임.  환경 솔루션의 변경 된 상태를 처리 하지만 솔루션 참조 되지만 프로젝트 파일 또는 해당 항목을 다음과 같이 저장 하지 않습니다 모든 개체의 변경 된 상태를 처리 해야 합니다.  프로젝트 편집기 또는 지 속성 항목에 대 한 관리를 담당 하는 경우 일반적으로 다음 상태 변경 추적을 구현 하는 데 담당 합니다.  
  
 에 응답 하는 `IVsQueryEditQuerySave2::QueryEditFiles` 전화 통화를 환경에서 다음을 수행할 수 있습니다.  
  
-   변경에 대 한 호출을 거부, 변경 되지 않은 \(원래\) 상태에서 편집기 또는 프로젝트 경우에 남아 있어야 합니다.  
  
-   문서 데이터를 다시 로드 하도록 지정 합니다.  프로젝트에 대 한 환경에서 프로젝트의 데이터를 다시 로드 합니다.  편집기를 통해 디스크에서 데이터를 다시 로드 해야 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2.ReloadDocData%2A> 구현 합니다.  두 경우 모두에서 데이터를 다시 로드 하는 프로젝트 또는 편집기에서 변경할 수 있습니다.  
  
 적절 한 개조 하는 복잡 하 고 어려운 작업입니다 `IVsQueryEditQuerySave2::QueryEditFiles` 는 기존의 코드 베이스를 호출 합니다.  따라서 이러한 호출은 편집기 또는 프로젝트를 만드는 동안 통합 되어야 합니다.  
  
## 파일을 저장 하려면 사용 권한 요청  
 프로젝트 또는 편집기를 파일을 저장 하기 전에 호출 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>.  프로젝트 파일에 대 한 이러한 호출 자동으로 프로젝트 파일을 저장 하는 시기를 알 수 있는 솔루션으로 완료 됩니다.  편집기입니다 하지 않는 한 이러한 호출을 수행 합니다 편집기 구현 `IVsPersistDocData2` 도우미 함수를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>.  편집기를 구현 하는 경우 `IVsPersistDocData2` 에서이 방식으로 다음 호출을 `IVsQueryEditQuerySave2::QuerySaveFile` 또는 `IVsQueryEditQuerySave2::QuerySaveFiles` 만들어집니다.  
  
> [!NOTE]
>  항상 이러한 호출을 선점형으로 사용자가\-즉, 편집기가 취소를 받을 수 있을 때 한 번에.  
  
## 추가, 제거 또는 프로젝트의에서 파일 이름을 바꿀 수 있는 권한을 요청 합니다.  
 프로젝트 추가, 이름 바꾸기 또는 파일 또는 디렉터리를 제거 하기 전에 적절 한 호출 해야 `IVsTrackProjectDocuments2::OnQuery*` 환경에서 메서드 사용 권한 요청을 합니다.  권한을 허가 후 프로젝트 작업을 완료 하 고 적절 한 호출 해야 하는 경우 `IVsTrackProjectDocuments2::OnAfter*` 메서드는 환경 작업을 완료 했음을 알립니다.  프로젝트의 메서드를 호출 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 는 부모 파일 및 모든 파일 \(예를 들어, 특정 파일\)에 대 한 인터페이스입니다.  파일 호출 필수 인지 하지만 디렉터리 호출 선택 사항입니다.  프로젝트 디렉터리 정보가 들어 있는 경우 적절 한 호출 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 메서드를 있지만이 정보가 없는 경우 환경 디렉터리 정보를 유추 합니다.  
  
 프로젝트의 메서드를 호출 해야 합니다 `IVsTrackProjectDocuments2` 에서 프로젝트를 열거나 닫습니다.  시작할 때이 정보를 수신기에 대 한 대기 수를 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A> 이벤트가 필요한 정보를 찾을 수 있는 솔루션을 통해 반복 하 고 있습니다.  시스템 종료에이 정보가 필요 하지 않습니다.  `IVsTrackProjectDocuments2`제공 되는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>.  
  
 각 추가, 이름 바꾸기 및 제거 작업에는 `OnQuery*` 메서드 및 `OnAfter*` 메서드.  호출 하는 `OnQuery*` 메서드를 추가할 수 있는 권한을 요청 하려면 이름 바꾸기 또는 파일 또는 디렉터리를 제거 합니다.  호출 하는 `OnAfter*` 파일 또는 디렉터리가 추가 되거나 이름이 변경 되거나 제거 하 고 새 상태로 프로젝트 상태를 반영 하는 메서드.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFiles%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell.SaveDocDataToFile%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>   
 [소스 제어를 지원합니다.](../../extensibility/internals/supporting-source-control.md)
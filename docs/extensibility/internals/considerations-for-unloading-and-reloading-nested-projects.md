---
title: "중첩된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중첩된 프로젝트를 언로드한 후 다시 로드"
  - "프로젝트 [Visual Studio SDK] 언로드 및 중첩 다시 로드"
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 중첩된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

중첩 된 프로젝트 형식을 구현 하는 경우 프로젝트를 다시 로드 하 고 언로드할 때 추가 단계를 수행 해야 합니다.  솔루션 이벤트 리스너를 제대로 알리려면를 정확 하 게 올려야 합니다는 `OnBeforeUnloadProject` 및 `OnAfterLoadProject` 이벤트입니다.  
  
 이러한 이벤트를 이런 방식이으로 발생 해야 하는 이유 중 하나는 소스 코드 제어 \(SCC\) 서버에서 항목을 삭제 한 다음 다시 무언가로 경우 새 추가 하기를 원하지는 `Get` 소스 코드 제어에서 작업 합니다.  이 경우 SCC의 새 파일이 로드 됩니다 및 다른 지 하는 경우 모든 파일을 언로드한 다음 다시 로드 해야 합니다.  소스 코드 제어 호출 `ReloadItem`.  해당 호출 구현 프로젝트를 삭제 하 고 다시 구현 하 여 다시 하는 것 `IVsFireSolutionEvents` 호출 하려면 `OnBeforeUnloadProject` 및 `OnAfterLoadProject`.  이 구현을 수행 하는 경우 SCC 프로젝트 일시적으로 삭제 하 고 다시 추가 하도록 알림을 받습니다.  따라서 SCC 프로젝트 되었습니다 및 서버에서 삭제 된 다음 다시 추가 것 처럼 프로젝트에서 작동 하지 않습니다.  
  
## 프로젝트를 다시 로드합니다.  
 중첩 된 프로젝트를 다시 로드 하려면 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> 메서드.  사용자의 구현에서 `ReloadItem`, 중첩 된 프로젝트를 닫은 다음 다시 만듭니다.  
  
 IDE는 프로젝트를 다시 로드 하면 발생 하는 일반적으로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> 및 `M:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject(Microsoft.VisualStudio.Shell.Interop.IVsHierarchy,Microsoft.VisualStudio.Shell.Interop.IVsHierarchy)` 이벤트입니다.  그러나, 삭제 하 고 다시 로드 합니다 중첩 된 프로젝트의 부모 프로젝트 않은 IDE 프로세스를 시작 합니다.  부모 프로젝트 솔루션 이벤트를 발생 시 키 지 및 IDE 프로세스를 초기화 하는 방법에 대 한 정보가 없습니다 있습니다 때문에 이벤트가 발생 하지 않습니다.  
  
 이 프로세스에는 부모 프로젝트 호출을 처리할 수 `QueryInterface` 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> 오프 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> 인터페이스.  `IVsFireSolutionEvents`IDE를 발생 하도록 지시 하는 함수가 포함 되어 있는 `OnBeforeUnloadProject` 중첩된 프로젝트를 언로드하고 후 발생 하는 이벤트는 `OnAfterLoadProject` 같은 프로젝트를 다시 로드 하는 이벤트.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 [중첩 프로젝트](../../extensibility/internals/nesting-projects.md)
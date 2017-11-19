---
title: "프로젝트 언로드 및 다시 로드에 대 한 고려 사항에 중첩 된 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf34a3fe708a6ecab200262224da395b9fa37ecb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>중첩 된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항
중첩 된 프로젝트 형식을 구현할 때 언로드되고 프로젝트 다시 로드 하는 경우 추가 단계를 수행 해야 합니다. 수신기 솔루션 이벤트를 알릴 올바르게를 올바르게 올려야는 `OnBeforeUnloadProject` 및 `OnAfterLoadProject` 이벤트입니다.  
  
 이런이 방식으로 이러한 이벤트를 발생 해야 하는 한 가지 이유는 소스 코드 제어 (SCC) 서버에서 항목을 삭제 하 고 다음 없을 경우 새로운 작업으로 다시 추가 하지 않을 `Get` SCC에서 작업 합니다. 이 경우 소스 코드 제어에서 새 파일을 로드할 수는 있으며 언로드되고 인 경우에 다른 모든 파일을 다시 로드 해야 합니다. SCC 호출 `ReloadItem`합니다. 호출을 구현 하는 프로젝트를 삭제 하 고 다시 구현 하 여 다시 만들는 `IVsFireSolutionEvents` 호출할 `OnBeforeUnloadProject` 및 `OnAfterLoadProject`합니다. 이 구현은 수행 하면 SCC는 프로젝트를 삭제 및 다시 추가 일시적으로 알림을 받습니다. 따라서 SCC 프로젝트 서버에서 실제로 삭제 되었고 다시 추가 하는 경우에 따라 프로젝트에서 작동 하지 않습니다.  
  
## <a name="reloading-projects"></a>프로젝트 다시 로드  
 중첩 된 프로젝트 다시 로드를 지원 하기 위해 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> 메서드. 구현에서 `ReloadItem`, 중첩 된 프로젝트를 닫은 다음 다시 작성 합니다.  
  
 일반적으로 프로젝트를 다시 로드 하는 경우 IDE를 발생 시킵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> 및 `M:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject(Microsoft.VisualStudio.Shell.Interop.IVsHierarchy,Microsoft.VisualStudio.Shell.Interop.IVsHierarchy)` 이벤트입니다. 그러나 부모 프로젝트를 삭제 하 고 다시 로드 하는 중첩 된 프로젝트에 대 한 IDE 하지 프로세스를 시작 합니다. 부모 프로젝트 솔루션 이벤트를 발생 시 키 지 않는 이어서 IDE에 프로세스의 초기화에 대 한 정보가 없으므로 이벤트가 발생 하지 않습니다.  
  
 이 프로세스는 부모 프로젝트에서 호출을 처리 하기 `QueryInterface` 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> 오프 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> 인터페이스입니다. `IVsFireSolutionEvents`발생 시키는 IDE에 지시 하는 함수에는 `OnBeforeUnloadProject` 중첩 된 프로젝트를 업로드 하 고 발생 한 다음 이벤트를는 `OnAfterLoadProject` 동일한 프로젝트 다시 로드 하는 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 [프로젝트 중첩](../../extensibility/internals/nesting-projects.md)
---
title: 프로젝트 언로드 및 다시 로드에 대 한 고려 사항에 중첩 된 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7f22575c4affa6e6a13ea80b32674a3e517202fb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>중첩 된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항

중첩 된 프로젝트 형식을 구현할 때 언로드되고 프로젝트 다시 로드 하는 경우 추가 단계를 수행 해야 합니다. 수신기 솔루션 이벤트를 알릴 올바르게를 올바르게 올려야는 `OnBeforeUnloadProject` 및 `OnAfterLoadProject` 이벤트입니다.

이러한 이벤트를 발생 시키는 한 가지 이유는 소스 코드 제어 (SCC)입니다. SCC는 서버에서 항목을 삭제 한 다음 추가를 하지 않으려면 변수로 다시 *새* 없을 경우는 `Get` SCC에서 작업 합니다. 이 경우 새 파일을 SCC에서 로드 됩니다. 언로드한 후 다른 하는 경우 모든 파일을 다시 로드 해야 합니다.

소스 코드 제어 호출 `ReloadItem`합니다. 구현은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> 호출할 인터페이스 `OnBeforeUnloadProject` 및 `OnAfterLoadProject` 하 프로젝트를 삭제 하 고 다시 만들어야 합니다. 이러한 방식으로 인터페이스를 구현 하는 경우 SCC는 프로젝트를 삭제 및 다시 추가 일시적으로 알림을 받습니다. 따라서 SCC는 작동 하지 않습니다는 프로젝트에서 프로젝트를 마치 *실제로* 삭제 하 고 다시 추가 합니다.

## <a name="reloading-projects"></a>프로젝트 다시 로드

중첩 된 프로젝트 다시 로드를 지원 하기 위해 구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> 메서드. 구현에서 `ReloadItem`, 중첩 된 프로젝트를 닫은 다음 다시 작성 합니다.

일반적으로 프로젝트를 다시 로드 하는 경우 IDE를 발생 시킵니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> 이벤트입니다. 그러나 부모 프로젝트 삭제 및 다시 로드 되는 중첩 된 프로젝트에 대 한 IDE 하지 프로세스를 시작 합니다. 부모 프로젝트 솔루션 이벤트를 발생 하지 않음 이어서 IDE에 프로세스의 초기화에 대 한 정보가 없으므로 이벤트 발생 하지 않습니다.

이 프로세스는 부모 프로젝트에서 호출을 처리 하기 `QueryInterface` 에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> 인터페이스입니다. `IVsFireSolutionEvents` 발생 시키는 IDE에 지시 하는 함수에는 `OnBeforeUnloadProject` 중첩 된 프로젝트를 업로드 하 고 발생 한 다음 이벤트를는 `OnAfterLoadProject` 동일한 프로젝트 다시 로드 하는 이벤트입니다.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- [프로젝트 중첩](../../extensibility/internals/nesting-projects.md)
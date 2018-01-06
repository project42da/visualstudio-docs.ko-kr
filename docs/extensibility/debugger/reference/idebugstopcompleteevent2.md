---
title: IDebugStopCompleteEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5d59de29078db46f716fe9d01a3f3fa076139ddf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
디버그 엔진 (DE) 프로그램이 중지 될 때이 선택적 이벤트 (SDM)의 세션 디버그 관리자에 게 보낼 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 이 새로운 인터페이스는 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)]합니다. 이전 릴리스의 비동기 중지를 지원 하지 않았습니다.  
  
 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) 다중 프로세스 또는 다중 프로그램 시나리오에서 SDM에 의해 호출 됩니다. 한 프로그램 중지 이벤트를 보내면은 SDM은 SDM 너무을 중지 하려면 다른 프로그램을 요청 합니다.  
  
 비동기적으로 프로그램이 중지 SDM를 알리기 위해 사용 됩니다. 이 기능은 유용 인터프리터 디버그 엔진의 경우 때로는 코드가 실행 되 고 있는 디버깅된 프로그램 내, 하므로 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) 동기적으로 완료할 수 없습니다. 반환 해야 하는 경우이 비동기 알림을 사용 하 여 디버그 엔진이, `S_ASYNC_STOP` 에서 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll
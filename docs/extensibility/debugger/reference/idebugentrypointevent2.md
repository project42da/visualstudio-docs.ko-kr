---
title: IDebugEntryPointEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEntryPointEvent2
helpviewer_keywords:
- IDebugEntryPointEvent2 interface
ms.assetid: a15d1cc3-97b7-438c-8d24-c23149708f42
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 194db40a0f73d998d5bf944fde42f09cd7f97b7d
ms.lasthandoff: 04/05/2017

---
# <a name="idebugentrypointevent2"></a>IDebugEntryPointEvent2
디버그 엔진 (DE)는 프로그램 사용자 코드의 첫 번째 명령 실행 되려고 할 때이 인터페이스를 세션 디버그 관리자 (SDM)를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEntryPointEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE의 정상 작업의 일부로이 인터페이스를 구현합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다. SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들어 디버깅 중인 프로그램 로드 하 고 사용자 코드의 첫 번째 명령 실행 하도록 준비 되어이 이벤트 개체를 보냅니다. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결할 때는 SDM에서 제공 되는 콜백 함수입니다.  
  
## <a name="remarks"></a>주의  
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md) 프로그램 첫 번째 명령을 실행 하려고 할 때 전송 됩니다. 예를 들어 `IDebugEntryPoint2` 프로그램 사용자의 실행 되려고 할 때 보내집니다 `main` 함수입니다.  
  
 DE를 보낼 때 `IDebugEntryPointEvent2`, 현재 코드 위치에 있어야 사용자 코드의 첫 번째 명령 같은 `main`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)

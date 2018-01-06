---
title: IDebugOutputStringEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugOutputStringEvent2
helpviewer_keywords: IDebugOutputStringEvent2 interface
ms.assetid: 86596fd1-cecc-4813-8add-dc3d70068f9b
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f222df8aa2a6fc35db08ceae3e8f49dfe7537960
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugoutputstringevent2"></a>IDebugOutputStringEvent2
이 인터페이스는 디버그 엔진 (DE)에 의해 세션 디버그 관리자 (SDM)를 출력으로 보내고 문자열  
  
## <a name="syntax"></a>구문  
  
```  
IDebugOutputStringEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 문자열을 보내는이 인터페이스를 구현 하는 **출력** IDE의 창. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다. SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE을 만들고이 이벤트 개체를 문자열 보내는 보냅니다는 **출력** 창. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 될 때은 SDM에서 제공 되는 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugOutputStringEvent2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetString](../../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)|표시할 수 있는 메시지를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 예를 들어 비관리 코드에서 문자열에 출력을 가져올 수 있습니다 때 디버깅 중인 프로그램 win32 문자열을 보냅니다 `OutputDebugString` 함수입니다. 이 문자열은는 DE에 의해 차단 되 고으로 SDM 게는 `IDebugOutputStringEvent2` 이벤트입니다.  
  
 사용 하 여 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md) 사용자 응답을 필요로 하는 메시지를 보내려고 합니다.  
  
 사용 하 여 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md) 응답 필요 하지 않은 오류 메시지를 보내려고 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
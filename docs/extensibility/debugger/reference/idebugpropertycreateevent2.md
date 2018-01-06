---
title: IDebugPropertyCreateEvent2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPropertyCreateEvent2
helpviewer_keywords: IDebugPropertyCreateEvent2 interface
ms.assetid: 33b3082b-a42e-488a-a1e4-dadf506f922c
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0557fd39d21415dfddb1a571c4f9e6ee69badf10
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpropertycreateevent2"></a>IDebugPropertyCreateEvent2
이 인터페이스는 세션 디버그 관리자 (SDM) 특정 문서와 연결 된 속성을 만들 때 디버그 엔진 (DE)에 의해 보내집니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPropertyCreateEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 속성이 이미 만들었다고 보고 하기 위해이 인터페이스를 구현 합니다. [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 해당이 인터페이스와 같은 개체에 대해 인터페이스를 구현 해야 합니다. SDM 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 액세스로는 `IDebugEvent2` 인터페이스입니다. 이 인터페이스는 DE가 로드 또는 생성 된 스크립트와 연결 된 속성을 생성 하 고 해당 스크립트는 IDE에 표시 해야 하는 경우에 구현 됩니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 DE 만들고이 이벤트 개체 속성이 생성 된 보고서를 전송 합니다. 이벤트를 사용 하 여 보내집니다는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 될 때은 SDM에서 제공 되는 콜백 함수입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에의 메서드는 `IDebugPropertyCreateEvent2` 인터페이스입니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md)|새 속성을 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 특정 문서 또는 연결 된 스크립트 속성이 있으면는 DE를 보낼 수 있습니다이 이벤트는 SDM 업데이트 하기 위해는 **스크립트 문서** 문서의 이름이 있는 창입니다. SDM를 호출 합니다 [GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md) 인수와 함께 `guidDocument` 검색 하는 `VARIANT` 포함 하는 [IUnknown](/cpp/atl/iunknown) 포인터입니다. SDM를 호출 합니다 [QueryInterface](/cpp/atl/queryinterface) 검색에 대 한 포인터이 고 [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 업데이트 하는 데 사용 되는 인터페이스는 **스크립트 문서** 창.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
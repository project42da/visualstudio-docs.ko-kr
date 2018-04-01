---
title: IDebugQueryEngine2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugQueryEngine2
helpviewer_keywords:
- IDebugQueryEngine2 interface
ms.assetid: 8f0e1838-a818-4459-9138-a3dceb7408de
caps.latest.revision: 11
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a54b6f6ab5667993553074f1ca2511a544a0eaea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugqueryengine2"></a>IDebugQueryEngine2
이 인터페이스에는 디버그 관리자 (SDM) 디버그 엔진 (DE)을 나타내는 인터페이스를 검색 하는 세션 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugQueryEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE는 가장 일반적인 DE 인터페이스를 구현 하는 개체에서이 인터페이스를 구현 (예: [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md), [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md), 및 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md))에서 에 대 한 액세스를 허용 하는 순서는 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) DE 자체의 인터페이스입니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [QueryInterface](/cpp/atl/queryinterface) 이 인터페이스를 가져올 수 있는 일반적인 DE 인터페이스에 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugQueryEngine2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetEngineInterface](../../../extensibility/debugger/reference/idebugqueryengine2-getengineinterface.md)|사용자 지정 디버그 엔진 (DE) 인터페이스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 일반적으로 구현 하는 개체에 구현 된 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 함수를 단계별로 실행 하면 인과 관계 주문, 즉, 디버거는 실행 함수를 종료 하는 경우를 지원 하기 위해 인터페이스는 다음 함수를 실행할 아닐 수도 있습니다는 이전 함수 스택에 수 있지만 다른 스레드의 함수 모두. "인과 관계"의 정의 참조 하십시오.는 [Visual Studio 디버거 용어집](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
---
title: IEnumDebugThreads2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugThreads2
helpviewer_keywords: IEnumDebugThreads2
ms.assetid: 1854f078-3b49-42c2-b65b-33e3b506fd63
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: b03d9adbec92986ea8a1cf0f589bd451107a611f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugthreads2"></a>IEnumDebugThreads2
이 interfac 현재 디버그 세션에서 실행 중인 스레드를 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IEnumDebugThreads2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 디버그 엔진 (DE)는 프로그램의 스레드 목록을 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md) 모든 스레드는 프로세스에서 실행 중인 모든 응용 프로그램에서의 목록을 나타내는이 인터페이스를 가져올 수 있습니다. 호출 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) 프로그램에서 실행 되는 스레드의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IEnumDebugThreads2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)|열거형 시퀀스에 있는 스레드의 지정된 된 수를 검색 합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugthreads2-skip.md)|열거형 시퀀스에 있는 스레드의 지정 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugthreads2-reset.md)|열거형 시퀀스 시작 부분으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugthreads2-clone.md)|현재 같은 열거형 상태를 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugthreads2-getcount.md)|열거자의 스레드 수를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 Visual Studio에는 일반적으로 업데이트 하려면이 인터페이스를 가져옵니다는 **스레드** 목록의 첫 번째 스레드가 호출 하기 위해 얻을 창 [Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md), [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md), 및 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)   
 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md)   
 [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md)   
 [실행](../../../extensibility/debugger/reference/idebugprocess3-execute.md)
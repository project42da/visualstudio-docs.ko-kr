---
title: IDebugModule3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugModule3
helpviewer_keywords:
- IDebugModule3 interface
ms.assetid: 44f8e96e-9c59-4ffc-9a08-9c908a0e4de7
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
ms.openlocfilehash: 8d06621cc46499d763fd16797813d9dd71e9fdfb
ms.lasthandoff: 04/05/2017

---
# <a name="idebugmodule3"></a>IDebugModule3
이 인터페이스는 기호와 JustMyCode 상태의 대체 위치를 지원 하는 모듈을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugModule3 : IDebugModule2  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 대체 위치를 지원 하 고 JustMyCode 상태를 작성 하려면이 인터페이스를 구현 하는 디버그 엔진 (DE) (참조는 [Visual Studio 디버거 용어집](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md) "JustMyCode"의 정의 대 한).  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md) 이 인터페이스를 반환 합니다. DE 보냅니다는 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md) 인터페이스를 사용 하 여 세션 디버그 관리자 (SDM)는 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 메서드. 에 대 한 호출 또한 [QueryInterface](/cpp/atl/queryinterface) 에 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 인터페이스는이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 메서드 외에도 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)|기호 및 각 경로 검색 결과를 검색 하는 경로 목록을 반환 합니다.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)|로드 하 고 현재 모듈에 대 한 기호를 초기화 합니다.|  
|[IsUserCode](../../../extensibility/debugger/reference/idebugmodule3-isusercode.md)|모듈 사용자 코드를 나타내는지 여부를 지정 하는 반환 플래그입니다.|  
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugmodule3-setjustmycodestate.md)|고려할지 여부를 모듈 사용자 코드 여부를 지정 합니다.|  
  
## <a name="remarks"></a>주의  
 Visual Studio는이 인터페이스의 일반 소비자입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [IDebugSymbolSearchEvent2](../../../extensibility/debugger/reference/idebugsymbolsearchevent2.md)   
 [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)

---
title: IDebugProgramEx2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramEx2
helpviewer_keywords:
- IDebugProgramEx2 interface
ms.assetid: 663359ed-635a-4539-addb-0cc52f19d1bd
caps.latest.revision: 18
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
ms.openlocfilehash: 55781c5d1f0fc15c505394fb08291a058de71247
ms.lasthandoff: 04/05/2017

---
# <a name="idebugprogramex2"></a>IDebugProgramEx2
이 인터페이스를 사용 하면 세션을 디버그 관리자 (SDM) 프로그램에 연결 하 고 프로그램과 연결 된 프로그램 노드를 가져오고 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 와 같은 개체에 대해이 인터페이스를 구현 하는 사용자 지정 포트 공급자는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 는 프로그램에 연결 된 모든 세션을 추적 포트 공급자 기능을 제공에 있는 동안 프로그램에 연결 SDM 수 있도록 하는 인터페이스입니다. 사용자 지정 포트 공급자 중에서 선택한 경우이 인터페이스를 구현할 수 있습니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 SDM 호출 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugProgram2` 인터페이스 프로그램에 연결 되어 있는 세션을 추적 하려면이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProgramEx2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)|세션에는 프로그램을 연결합니다.|  
|[GetProgramNode](../../../extensibility/debugger/reference/idebugprogramex2-getprogramnode.md)|프로그램과 연결 된 프로그램 노드를 가져옵니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스는 SDM와 프로그램 간의 비공개입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)

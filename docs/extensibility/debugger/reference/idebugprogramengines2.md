---
title: IDebugProgramEngines2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramEngines2
helpviewer_keywords:
- IDebugProgramEngines2 interface
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
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
ms.openlocfilehash: b1feaad2478a39799dfc9239cef288553120bd6d
ms.lasthandoff: 04/05/2017

---
# <a name="idebugprogramengines2"></a>IDebugProgramEngines2
프로그램 노드가 모든 가능한 있는 디버그 엔진 (DE)이이 프로그램을 디버깅할 수를 지정 하려면이 인터페이스를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProgramEngines2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 DE 또는 사용자 지정 포트 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 를 특정 프로그램에 사용할 특정 DE을 지원 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugProgramNode2` 인터페이스가이 인터페이스를 가져올 수 있습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugProgramEngines2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|이 프로그램을 디버깅할 수 있는 모든 가능한 DEs를 나타냅니다.|  
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|이 프로그램을 디버깅에 사용할 DE를 선택 합니다.|  
  
## <a name="remarks"></a>주의  
 선택 항목을 호출 하 여 등록 된 프로그램 노드는 DE를 사용자가 선택 되 면 [SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)합니다. 선택한 엔진에서 반환한 엔진은 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)

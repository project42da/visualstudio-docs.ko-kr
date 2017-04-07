---
title: IDebugProviderProgramNode2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
caps.latest.revision: 8
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
ms.openlocfilehash: 55cccc52e968dd3553c55a9aedb2fb838bd06093
ms.lasthandoff: 04/05/2017

---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
이 인터페이스를 프로세스 경계를 넘어 프로그램 관련 인터페이스를 마샬링합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugProviderProgramNode2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 구현 하는 동일한 개체에서이 인터페이스를 구현 하는 디버그 엔진 (DE) [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 프로세스 경계를 넘어 마샬링 인터페이스를 지원 하도록 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 호출 [QueryInterface](/cpp/atl/queryinterface) 에 `IDebugProgramNode2` 인터페이스가이 인터페이스를 가져올 수 있습니다. 이 인터페이스를 가져올 수 없는 경우는 DE 인터페이스의 마샬링을 지원 하지 않습니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|프로세스 경계에 걸쳐 지정된 된 인터페이스를 가져옵니다.|  
  
## <a name="remarks"></a>설명  
 DE 디버깅 중인 프로그램에서 별도 프로세스 공간에서 실행 될 때이 인터페이스는 구현:는 DE 디버깅 중인 프로그램의 프로세스 공간 대신 Visual Studio 프로세스 공간에서 실행 중인 경우에 예를 들어 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

---
title: IDebugPortSupplier2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortSupplier2
helpviewer_keywords: IDebugPortSupplier2 interface
ms.assetid: 37067324-2ea6-4a01-8829-a6e9c7a70068
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 257bbf334adbdfd3a93cf172de0b15bf63cb3217
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportsupplier2"></a>IDebugPortSupplier2
이 인터페이스는 포트 세션 디버그 관리자 (SDM)를 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugPortSupplier2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 사용자 지정 포트 공급자 포트 공급자를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 에 대 한 호출 `CoCreateInstance` 포트 공급 업체와 `GUID` (이것이이 인터페이스를 검색 하는 일반적인 방법)이이 인터페이스를 반환 합니다. 예:  
  
```cpp  
IDebugPortSupplier2 *GetPortSupplier(GUID *pPortSupplierGuid)  
{  
    IDebugPortSupplier2 *pPS = NULL;  
    if (pPortSupplierGuid != NULL) {  
        CComPtr<IDebugPortSupplier2> spPortSupplier;  
        spPortSupplier.CoCreateInstance(*pPortSupplierGuid);  
        if (spPortSupplier != NULL) {  
            pPS = spPortSupplier.Detach();  
        }  
    }  
    return (pPS);  
}  
```  
  
 에 대 한 호출 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md) 이 인터페이스를 사용 하 고 현재 포트 공급 업체를 나타내는 반환 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md) 만든 포트를 포트 공급 업체를 나타내는이 인터페이스를 반환 합니다.  
  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md) 의 목록을 나타냅니다. `IDebugPortSupplier` 인터페이스 (의 `IEnumDebugPortSuppliers` 인터페이스에서 가져온 [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md), 등록 된모든포트공급자를나타내는[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]).  
  
 디버그 엔진 일반적으로 상호 작용 하지 않습니다 포트 공급자입니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 다음 표에서의 메서드를 보여 줍니다. `IDebugPortSupplier2`합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetPortSupplierName](../../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)|포트 공급 업체 이름을 가져옵니다.|  
|[GetPortSupplierId](../../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)|포트 공급 업체 식별자를 가져옵니다.|  
|[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)|포트 공급 업체에서 포트를 가져옵니다.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)|이미 존재 하는 포트를 열거 합니다.|  
|[CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)|포트 공급자에서는 새 포트를 추가할 수 있는지 확인 합니다.|  
|[포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)|포트를 추가합니다.|  
|[RemovePort](../../../extensibility/debugger/reference/idebugportsupplier2-removeport.md)|포트를 제거 합니다.|  
  
## <a name="remarks"></a>설명  
 포트 공급자 이름 및 ID로 자신을 식별, 추가 및 포트를 제거 및 포트 공급자를 제공 하는 모든 포트 열거.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)   
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
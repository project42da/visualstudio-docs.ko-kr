---
title: "IDebugPortSupplier2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2"
helpviewer_keywords: 
  - "IDebugPortSupplier2 인터페이스"
ms.assetid: 37067324-2ea6-4a01-8829-a6e9c7a70068
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugPortSupplier2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 포트 세션 디버그 매니저 \(SDM\)을 제공합니다.  
  
## 구문  
  
```  
IDebugPortSupplier2 : IUnknown  
```  
  
## 구현자 참고 사항  
 포트 공급자를 나타내는 데이 인터페이스를 구현 하는 포트 사용자 지정 협력 업체.  
  
## 호출자에 대 한 참고 사항  
 호출을 `CoCreateInstance` 포트 공급 업체와 `GUID` \(이것은이 인터페이스를 가져올 수 있는 일반적인 방법\)이이 인터페이스를 반환 합니다.  예를 들면 다음과 같습니다.  
  
```cpp#  
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
  
 호출을 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md) 이 인터페이스를 사용 하 고 현재 포트 공급 업체를 나타내는이 반환 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].  
  
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)포트를 만든 포트 공급자를 나타내는이 인터페이스를 반환 합니다.  
  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)목록을 나타내는 `IDebugPortSupplier` 인터페이스 \(는 `IEnumDebugPortSuppliers` 에서 얻은 인터페이스 [EnumPortSuppliers](../../../extensibility/debugger/reference/idebugcoreserver2-enumportsuppliers.md), 모든 포트 공급자를 나타내는 등록 하 여 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]\).  
  
 일반적으로 디버그 엔진 포트 협력 업체와 상호 작용 하지 않습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPortSupplier2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetPortSupplierName](../../../extensibility/debugger/reference/idebugportsupplier2-getportsuppliername.md)|포트 공급자 이름을 가져옵니다.|  
|[GetPortSupplierId](../../../extensibility/debugger/reference/idebugportsupplier2-getportsupplierid.md)|포트 공급자 식별자를 가져옵니다.|  
|[GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md)|포트를 포트 공급자를 가져옵니다.|  
|[EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)|이미 존재 하는 포트를 열거 합니다.|  
|[CanAddPort](../../../extensibility/debugger/reference/idebugportsupplier2-canaddport.md)|포트 공급자 새 포트를 추가 지원 하는지 확인 합니다.|  
|[포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)|포트를 추가합니다.|  
|[RemovePort](../../../extensibility/debugger/reference/idebugportsupplier2-removeport.md)|포트를 제거합니다.|  
  
## 설명  
 포트 공급자 수 있습니다 자체 이름과 ID에 의해 식별, 추가 및 포트, 제거 하 고 포트 공급자를 제공 하는 모든 포트를 열거 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)   
 [GetPortSupplier](../../../extensibility/debugger/reference/idebugcoreserver2-getportsupplier.md)   
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
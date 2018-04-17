---
title: IDebugAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugAddress
helpviewer_keywords:
- IDebugAddress interface
ms.assetid: bc709ff7-4966-4f36-9af2-690efe2cea1d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ace2892d4518de8c5a4abaa2c113df914f9fa6b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugaddress"></a>IDebugAddress
이 인터페이스는 항목의 주소를 나타냅니다. 기호 처리기에 의해 반환 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugAddress : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자 개체의 주소를 나타내는 데이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 여러 인터페이스에서 대부분의 메서드는이 인터페이스를 반환 합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)|검색 한 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md) 개체와 해당 위치를 설명 하는 구조입니다.|  
  
## <a name="remarks"></a>설명  
 기호 공급자를 나타내는 개체와 해당 위치 (예: 함수, 메서드 또는 클래스)의 특정 범위 내에서이 인터페이스를 반환 합니다. 이 인터페이스에서 반환 되어 기호 공급자과 식의 다양 한 방법에 전달 된 계산기 합니다. 일반적으로 기호 공급자는이 인터페이스의 내용을 해석 하는 유일한 엔터티입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)
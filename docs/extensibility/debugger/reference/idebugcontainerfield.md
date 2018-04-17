---
title: IDebugContainerField | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugContainerField
helpviewer_keywords:
- IDebugContainerField interface
ms.assetid: a8bbe061-c382-4fe9-a193-3f7d12216041
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bee04d21e3181d4590f26b64c794164ab1a84b6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcontainerfield"></a>IDebugContainerField
이 인터페이스는 기호 또는 다른 기호 또는 형식에 대 한 컨테이너 형식을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugContainerField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 하는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스입니다. 이 인터페이스 컨테이너를 나타내는 모든 인터페이스에 대 한 기본 클래스 이기도 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 여러 인터페이스에서 대부분의 메서드는이 인터페이스를 반환 합니다. 더욱 특수화 된 인터페이스를 사용 하 여이 인터페이스에서 가져온 모든 컨테이너에 대 한 기본 클래스 이므로 [QueryInterface](/cpp/atl/queryinterface)합니다. 이러한 인터페이스 포함 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md), [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), 및 [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)합니다.  
  
## <a name="methods-in-vtable-order"></a>Vtable 순서의 메서드  
 에 메서드 외에도 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)|컨테이너의 필드에 대 한 열거자를 만듭니다.|  
  
## <a name="remarks"></a>설명  
 배열 (변수에 대 한 컨테이너), (메서드 및 변수에 대 한 컨테이너) 클래스 및 메서드 (매개 변수 및 지역 변수 컨테이너)은 컨테이너의 모든 예입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
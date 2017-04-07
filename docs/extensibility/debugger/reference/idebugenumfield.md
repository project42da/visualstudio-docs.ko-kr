---
title: IDebugEnumField | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugEnumField
helpviewer_keywords:
- IDebugEnumField interface
ms.assetid: 42f685bf-0f39-47f4-98b0-6022efe2bf97
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
ms.openlocfilehash: a4040577cc6d51cedc10fcb641c7aca18fa51c14
ms.lasthandoff: 04/05/2017

---
# <a name="idebugenumfield"></a>IDebugEnumField
이 인터페이스는 열거형을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
IDebugEnumField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>구현자 참고 사항  
 기호 공급자를 나타내는 열거형이이 인터페이스를 구현 합니다.  
  
## <a name="notes-for-callers"></a>호출자에 대 한 참고 사항  
 사용 하 여 [QueryInterface](/cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인터페이스 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 반환 `FIELD_TYPE_ENUM`합니다.  
  
## <a name="methods-in-vtable-order"></a>VTable 순서의 메서드  
 메서드 외에도 `IDebugField` 및 `IDebugContainerField` 인터페이스의 경우이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[GetUnderlyingSymbol](../../../extensibility/debugger/reference/idebugenumfield-getunderlyingsymbol.md)|반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 이 열거형 형식에 대 한 이름을 설명 하 합니다.|  
|[GetStringFromValue](../../../extensibility/debugger/reference/idebugenumfield-getstringfromvalue.md)|지정 된 값과 관련 된 열거형 상수의 이름을 반환 합니다.|  
|[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)|지정 된 열거형 상수 이름과 연결한 값 반환|  
|[GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)|지정 된 열거형 상수 이름은 같지만 대/소문자 무시 연관 된 값을 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 것은 실제로 있는 위치에 바인딩되는 기본 기호 [바인딩할](../../../extensibility/debugger/reference/idebugbinder-bind.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [바인딩](../../../extensibility/debugger/reference/idebugbinder-bind.md)

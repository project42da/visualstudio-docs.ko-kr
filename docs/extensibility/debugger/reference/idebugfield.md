---
title: "IDebugField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugField"
helpviewer_keywords: 
  - "IDebugField 인터페이스"
ms.assetid: adecdd1c-b1b9-4027-92da-74cbe910636f
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에는 필드를, 기호 또는 형식 설명을 나타냅니다.  
  
## 구문  
  
```  
IDebugField : IUnknown  
```  
  
## 구현자 참고 사항  
 기호 공급자 기본 클래스로 모든 필드에 대해이 인터페이스를 구현합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스는 모든 필드에 대 한 기본 클래스입니다.  반환 값에 따라 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md),이 인터페이스를 사용 하 여 보다 전문화 된 인터페이스를 반환할 수 있습니다 [QueryInterface](/visual-cpp/atl/queryinterface).  또한 많은 인터페이스를 반환 `IDebugField` 개체에서 다양 한 방법입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugField`.  
  
|메서드|설명|  
|---------|--------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)|기호 또는 형식을 표시할 수 있는 정보를 가져옵니다.|  
|[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)|필드의 종류를 가져옵니다.|  
|[GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)|필드의 형식을 가져옵니다.|  
|[GetContainer](../../../extensibility/debugger/reference/idebugfield-getcontainer.md)|필드의 컨테이너를 가져옵니다.|  
|[GetAddress](../../../extensibility/debugger/reference/idebugfield-getaddress.md)|주소를 필드를 가져옵니다.|  
|[GetSize](../../../extensibility/debugger/reference/idebugfield-getsize.md)|바이트에서 필드의 크기를 가져옵니다.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugfield-getextendedinfo.md)|확장 필드에 대 한 정보를 가져옵니다.|  
|[Equal](../../../extensibility/debugger/reference/idebugfield-equal.md)|두 필드를 비교합니다.|  
|[GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)|기호 또는 형식에 대 한 형식에 관계 없이 정보를 가져옵니다.|  
  
## 설명  
 C 언어에 해당 하는 형식인 `typedef`.  
  
 다음 c \+ \+ 언어 예제에서 `weather` 클래스 형식 및 `sunny` 및 `stormy` 기호입니다.  
  
```cpp#  
class weather;  
weather sunny;  
weather stormy;  
```  
  
 필드는 표시 여부 형식을 호출 하 여 확인할 수 있습니다 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 및 검사 하는 [FIELD\_KIND](../../../extensibility/debugger/reference/field-kind.md) 결과입니다.  경우는 `FIELD_KIND_TYPE` 비트가 설정, 필드의 형식이 경우에 `FIELD_KIND_SYMBOL` 비트가 설정, 심볼입니다.  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
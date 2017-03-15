---
title: "IDebugEnumField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEnumField"
helpviewer_keywords: 
  - "IDebugEnumField 인터페이스"
ms.assetid: 42f685bf-0f39-47f4-98b0-6022efe2bf97
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugEnumField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 열거 형식을 나타냅니다.  
  
## 구문  
  
```  
IDebugEnumField : IDebugContainerField  
```  
  
## 구현자 참고 사항  
 기호 공급자의 열거형을 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 사용 [QueryInterface](/visual-cpp/atl/queryinterface) 에서이 인터페이스를 가져올 수 있는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 경우 인터페이스 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) 반환 `FIELD_TYPE_ENUM`.  
  
## 메서드에서 VTable 순서  
 메서드 외에 `IDebugField` 및 `IDebugContainerField` 인터페이스,이 인터페이스는 다음 메서드를 구현 합니다.  
  
|메서드|설명|  
|---------|--------|  
|[GetUnderlyingSymbol](../../../extensibility/debugger/reference/idebugenumfield-getunderlyingsymbol.md)|반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 이 열거형 형식에 대 한 이름을 설명 하는.|  
|[GetStringFromValue](../../../extensibility/debugger/reference/idebugenumfield-getstringfromvalue.md)|열거형 상수는 지정 된 값과 관련 된 이름을 반환 합니다.|  
|[GetValueFromString](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstring.md)|지정 된 열거형 상수 이름과 연결 된 값을 반환|  
|[GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)|지정 된 열거형 상수 이름이 있지만 무시 대\/소문자와 관련 된 값을 반환 합니다.|  
  
## 설명  
 실제로 위치와 연결 된 기본 기호입니다 [바인딩](../../../extensibility/debugger/reference/idebugbinder-bind.md).  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [기호 공급자 인터페이스](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [바인딩](../../../extensibility/debugger/reference/idebugbinder-bind.md)
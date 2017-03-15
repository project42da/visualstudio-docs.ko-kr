---
title: "IDebugProperty2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty2"
helpviewer_keywords: 
  - "IDebugProperty2 인터페이스"
ms.assetid: a7d5c70f-a1a5-4120-9f70-184e01c25bff
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugProperty2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 스택 프레임 속성, 프로그램 문서 속성 또는 다른 속성을 나타냅니다.  이 속성은 일반적으로 식 계산의 결과입니다.  
  
> [!NOTE]
>  "속성"이이 사용 해당 멤버 변수를 클래스의 의미와 일치 하지 않습니다을 `IDebugProperty2` 와 같은 엔터티를 나타낼 수 있습니다.  
  
## 구문  
  
```  
IDebugProperty2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE의 특정 종류의 값을 나타내는 데이 인터페이스를 구현 합니다.  예를 들어, 값은 메모리 또는 레지스터 및 해당 값 목록을 표시 하는 데 사용 되는 메모리 컨텍스트 식 계산의 결과 숫자 값을 수 있습니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 또는 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 의 평가 결과 나타내는이 인터페이스를 얻을 수 있습니다.  `IDebugExpression2::EvaluateAsync`전송 하 여이 인터페이스를 반환 된 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 인터페이스를 차례로 호출 하는 SDM [GetResult](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md) 속성을 검색 합니다.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugpropertycreateevent2-getdebugproperty.md)스크립트 관련된 문서를 제공 하기 위해이 인터페이스를 반환 합니다.  
  
 [GetReturnValue](../../../extensibility/debugger/reference/idebugreturnvalueevent2-getreturnvalue.md)이 인터페이스는 함수의 반환 값을 나타내는 수를 반환 합니다.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugprogram2-getdebugproperty.md)프로그램 이름 또는 메모리 컨텍스트 등의 다양 한 속성을 나타내는 데이 인터페이스를 반환 합니다.  
  
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)스택 프레임이 로컬 변수 등의 다양 한 속성을 나타내는 데이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProperty2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md)|칠 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 속성에 설명 하는 구조입니다.|  
|[SetValueAsString](../../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md)|문자열에서 속성의 값을 설정합니다.|  
|[SetValueAsReference](../../../extensibility/debugger/reference/idebugproperty2-setvalueasreference.md)|지정한 참조의 값에서 속성의 값을 설정합니다.|  
|[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)|Children 속성을 열거합니다.|  
|[GetParent](../../../extensibility/debugger/reference/idebugproperty2-getparent.md)|속성의 부모를 반환 합니다.|  
|[GetDerivedMostProperty](../../../extensibility/debugger/reference/idebugproperty2-getderivedmostproperty.md)|최대 파생 속성의 속성을 설명 하는 속성을 반환 합니다.|  
|[GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)|속성의 값을 구성 하는 메모리 바이트 수를 반환 합니다.|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)|속성 값에 대 한 메모리 컨텍스트를 반환합니다.|  
|[GetSize](../../../extensibility/debugger/reference/idebugproperty2-getsize.md)|크기, 속성 값을 바이트 단위로 반환합니다.|  
|[GetReference](../../../extensibility/debugger/reference/idebugproperty2-getreference.md)|이 속성의이 값에 대 한 참조를 반환합니다.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugproperty2-getextendedinfo.md)|속성의 확장된 된 정보를 반환합니다.|  
  
## 설명  
 표시 된 속성은 `IDebugProperty2` 인터페이스를을 가진 이름, 종류, 및 주소 값으로 생각할 수 있습니다.  보다 일반적인 용어로 `IDebugProperty2` 부모 및 자식 노드를 계층 구조에 있는 모든 항목을 나타낼 수 있습니다.  
  
 속성은 현재 스택 프레임에만 처럼 오래 예 이며 보통 일시적인,입니다.  반면, 표시 되는 참조에 있는 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 인터페이스에서 유지 되는 값 메모리에 유지 되는.  
  
 IDE에서 사용할 수 있습니다의 `IDebugProperty2` 인터페이스를 사용자가 탐색 하 고 실행된 시에 속성을 수정 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
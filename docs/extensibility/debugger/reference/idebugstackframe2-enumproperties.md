---
title: "IDebugStackFrame2::EnumProperties | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugStackFrame2::EnumProperties"
helpviewer_keywords: 
  - "IDebugStackFrame2::EnumProperties"
ms.assetid: 334bb95e-c7e0-4008-9f06-8c3999e47ee8
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugStackFrame2::EnumProperties
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

로컬 변수 같은 스택 프레임에 관련 된 속성에 대 한 열거자를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumProperties (   
   DEBUGPROP_INFO_FLAGS      dwFieldSpec,  
   UINT                      nRadix,  
   REFIID                    refiid,  
   DWORD                     dwTimeout,  
   ULONG*                    pcelt,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```c#  
int EnumProperties (   
   enum_DEBUGPROP_INFO_FLAGS   dwFieldSpec,  
   uint                        nRadix,  
   ref Guid                    refiid,  
   uint                        dwTimeout,  
   out uint                    pcelt,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### 매개 변수  
 `dwFieldSpec`  
 \[in\] 플래그의 조합에서 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 열거에서 필드를 지정 하는 열거형 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조인 채워야 합니다.  
  
 `nRadix`  
 \[in\] 임의의 숫자 정보를 서식 지정에 사용할 기 수입니다.  
  
 `refiid`  
 \[in\] 필터를 선택 하는 데 사용 하는 GUID [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조입니다, 열거 등을 `guidFilterLocals`.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간입니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
 `pcelt`  
 \[out\] 열거 된 속성의 수를 반환 합니다.  이는 [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md) 메서드.  
  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 원하는 속성 목록을 포함 하는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 선택한 모든 속성을 한 번의 호출에서 검색 될 수 있기 때문에 순차적으로 호출 하는 것 보다 빠른 것은 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) 및 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 방법.  
  
## 참고 항목  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)   
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)
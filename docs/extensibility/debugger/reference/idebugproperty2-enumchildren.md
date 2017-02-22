---
title: "IDebugProperty2::EnumChildren | Microsoft Docs"
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
  - "IDebugProperty2::EnumChildren"
helpviewer_keywords: 
  - "IDebugProperty2::EnumChildren"
ms.assetid: cf79f666-65d1-417c-af7c-9271bac9a267
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProperty2::EnumChildren
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

자식 속성의 목록을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumChildren (   
   DEBUGPROP_INFO_FLAGS      dwFields,  
   DWORD                     dwRadix,  
   REFGUID                   guidFilter,  
   DBG_ATTRIB_FLAGS          dwAttribFilter,  
   LPCOLESTR                 pszNameFilter,  
   DWORD                     dwTimeout,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```c#  
int EnumChildren (   
   enum_DEBUGPROP_INFO_FLAGS   dwFields,  
   uint                        dwRadix,  
   ref Guid                    guidFilter,  
   uint                        dwAttribFilter,  
   string                      pszNameFilter,  
   uint                        dwTimeout,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 플래그의 조합에서 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 열거에서 필드를 지정 하는 열거형 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조인 채워야 합니다.  
  
 `dwRadix`  
 \[in\] 모든 숫자 정보를 서식 지정에 사용 되는 기 수를 지정 합니다.  
  
 `guidFilter`  
 \[in\] GUID를 사용 하는 필터를의 `dwAttribFilter` 및 `pszNameFilter` 매개 변수를 선택 `DEBUG_PROPERTY_INFO` 자식인를 열거 합니다.  예를 들어, `guidFilterLocals` 지역 변수에 대 한 필터입니다.  
  
 `dwAttribFilter`  
 \[in\] 플래그의 조합에서 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 예를 열거 하는 개체의 형식을 지정 하는 열거형 `DBG_ATTRIB_METHOD` 이 속성의 하위가 될 수 있는 모든 방법에 대 한.  함께 사용 되는 `guidFilter` 및 `pszNameFilter` 매개 변수.  
  
 `pszNameFilter`  
 \[in\] 사용할 필터의 이름에서 `guidFilter` 및 `dwAttribFilter` 매개 변수를 선택 합니다 `DEBUG_PROPERTY_INFO` 자식인 열거할.  예를 들어, 이름이 "MyX" 모든 자식에 대 한 "MyX" 필터를이 매개 변수를 설정  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간을 지정 합니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 자식 속성 목록을 포함 하는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)
---
title: "IDebugProperty2::GetPropertyInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProperty2::GetPropertyInfo"
helpviewer_keywords: 
  - "IDebugProperty2::GetPropertyInfo"
ms.assetid: 39d6e942-df72-4c84-a5d9-a386d112714c
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProperty2::GetPropertyInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

가져옵니다는 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 속성에 설명 하는 구조입니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPropertyInfo (   
   DEBUGPROP_INFO_FLAGS dwFields,  
   DWORD                nRadix,  
   DWORD                dwTimeout,  
   IDebugReference2**   rgpArgs,  
   DWORD                dwArgCount,  
   DEBUG_PROPERTY_INFO* pPropertyInfo  
);  
```  
  
```cpp#  
int GetPropertyInfo (   
   enum_DEBUGPROP_INFO_FLAGS dwFields,  
   uint                      nRadix,  
   uint                      dwTimeout,  
   IDebugReference2[]        rgpArgs,  
   uint                      dwArgCount,  
   DEBUG_PROPERTY_INFO[]     pPropertyInfo  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 값의 조합에 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 필드에 데이터를 입력할 수를 지정 하는 열거형의 `pPropertyInfo` 구조.  
  
 `nRadix`  
 \[in\] 임의의 숫자 정보를 서식 지정에 사용할 기 수입니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간을 지정 합니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
 `rgpArgs`  
 \[in, out\] 나중에 사용 하도록 예약 됩니다. null 값으로 설정 합니다.  
  
 `dwArgCount`  
 \[in\] 나중에 사용 하도록 예약 됩니다. 0으로 설정 합니다.  
  
 `pPropertyInfo`  
 \[out\] A [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조 속성에 대 한 설명으로 채웁니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUG\_PROPERTY\_INFO](../../../extensibility/debugger/reference/debug-property-info.md)
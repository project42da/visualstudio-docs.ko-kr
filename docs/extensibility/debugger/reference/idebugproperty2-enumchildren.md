---
title: IDebugProperty2::EnumChildren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2::EnumChildren
helpviewer_keywords: IDebugProperty2::EnumChildren
ms.assetid: cf79f666-65d1-417c-af7c-9271bac9a267
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 82f08fad921a2249e6a7943acec1fb9cb60e006b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty2enumchildren"></a>IDebugProperty2::EnumChildren
속성의 자식 목록을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
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
  
#### <a name="parameters"></a>매개 변수  
 `dwFields`  
 [in] 플래그의 조합을 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) 에 열거 된 필드를 지정 하는 열거형 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) 구조체가을 입력 합니다.  
  
 `dwRadix`  
 [in] 모든 숫자 정보를 서식 지정 하는 데 사용할 기 수를 지정 합니다.  
  
 `guidFilter`  
 [in] 사용 하는 필터의 GUID는 `dwAttribFilter` 및 `pszNameFilter` 매개 변수를 선택할 `DEBUG_PROPERTY_INFO` 자식 항목을 열거할 수는 있습니다. 예를 들어 `guidFilterLocals` 지역 변수에 대 한 필터입니다.  
  
 `dwAttribFilter`  
 [in] 플래그의 조합 된 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 예를 들어 열거할 개체의 유형을 지정 하는 열거형 `DBG_ATTRIB_METHOD` 이 속성의 자식일 수 있는 모든 메서드에 대 한 합니다. 와 함께 사용 된 `guidFilter` 및 `pszNameFilter` 매개 변수입니다.  
  
 `pszNameFilter`  
 [in] 함께 사용할 필터의 이름을 `guidFilter` 및 `dwAttribFilter` 매개 변수를 선택할 `DEBUG_PROPERTY_INFO` 자식 항목을 열거할 수는 있습니다. 예를 들어 "MyX" 이름 가진 모든 자식에 대 한 "MyX" 필터에이 매개 변수를 설정  
  
 `dwTimeout`  
 [in] 이 메서드로부터 반환 하기 전에 대기할 밀리초 단위로 최대 시간을 지정 합니다. 사용 하 여 `INFINITE` 무기한 대기를 나타냅니다.  
  
 `ppEnum`  
 [out] 반환 된 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 자식 속성 목록이 포함 된 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [DBG_ATTRIB_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)
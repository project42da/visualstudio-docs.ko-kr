---
title: "IDebugReference2::EnumChildren | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugReference2::EnumChildren"
helpviewer_keywords: 
  - "IDebugReference2::EnumChildren"
ms.assetid: 35b3c2f3-69f4-4013-b555-f847221f62e8
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugReference2::EnumChildren
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

선택된 된 자식 개체에 대 한 참조 목록을 가져옵니다.  다음에 사용하도록 예약됩니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumChildren (   
   DEBUGREF_INFO_FLAGS        dwFields,  
   DWORD                      dwRadix,  
   DBG_ATTRIB_FLAGS           dwAttribFilter,  
   LPCOLESTR                  pszNameFilter,  
   DWORD                      dwTimeout,  
   IEnumDebugReferenceInfo2** ppEnum  
);  
```  
  
```c#  
int EnumChildren (   
   enum_DEBUGREF_INFO_FLAGS     dwFields,  
   uint                         dwRadix,  
   enum_DBG_ATTRIB_FLAGS        dwAttribFilter,  
   string                       pszNameFilter,  
   uint                         dwTimeout,  
   out IEnumDebugReferenceInfo2 ppEnum  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 플래그의 조합에서 [DEBUGREF\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) 열거에서 필드를 지정 하는 열거형 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 구조인 채워야 합니다.  
  
 `dwRadix`  
 \[in\] 임의의 숫자 정보를 서식 지정에 사용할 기 수입니다.  
  
 `dwAttribFilter`  
 \[in\] 플래그의 조합에서 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md) 필터와 함께에서 사용 되는 열거형의 `pszNameFilter` 매개 변수를 열거 하는 구조인 선택 합니다.  
  
 `pszNameFilter`  
 \[in\] "함께 사용 MyX"와 같은 필터를 지정 하는 문자열을 `dwAttribFilter` 매개 변수를 열거 하는 구조를 선택 합니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간입니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md) 요청 된 자식 속성 목록을 포함 하는 개체입니다.  
  
## 반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## 참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUGREF\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)   
 [DBG\_ATTRIB\_FLAGS](../../../extensibility/debugger/reference/dbg-attrib-flags.md)   
 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)
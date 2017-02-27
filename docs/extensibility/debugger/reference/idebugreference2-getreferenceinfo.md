---
title: "IDebugReference2::GetReferenceInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugReference2::GetReferenceInfo"
helpviewer_keywords: 
  - "IDebugReference2::GetReferenceInfo"
ms.assetid: ae611714-f114-4cf2-b5bb-37461e6ff289
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugReference2::GetReferenceInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

가져옵니다는 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 구조에 대 한 참조를 설명 합니다.  다음에 사용하도록 예약됩니다.  
  
## 구문  
  
```cpp#  
HRESULT GetReferenceInfo (   
   DEBUGREF_INFO_FLAGS   dwFields,  
   DWORD                 nRadix,  
   DWORD                 dwTimeout,  
   IDebugReference2**    rgpArgs,  
   DWORD                 dwArgCount,  
   DEBUG_REFERENCE_INFO* pReferenceInfo  
);  
```  
  
```c#  
int GetReferenceInfo (   
   enum_DEBUGREF_INFO_FLAGS  dwFields,  
   uint                      nRadix,  
   uint                      dwTimeout,  
   IDebugReference2[]        rgpArgs,  
   uint                      dwArgCount,  
   DEBUG_REFERENCE_INFO[]    pReferenceInfo  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 플래그의 조합에서 [DEBUGREF\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md) 에 입력할 수 있는 필드를 결정 하는 열거형의 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 구조.  
  
 `nRadix`  
 \[in\] 임의의 숫자 정보를 서식 지정에 사용할 기 수입니다.  
  
 `dwTimeout`  
 \[in\] 이 메서드에서 반환 하기 전에 대기할 시간 \(밀리초\), 최대 시간입니다.  사용 `INFINITE` 무제한으로 대기 합니다.  
  
 `rgpArgs`  
 \[in\] 배열 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 개체입니다.  나중에 사용 하도록 예약 됩니다. null 값으로 설정 합니다.  
  
 `dwArgCount`  
 \[in\] 참조 인수 개수는 `rgpArgs` 배열입니다.  나중에 사용 하도록 예약 됩니다. 0으로 설정 합니다.  
  
 `pReferenceInfo`  
 \[out\] A [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) 구조에 대 한 설명 속성에 포함 됩니다.  
  
## 반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## 참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [DEBUGREF\_INFO\_FLAGS](../../../extensibility/debugger/reference/debugref-info-flags.md)   
 [DEBUG\_REFERENCE\_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)
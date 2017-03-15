---
title: "IDebugBreakpointResolution2::GetBreakpointType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBreakpointResolution2::GetBreakpointType"
helpviewer_keywords: 
  - "IDebugBreakpointResolution2::GetBreakpointType"
ms.assetid: 2b707fb9-f703-4c78-91bf-7434f57790a0
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugBreakpointResolution2::GetBreakpointType
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 해결 방법으로 표현 되는 중단점의 종류를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetBreakpointType(   
   BP_TYPE* pBPType  
);  
```  
  
```c#  
int GetBreakpointType(   
   out enum_ BP_TYPE pBPType  
);  
```  
  
#### 매개 변수  
 `pBPType`  
 \[out\] 반환 값에서는 [BP\_TYPE](../../../extensibility/debugger/reference/bp-type.md) 이 중단점 형식을 지정 하는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  경우 E\_FAIL을 반환의 `bpResLocation` 필드에 연결 된 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) 구조가 잘못 되었습니다.  
  
## 설명  
 중단점이 있는 코드 또는 데이터 중단점을 예를 수 있습니다.  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CDebugBreakpointResolution` 를 노출 하는 개체는 [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md) 인터페이스입니다.  
  
```  
HRESULT CDebugBreakpointResolution::GetBreakpointType(BP_TYPE* pBPType)    
{    
   HRESULT hr;    
  
   if (pBPType)    
   {    
      // Set default BP_TYPE.    
      *pBPType = BPT_NONE;    
  
      // Check if the BPRESI_BPRESLOCATION flag is set in BPRESI_FIELDS.    
      if (IsFlagSet(m_bpResolutionInfo.dwFields, BPRESI_BPRESLOCATION))    
      {    
         // Set the new BP_TYPE.    
         *pBPType = m_bpResolutionInfo.bpResLocation.bpType;    
         hr = S_OK;    
      }    
      else    
      {    
         hr = E_FAIL;    
      }    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## 참고 항목  
 [IDebugBreakpointResolution2](../../../extensibility/debugger/reference/idebugbreakpointresolution2.md)   
 [BP\_TYPE](../../../extensibility/debugger/reference/bp-type.md)   
 [BPRESI\_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)   
 [BP\_RESOLUTION\_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)   
 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)
---
title: "BP_RESOLUTION_DATA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_RESOLUTION_DATA"
helpviewer_keywords: 
  - "BP_RESOLUTION_DATA 구조"
ms.assetid: 9e0b9000-6a84-47b9-b07a-367a75764389
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# BP_RESOLUTION_DATA
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

데이터 중단점을 바인딩할 결과를 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct _BP_RESOLUTION_DATA {   
   BSTR              bstrDataExpr;  
   BSTR              bstrFunc;  
   BSTR              bstrImage;  
   BP_RES_DATA_FLAGS dwFlags;  
} BP_RESOLUTION_DATA;  
```  
  
```c#  
public struct BP_RESOLUTION_DATA {   
   public string bstrDataExpr;  
   public string bstrFunc;  
   public string bstrImage;  
   public uint   dwFlags;  
};  
```  
  
## Members  
 `bstrDataExpr`  
 바인딩된 데이터 식을 합니다.  
  
 `bstrFunc`  
 함수 이름 데이터 중단점의 있을 경우 바인딩.  
  
 `bstrImage`  
 데이터 중단점에 연결 되어 있는 모듈 \(예: MyModule.dll\)의 이름입니다.  
  
 `dwFlags`  
 값은 [BP\_RES\_DATA\_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md) 데이터 중단점 구현 되는 방식을 설명 하는 열거형입니다.  
  
## 설명  
 이 구조체의 멤버입니다의 [BP\_RESOLUTION\_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md) 의 구성원을 설정 하는 구조는 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) 구조에서 반환 하는 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md) 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP\_RESOLUTION\_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)   
 [BP\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
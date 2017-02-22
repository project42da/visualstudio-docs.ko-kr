---
title: "BPERESI_FIELDS | Microsoft Docs"
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
  - "BPERESI_FIELDS"
helpviewer_keywords: 
  - "BPERESI_FIELDS 열거형"
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# BPERESI_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점에 대 한 실패 한 해상도 검색할 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD BPERESI_FIELDS;  
```  
  
```c#  
public enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
```  
  
## Members  
 PERESI\_BPRESLOCATION  
 초기화\/사용의 `bpResLocation` \(해상도 위치 중단점\) 필드에는 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 구조.  
  
 BPERESI\_PROGRAM  
 초기화\/사용의 `pProgram` 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
 BPERESI\_THREAD  
 초기화\/사용의 `pThread` 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
 BPERESI\_MESSAGE  
 초기화\/사용의 `bstrMessage` 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
 BPERESI\_TYPE  
 초기화\/사용의 `dwType` 의 \(중단점 형식\) 필드는 `BP_ERROR_RESOLUTION_INFO` 구조.  
  
 BPERESI\_ALLFIELDS  
 초기화\/사용의 모든 필드는 `BP_ERROR_RESOLUTION_INFO` 구조입니다.  
  
## 설명  
 매개 변수로 전달 되는 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) 필드의 나타내도록 메서드는 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) 된 구조를 초기화 합니다.  
  
 이러한 값도는에서 필드를 나타내는 데 사용 됩니다 있는 `BP_ERROR_RESOLUTION_INFO` 구조는 유효 하 고 사용 하는 구조를 반환 하는 경우.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP\_ERROR\_RESOLUTION\_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)
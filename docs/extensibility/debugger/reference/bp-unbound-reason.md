---
title: "BP_UNBOUND_REASON | Microsoft Docs"
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
  - "BP_UNBOUND_REASON"
helpviewer_keywords: 
  - "BP_UNBOUND_REASON 열거형"
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# BP_UNBOUND_REASON
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점을 바운드 된 이유를 설명 합니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
typedef DWORD BP_UNBOUND_REASON;  
```  
  
```c#  
public enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
```  
  
## Members  
 BPUR\_UNKNOWN  
 그 이유를 알 수 없습니다.  
  
 BPUR\_CODE\_UNLOADED  
 중단점이 포함 된 코드는 로드 되지 않은 상태입니다.  
  
 BPUR\_BREAKPOINT\_REBIND  
 다른 위치에 중단점이 다시 바인딩되지 되었습니다.  편집 후 발생 하 고 중단점을 이동할 때 또는 파일을 더 이상 사용할 수 있는 경로 중단점이 바인딩되는 경우 작업을 계속 없습니다.  
  
 BPUR\_ BREAKPOINT\_ERROR  
 중단점 오류에 연결 된 후에 결정 됩니다.  해당 조건이 더 이상 유효 하지 관리 되는 중단점을 발생 합니다.  
  
## 설명  
 반환 되는 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)
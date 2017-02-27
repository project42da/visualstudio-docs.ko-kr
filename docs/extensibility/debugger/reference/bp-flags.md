---
title: "BP_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_FLAGS"
helpviewer_keywords: 
  - "BP_FLAGS 열거형"
ms.assetid: c45dfc74-5e7f-4f1e-a147-ab2a55dccbd0
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

추가 정보를 지정 하 여 중단점을 설정할 때 사용할 수 있는 선택적 플래그를 제공 합니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
typedef DWORD BP_FLAGS;  
```  
  
```c#  
public enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
```  
  
## Members  
 BP\_FLAG\_NONE  
 플래그 없음 중단점을 지정합니다.  
  
 BP\_FLAG\_MAP\_DOCPOSITION  
 디버그 엔진 \(DE\) 문서의 위치를 사용 하 여 중단점 매핑되어야 합니다 것을 지정 합니다.  이 설정 스크립트 기반 소스 파일 Active Server Pages \(ASP\)와 같은 중단점에만 적용할 수 있습니다.  
  
 BP\_FLAG\_DONT\_STOP  
 지정 중단점을 디버그 엔진으로 처리 해야 하지만 디버그 궁극적으로 엔진 있습니다 중지 해서는 안됩니다 \(즉,는 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) 이벤트 개체를 전송 해야 합니다 없습니다\).  이 플래그는 주로 추적점을 사용 하도록 설계 되었습니다.  
  
## 설명  
 사용 되는 `dwFlags` 의 멤버는 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 및 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) 구조.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP\_REQUEST\_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP\_REQUEST\_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)
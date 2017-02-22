---
title: "BP_FLAGS90 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BP_FLAGS90 열거형"
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# BP_FLAGS90
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

선택적 플래그에 대 한 유효한 값을 열거합니다.  중단점을 설정 하는 경우 추가 정보를 지정 하는 선택적 플래그를 사용할 수 있습니다.  이 열거형에 확장 되는 [BP\_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) 열거형입니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE               = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION    = 0x0001,  
   BP90_FLAG_DONT_STOP          = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
typedef DWORD BP_FLAGS90;  
```  
  
```c#  
public enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE                = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION     = 0x0001,  
   BP90_FLAG_DONT_STOP           = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
```  
  
#### 매개 변수  
 BP90\_FLAG\_NONE  
 플래그 없음 중단점을 지정합니다.  
  
 BP90\_FLAG\_MAP\_DOCPOSITION  
 디버그 엔진 \(DE\) 문서의 위치를 사용 하 여 중단점 매핑되어야 합니다 지정 합니다.  이 설정 스크립트 기반 소스 파일 Active Server Pages \(ASP\)와 같은 중단점에만 적용할 수 있습니다.  
  
 BP90\_FLAG\_DONT\_STOP  
 중단점을 디버그 엔진으로 처리 해야 하지만 디버그 엔진 궁극적으로 중지 하지 하도록 지정 합니다. 즉,는 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) 이벤트 개체를 전송 해야 합니다 없습니다.  이 플래그는 기본적으로 추적 지점으로 사용 하도록 설계 되었습니다.  
  
 BP90\_FLAG\_TRACEPOINT\_CONTINUE  
 기본 디버그 엔진에서 스테핑 상태를 지울 수 있는지 여부를 확인 하는 데 사용.  추적 지점이 매크로 실행 하면 bp90\_flag\_dont\_stop가 설정 되어 있지 않아 bp90\_flag\_dont\_stop에서와 다릅니다.  
  
## 요구 사항  
 헤더: Msdbg90.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
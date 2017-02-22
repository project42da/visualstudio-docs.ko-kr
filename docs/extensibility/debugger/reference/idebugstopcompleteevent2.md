---
title: "IDebugStopCompleteEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugStopCompleteEvent2 인터페이스"
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugStopCompleteEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램을 중지 했을 때 디버그 엔진 \(DE\) 세션 디버그 매니저 \(SDM\)이 선택적 이벤트를 보낼 수 있습니다.  
  
## 구문  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 이 대 한 새 인터페이스입니다 [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)].  이전 릴리스에서 비동기 중단을 지원 하지 않습니다.  
  
 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)SDM 다중 프로세스 또는 multi\-program 시나리오에서 호출 됩니다.  프로그램 중지 이벤트는 SDM을 보내면는 SDM 너무 중지 하려면 다른 프로그램을 요청 합니다.  
  
 비동기적으로 프로그램을 중지 했습니다 SDM을 알리기 위해 사용 됩니다.  때로는 코드가 디버깅된 되는 프로그램 안에서 실행 되는, 인터프리터 디버그 엔진에 유용 하므로 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) 동기적으로 완료 될 수 있습니다.  디버그 엔진이 비동기 알림을 사용 하는 경우, 원하는 반환 합니다 `S_ASYNC_STOP` 에서 [중지](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll
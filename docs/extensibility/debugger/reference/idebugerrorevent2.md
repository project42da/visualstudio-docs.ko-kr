---
title: "IDebugErrorEvent2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugErrorEvent2"
helpviewer_keywords: 
  - "IDebugErrorEvent2 인터페이스"
ms.assetid: 275b6f38-b3d4-4cae-8491-491177f524fb
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugErrorEvent2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에 오류 메시지를 사용자에 게 보고 해야 합니다 지정 합니다.  
  
## 구문  
  
```  
IDebugErrorEvent2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\)이이 인터페이스에서 오류를 보고 읽을 메시지를 구현합니다.  [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md) 이 인터페이스와 같은 개체에서 인터페이스를 구현 해야 합니다.  SDM을 사용 하 여 [QueryInterface](/visual-cpp/atl/queryinterface) 액세스 하는 `IDebugEvent2` 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 DE 만들고 오류를 보고 하려면이 이벤트 개체를 보냅니다.  이벤트를 사용 하 여 전송 되는 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) 디버깅 중인 프로그램에 연결 하는 경우 SDM가 제공 되는 콜백 함수입니다.  
  
## 메서드에서 Vtable 순서  
 이 인터페이스에 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|`GetErrorMessage`|사람이 읽을 수 있는 string으로 오류를 반환 합니다.|  
  
## 설명  
 디버그 엔진에 오류가 발생 하는 경우이 인터페이스 메시지 Visual Studio 통해 사용자에 게 보고할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)
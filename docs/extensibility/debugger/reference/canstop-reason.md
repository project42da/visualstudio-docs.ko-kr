---
title: "CANSTOP_REASON | Microsoft Docs"
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
  - "CANSTOP_REASON"
helpviewer_keywords: 
  - "CANSTOP_REASON 열거형"
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# CANSTOP_REASON
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램 실행에 특정 지점에 도달 하면 실행이 중지 수 있습니다 경우 결정 하는 데 사용 됩니다.  
  
## 구문  
  
```cpp#  
enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
typedef DWORD CANSTOP_REASON;  
```  
  
```c#  
public enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
```  
  
## Members  
 CANSTOP\_ENTRYPOINT  
 지정한 프로그램의 진입점을 지정합니다.  
  
 CANSTOP\_STEPIN  
 함수를 한 단계씩 실행을 지정 합니다.  
  
## 설명  
 인수로 전달 되는 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) 메서드가 프로그램의 진입점에 도달 하거나 메서드 또는 함수를 한 단계씩 실행 후 중지할 수 있는 경우는 세션 디버그 매니저 \(SDM\)을 확인 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)
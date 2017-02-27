---
title: "EXCEPTION_STATE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EXCEPTION_STATE"
helpviewer_keywords: 
  - "EXCEPTION_STATE 열거형"
ms.assetid: 597f4f4c-9b70-485c-b5dc-3c2e3aecc664
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# EXCEPTION_STATE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

예외 상태를 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_EXCEPTION_STATE {   
   EXCEPTION_NONE                          = 0x0000,  
   EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,  
   EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,  
   EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,  
   EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,  
   EXCEPTION_STOP_ALL                      = 0x00FF,  
   EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,  
  
   // These are for exception types only  
   EXCEPTION_CODE_SUPPORTED                = 0x1000,  
   EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,  
   EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,  
   EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,  
  
   // These are no longer used  
   EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,  
   EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,  
   EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,  
   EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,  
};  
typedef DWORD EXCEPTION_STATE;  
```  
  
```c#  
public enum enum_EXCEPTION_STATE {   
   EXCEPTION_NONE                          = 0x0000,  
   EXCEPTION_STOP_FIRST_CHANCE             = 0x0001,  
   EXCEPTION_STOP_SECOND_CHANCE            = 0x0002,  
   EXCEPTION_STOP_USER_FIRST_CHANCE        = 0x0010,  
   EXCEPTION_STOP_USER_UNCAUGHT            = 0x0020,  
   EXCEPTION_STOP_ALL                      = 0x00FF,  
   EXCEPTION_CANNOT_BE_CONTINUED           = 0x0100,  
  
   // These are for exception types only  
   EXCEPTION_CODE_SUPPORTED                = 0x1000,  
   EXCEPTION_CODE_DISPLAY_IN_HEX           = 0x2000,  
   EXCEPTION_JUST_MY_CODE_SUPPORTED        = 0x4000,  
   EXCEPTION_MANAGED_DEBUG_ASSISTANT       = 0x8000,  
  
   // These are no longer used  
   EXCEPTION_STOP_FIRST_CHANCE_USE_PARENT      = 0x0004,  
   EXCEPTION_STOP_SECOND_CHANCE_USE_PARENT     = 0x0008,  
   EXCEPTION_STOP_USER_FIRST_CHANCE_USE_PARENT = 0x0040,  
   EXCEPTION_STOP_USER_UNCAUGHT_USE_PARENT     = 0x0080,  
};  
```  
  
## Members  
 EXCEPTION\_NONE  
 예외에서 중지 하지 마십시오.  
  
 EXCEPTION\_STOP\_FIRST\_CHANCE  
 첫 번째 예외 발사 중지 합니다.  예외 이벤트를 설명 하는 경우이 플래그는 예외 이벤트 첫 번째 예외 이벤트입니다.  
  
 EXCEPTION\_STOP\_SECOND\_CHANCE  
 두 번째 예외 발사 중지 합니다.  예외 이벤트를 설명 하는 경우 예외 이벤트가 두 번째 예외 이벤트입니다.  
  
 EXCEPTION\_STOP\_USER\_FIRST\_CHANCE  
 첫 번째 사용자 모드 예외 발사 중지 합니다.  예외 이벤트를 설명 하는 경우 예외 이벤트 첫째 사용자 예외 이벤트입니다.  
  
 EXCEPTION\_STOP\_USER\_UNCAUGHT  
 사용자 모드 예외를 catch 하지 중지 합니다.  예외 이벤트를 설명 하는 경우 예외 이벤트는 catch 되지 않은 사용자 모드 예외 이벤트입니다.  
  
 EXCEPTION\_STOP\_ALL  
 모든 예외에서 중단 합니다.  예외 이벤트를 설명 하는 경우 사용지 않습니다.  
  
 EXCEPTION\_CANNOT\_BE\_CONTINUED  
 예외 이벤트를 설명 하는 경우 예외를 계속할 수 없습니다 나타냅니다.  
  
 EXCEPTION\_CODE\_SUPPORTED  
 예외를 지 원하는 코드가 있음을 나타냅니다.  사용 하는 예외를 표시 하는  
  
 EXCEPTION\_CODE\_DISPLAY\_IN\_HEX  
 예외 코드를 16 진수로 표시 되어야 함을 나타냅니다.  예외를 표시 하는 사용 합니다.  
  
 EXCEPTION\_JUST\_MY\_CODE\_SUPPORTED  
 예외 코드 Justmycode를 지원함을 나타냅니다.  예외를 표시 하는 사용 합니다.  
  
 EXCEPTION\_MANAGED\_DEBUG\_ASSISTANT  
 관리 코드 디버거에 예외를 처리 해야 합니다 나타냅니다.  그렇지 않으면 기본 디버거 설정의 예외를 처리 합니다.  이 전달 되는 [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) 메서드 사용 안은 [EXCEPTION\_INFO](../../../extensibility/debugger/reference/exception-info.md) 구조입니다.  
  
 EXCEPTION\_STOP\_FIRST\_CHANCE\_USE\_PARENT  
 사용 되지 않음, 사용 하지 마십시오.  
  
 EXCEPTION\_STOP\_SECOND\_CHANCE\_USE\_PARENT  
 사용 되지 않음, 사용 하지 마십시오.  
  
 EXCEPTION\_STOP\_USER\_FIRST\_CHANCE\_USE\_PARENT  
 사용 되지 않음, 사용 하지 마십시오.  
  
 EXCEPTION\_STOP\_USER\_SECOND\_CHANCE\_USE\_PARENT  
 사용 되지 않음, 사용 하지 마십시오.  
  
## 설명  
 사용 되는 `dwState` 의 구성원은 [EXCEPTION\_INFO](../../../extensibility/debugger/reference/exception-info.md) 예외 및 대해 수행할 수 있는 상태를 나타내는 구조.  
  
 이러한 값도 전달의 [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md) 메서드 상태는 모든 예외를 설정 합니다.  
  
 비트 OR로 이러한 플래그를 조합할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EXCEPTION\_INFO](../../../extensibility/debugger/reference/exception-info.md)   
 [SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)
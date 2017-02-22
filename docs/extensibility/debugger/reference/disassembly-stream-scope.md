---
title: "DISASSEMBLY_STREAM_SCOPE | Microsoft Docs"
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
  - "DISASSEMBLY_STREAM_SCOPE"
helpviewer_keywords: 
  - "DISASSEMBLY_STREAM_SCOPE 열거형"
ms.assetid: 43e2b364-cbbe-4755-a7e6-a03f3054c965
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# DISASSEMBLY_STREAM_SCOPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디스어셈블리 스트림 중 하나를 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
typedef DWORD DISASSEMBLY_STREAM_SCOPE;  
```  
  
```c#  
public enum enum_DISASSEMBLY_STREAM_SCOPE {   
   DSS_HUGE     = 0x10000000,  
   DSS_FUNCTION = 0x0001,  
   DSS_MODULE   = (DSS_HUGE) | 0x0002,  
   DSS_ALL      = (DSS_HUGE) | 0x0003  
};  
```  
  
## Members  
 DSS\_HUGE  
 클라이언트는 일반적으로 단일 호출에 검색 하려는 것 보다 더 많은 출력 코드 컨텍스트 분해 생성 한다고 지정 합니다.  
  
 DSS\_FUNCTION  
 코드 컨텍스트에 포함 된 함수를 해제할 수 있는지를 지정 합니다.  디스어셈블리 스트림을 반환 하는 경우 함수를 나타낸다는 것을 지정의 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) 메서드가 있습니다.  
  
 DSS\_MODULE  
 반환 되는 경우는 `IDebugDisassemblyStream2::GetScope` 메서드를 지정 디스어셈블리 스트림에 모듈을 나타냅니다.  
  
 DSS\_ALL  
 전체 주소 공간에 대 한 디스어셈블리를 지정합니다.  
  
## 설명  
 인수로 전달 되는 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md) 메서드 및 반환 하는 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md) 메서드.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDisassemblyStream](../../../extensibility/debugger/reference/idebugprogram2-getdisassemblystream.md)   
 [GetScope](../../../extensibility/debugger/reference/idebugdisassemblystream2-getscope.md)
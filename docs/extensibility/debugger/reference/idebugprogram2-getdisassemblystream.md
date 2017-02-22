---
title: "IDebugProgram2::GetDisassemblyStream | Microsoft Docs"
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
  - "IDebugProgram2::GetDisassemblyStream"
helpviewer_keywords: 
  - "IDebugProgram2::GetDisassemblyStream"
ms.assetid: beda0da5-267e-4bf3-96c4-b659d29e2254
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::GetDisassemblyStream
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램 또는이 프로그램의 일부에 대 한 디스어셈블리 stream을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDisassemblyStream(   
   DISASSEMBLY_STREAM_SCOPE   dwScope,  
   IDebugCodeContext2*        pCodeContext,  
   IDebugDisassemblyStream2** ppDisassemblyStream  
);  
```  
  
```c#  
int GetDisassemblyStream(   
   enum_DISASSEMBLY_STREAM_SCOPE  dwScope,  
   IDebugCodeContext2             pCodeContext,  
   out IDebugDisassemblyStream2   ppDisassemblyStream  
);  
```  
  
#### 매개 변수  
 `dwScope`  
 \[in\] 값을 지정의 [DISASSEMBLY\_STREAM\_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) 디스어셈블리 stream의 범위를 정의 하는 열거형입니다.  
  
 `pCodeContext`  
 \[in\] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 디스어셈블리 스트림의 시작 위치 위치를 나타내는 개체입니다.  
  
 `ppDisassemblyStream`  
 \[out\] 반환 된 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md) 디스어셈블리 스트림을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_DISASM_NOTSUPPORTED` 이 특정 아키텍처에 대 한 디스어셈블리를 지원 하지 않는 경우.  
  
## 설명  
 경우는 `dwScopes` 매개 변수는 `DSS_HUGE` 의 플래그는 [DISASSEMBLY\_STREAM\_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) 열거형을 설정 하는 경우 디스어셈블리 많은 디스어셈블리 지침, 예를 들어, 전체 파일 또는 모듈에 대 한 반환 해야 합니다.  경우는 `DSS_HUGE` 플래그가 설정 되지 않았습니다. 다음 디스어셈블리가 작은 영역에 국한 될 것으로 예상 되는 일반적으로 단일 함수입니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [DISASSEMBLY\_STREAM\_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)
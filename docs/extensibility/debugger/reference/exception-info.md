---
title: "EXCEPTION_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EXCEPTION_INFO"
helpviewer_keywords: 
  - "EXCEPTION_INFO 구조"
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# EXCEPTION_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

예외 또는 디버깅 중인 프로그램에서 발생 하는 런타임 오류에 설명 합니다.  
  
## 구문  
  
```cpp#  
typedef struct tagEXCEPTION_INFO {   
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   BSTR            bstrExceptionName;  
   DWORD           dwCode;  
   EXCEPTION_STATE dwState;  
   GUID            guidType;  
} EXCEPTION_INFO;  
```  
  
```c#  
public struct EXCEPTION_INFO {   
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public string         bstrExceptionName;  
   public uint           dwCode;  
   public uint           dwState;  
   public Guid           guidType;  
};  
```  
  
## Members  
 pProgram  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 예외가 발생 하 여 프로그램을 나타내는 개체입니다.  
  
 bstrProgramName  
 예외가 발생 하는 프로그램의 이름입니다.  
  
 bstrExceptionName  
 예외의 이름입니다.  
  
 dwCode  
 예외 또는 런타임 오류를 식별 코드입니다.  
  
 dwState  
 값은 [EXCEPTION\_STATE](../../../extensibility/debugger/reference/exception-state.md) 예외 상태를 정의 하는 열거형입니다.  
  
 guidType  
 GUID 언어 식별자는 `guidLang` 또는 `guidEng`.  
  
## 설명  
 이 구조체는 매개 변수로 전달 되는 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md) 및 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md) 방법.  이 구조에도 전달 되는 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md) 채울 수 있도록 하는 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [EXCEPTION\_STATE](../../../extensibility/debugger/reference/exception-state.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)   
 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)
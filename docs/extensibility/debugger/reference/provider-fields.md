---
title: "PROVIDER_FIELDS | Microsoft Docs"
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
  - "PROVIDER_FIELDS"
helpviewer_keywords: 
  - "PROVIDER_FIELDS 열거형"
ms.assetid: 39631545-2b0e-45b4-978b-d63656484b02
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# PROVIDER_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램 공급자와 관련 된 속성을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_PROVIDER_FIELDS {  
   PFIELD_PROGRAM_NODES       = 0x01,  
   PFIELD_IS_DEBUGGER_PRESENT = 0x02  
};  
typedef DWORD PROVIDER_FIELDS;  
```  
  
```c#  
public enum enum_PROVIDER_FIELDS {  
   PFIELD_PROGRAM_NODES       = 0x01,  
   PFIELD_IS_DEBUGGER_PRESENT = 0x02  
};  
```  
  
## Members  
 PFIELD\_PROGRAM\_NODES  
 `ProgramNodes` 필드를 사용할 수 있습니다.  
  
 PFIELD\_IS\_DEBUGGER\_PRESENT  
 `fIsDebuggerPresent` 필드를 사용할 수 있습니다.  
  
## 설명  
 이 값이 반환 됩니다는 `Fields` 의 멤버는 [PROVIDER\_PROCESS\_DATA](../../../extensibility/debugger/reference/provider-process-data.md) 필드 구조를 명시적으로 입력 나타내도록 구조.  
  
 이 값이 비트와 결합 될 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROVIDER\_PROCESS\_DATA](../../../extensibility/debugger/reference/provider-process-data.md)
---
title: "AD_PROCESS_ID_TYPE | Microsoft Docs"
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
  - "AD_PROCESS_ID_TYPE"
helpviewer_keywords: 
  - "AD_PROCESS_ID_TYPE 열거형"
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# AD_PROCESS_ID_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스 ID를 해석 하는 방법 지정의 [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조.  
  
## 구문  
  
```cpp#  
enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
typedef DWORD AD_PROCESS_ID_TYPE;  
```  
  
```c#  
public enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
```  
  
## Members  
 AD\_PROCESS\_ID\_SYSTEM  
 프로세스 ID는 시스템 식별자입니다.  사용은 `ProcessId.dwProcessId` 필드는 [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조입니다.  
  
 AD\_PROCESS\_ID\_GUID  
 프로세스 ID는 GUID입니다.  사용은 `ProcessId.guidProcessId` 필드는 `AD_PROCESS_ID` 구조입니다.  
  
## 설명  
 사용 되는 `ProcessIdType` 의 구성원은 [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md) 구조에 포함 된 프로세스 ID를 식별 하는 구조.  해석 하는 방법을 결정은 `ProcessId` 구조에 통합 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md)
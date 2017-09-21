---
title: "THREADPROPERTY_FIELDS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "THREADPROPERTY_FIELDS"
helpviewer_keywords: 
  - "THREADPROPERTY_FIELDS 열거형"
ms.assetid: 5b88acb9-03ea-4c29-a788-f0087dccbe23
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# THREADPROPERTY_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스레드에 대 한 정보를 검색할 수를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD THREADPROPERTY_FIELDS;  
```  
  
```c#  
public enum enum_THREADPROPERTY_FIELDS {   
   TPF_ID           = 0x0001,  
   TPF_SUSPENDCOUNT = 0x0002,  
   TPF_STATE        = 0x0004,  
   TPF_PRIORITY     = 0x0008,  
   TPF_NAME         = 0x0010,  
   TPF_LOCATION     = 0x0020,  
   TPF_ALLFIELDS    = 0xffffffff  
};  
```  
  
## Members  
 TPF\_ID  
 초기화\/사용의 `dwThreadId` 필드는 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조입니다.  
  
 TPF\_SUSPENDCOUNT  
 초기화\/사용의 `dwSuspendCount` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF\_STATE  
 초기화\/사용의 `dwThreadState` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF\_PRIORITY  
 초기화\/사용의 `bstrPriority` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF\_NAME  
 초기화\/사용의 `bstrName` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF\_LOCATION  
 초기화\/사용의 `bstrLocation` 필드는 `THREADPROPERTIE`S 구조입니다.  
  
 TPF\_ALLFIELDS  
 모든 필드를 지정합니다.  
  
## 설명  
 이러한 값을 인수로 전달 되는 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) 필드의 나타내도록 메서드는 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조에 있는 초기화.  
  
 이러한 값에도 사용 됩니다 `dwFields` 의 멤버는 `THREADPROPERTIES` 구조 필드 사용 되는 및 잘못 된 것을 나타냅니다.  
  
 이러한 플래그의 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)
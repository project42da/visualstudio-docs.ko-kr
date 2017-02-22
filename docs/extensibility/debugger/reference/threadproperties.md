---
title: "THREADPROPERTIES | Microsoft Docs"
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
  - "THREADPROPERTIES"
helpviewer_keywords: 
  - "THREADPROPERTIES 구조"
ms.assetid: 7d397207-db03-4ec0-9f79-3794056ed89f
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# THREADPROPERTIES
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스레드 속성을 설명합니다.  
  
## 구문  
  
```cpp#  
typedef struct _tagTHREADPROPERTIES {   
   THREADPROPERTY_FIELDS dwFields;  
   DWORD                 dwThreadId;  
   DWORD                 dwSuspendCount;  
   DWORD                 dwThreadState;  
   BSTR                  bstrPriority;  
   BSTR                  bstrName;  
   BSTR                  bstrLocation;  
} THREADPROPERTIES;  
```  
  
```c#  
public struct THREADPROPERTIES {   
   public uint   dwFields;  
   public uint   dwThreadId;  
   public uint   dwSuspendCount;  
   public uint   dwThreadState;  
   public string bstrPriority;  
   public string bstrName;  
   public string bstrLocation;  
};  
```  
  
## Members  
 dwFields  
 플래그의 조합에 [THREADPROPERTY\_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md) 이 구조체의 필드 잘못 된 설명 하는 열거형입니다.  
  
 dwThreadId  
 스레드 id입니다.  
  
 dwSuspendCount  
 스레드 횟수를 일시 중단 합니다.  
  
 dwThreadState  
 값은 [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md) 운영 체제 스레드의 상태를 나타내는 열거형입니다.  
  
 bstrPriority  
 스레드 우선 순위를 지정 하는 문자열입니다. 예를 들어, 위의 "보통", "보통" 또는 시간 "긴급".  
  
 bstName  
 스레드의 이름입니다.  
  
 bstrLocation  
 일반적으로 실행이 중지 됩니다 현재 메서드 이름으로 표현 된 스레드 위치 \(일반적으로 최상위 스택 프레임\)를.  
  
## 설명  
 이 구조를 호출 하 여 채워집니다는 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md) 메서드가 있습니다.  따라서 반환 되는 정보를 채우는 데에 일반적으로 사용 됩니다 있는  **스레드** 창.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)   
 [THREADPROPERTY\_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)   
 [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)
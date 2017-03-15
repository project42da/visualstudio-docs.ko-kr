---
title: "BP_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BP_TYPE"
helpviewer_keywords: 
  - "BP_TYPE 열거형"
ms.assetid: ef07191e-7966-43ab-96fb-1a0b1db3115d
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# BP_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점이 코드 위치에, 데이터 위치, 인지 또는 다른 형식의 중단점 지를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_TYPE {   
   BPT_NONE    = 0x0000,  
   BPT_CODE    = 0x0001,  
   BPT_DATA    = 0x0002,  
   BPT_SPECIAL = 0x0003  
};  
typedef DWORD BP_TYPE;  
```  
  
```c#  
public enum enum_BP_TYPE {   
   BPT_NONE    = 0x0000,  
   BPT_CODE    = 0x0001,  
   BPT_DATA    = 0x0002,  
   BPT_SPECIAL = 0x0003  
};  
```  
  
## Members  
 BPT\_NONE  
 중단점 형식이 지정합니다.  
  
 BPT\_CODE  
 코드에 중단점을 지정합니다.  
  
 BPT\_DATA  
 데이터 중단점을 지정합니다.  
  
 BPT\_SPECIAL  
 코드나 데이터 형식이 되는 중단점을 지정 합니다.  이 종류 되지 않으며 사용 하지 않아야 합니다.  
  
## 설명  
 매개 변수로 전달 되는 [GetBreakpointType](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md) 및 [GetBreakpointType](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md) 방법.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetBreakpointType](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getbreakpointtype.md)   
 [GetBreakpointType](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getbreakpointtype.md)
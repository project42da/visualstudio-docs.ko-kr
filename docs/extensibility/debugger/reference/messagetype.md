---
title: "MESSAGETYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MESSAGETYPE"
helpviewer_keywords: 
  - "MESSAGETYPE 열거형"
ms.assetid: 800cc77d-3c27-4763-a9df-552a9384bd49
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# MESSAGETYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

메시지 종류와 이유를 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
typedef DWORD MESSAGETYPE;  
```  
  
```c#  
public enum enum_MESSAGETYPE {   
   MT_OUTPUTSTRING      = 0x0000001,  
   MT_MESSAGEBOX        = 0x00000002,  
   MT_TYPE_MASK         = 0x000000FF,  
   MT_REASON_EXCEPTION  = 0x00000100,  
   MT_REASON_TRACEPOINT = 0x00000200,  
   MT_REASON_MASK       = 0x0000FF00  
};  
```  
  
## Members  
 MT\_OUTPUTSTRING  
 출력 창에 메시지를 보낼 수 있어야 한다는 나타냅니다.  이 함께 사용할 수 있습니다 `MT_MESSAGEBOX`.  
  
 MT\_MESSAGEBOX  
 메시지를 메시지 상자에 표시할지 나타냅니다.  이 함께 사용할 수 있습니다 `MT_OUTPUTSTRING`.  
  
 MT\_TYPE\_MASK  
 대상 메시지를 격리 하는 마스크 값입니다.  
  
 MT\_REASON\_EXCEPTION  
 메시지 상자 결과로 예외가 표시 되지 않음을 나타냅니다.  이 함께 사용할 수 있습니다 `MT_REASON_TRACEPOINT`.  
  
 MT\_REASON\_TRACEPOINT  
 메시지 상자 추적점을 맞 혀로 인해 표시 되지 않음을 나타냅니다.  이 함께 하는 `MT_REASON_EXCEPTION`.  
  
 MT\_REASON\_MASK  
 표시 되는 메시지에 대 한 원인을 격리 하는 마스크 값입니다.  
  
## 설명  
 이러한 값에서 반환 되는 [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md) 및 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md) 메서드.  
  
 이유 값 중 하나로 결합할 수 있습니다 연산을 사용 하 여 출력 대상 값 중 하나를 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetMessage](../../../extensibility/debugger/reference/idebugmessageevent2-getmessage.md)   
 [GetErrorMessage](../../../extensibility/debugger/reference/idebugerrorevent2-geterrormessage.md)
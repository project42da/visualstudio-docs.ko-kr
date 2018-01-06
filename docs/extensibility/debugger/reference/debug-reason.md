---
title: DEBUG_REASON | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEBUG_REASON
helpviewer_keywords: DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fda733db5a70d88d5029c4001c632c234d32a823
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugreason"></a>DEBUG_REASON
디버깅 하는 프로세스를 시작한 이유를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
typedef DWORD DEBUG_REASON;  
```  
  
```csharp  
public enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 DEBUG_REASON_ERROR  
 관련 되지 않은 오류가 발생 했습니다 (때 사용 되며 기본 조건으로 있는 다른 이유로 맞춤).  
  
 DEBUG_REASON_USER_LAUNCHED  
 사용자의 요청으로 프로세스 시작 되었습니다.  
  
 DEBUG_REASON_USER_ATTACHED  
 이미 실행 중인 프로세스에는 사용자가 연결 되었습니다.  
  
 DEBUG_REASON_AUTO_ATTACHED  
 시작 될 때 프로세스에 자동으로 연결 되었습니다.  
  
 DEBUG_REASON_CAUSALITY  
 로 인해 시작 하는 프로세스는 *Just In Time* (JIT) 디버깅 이벤트입니다.  
  
## <a name="remarks"></a>설명  
 반환 되는 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)
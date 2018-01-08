---
title: THREADSTATE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: THREADSTATE
helpviewer_keywords: THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 7912e890690caf6733f3673842dd3d0833473c03
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="threadstate"></a>THREADSTATE
스레드의 상태를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
typedef DWORD THREADSTATE;  
```  
  
```csharp  
public enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
```  
  
## <a name="members"></a>멤버  
 THREADSTATE_RUNNING  
 스레드가 실행 중임을 나타냅니다.  
  
 THREADSTATE_STOPPED  
 스레드가 중단점으로 인해 중지 되었음을 나타냅니다.  
  
 THREADSTATE_FRESH  
 스레드가 만들어져 있지만 코드를 아직 실행 되지 않는 나타냅니다.  
  
 THREADSTATE_DEAD  
 스레드가 비활성화 된 것을 나타냅니다.  
  
 THREADSTATE_FROZEN  
 스레드가 중지 되었음을 나타냅니다 (없습니다 실행을 수행할 수 있습니다.).  
  
## <a name="remarks"></a>설명  
 에 사용 된 `dwThreadState` 필드는 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)
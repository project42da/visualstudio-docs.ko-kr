---
title: BP_UNBOUND_REASON | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_UNBOUND_REASON
helpviewer_keywords: BP_UNBOUND_REASON enumeration
ms.assetid: 939b6f9c-113b-471d-9f30-b03871af6285
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fa824f71a4b468a131b1ebf31b3dba21bc83032c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bpunboundreason"></a>BP_UNBOUND_REASON
중단점 바인딩된 없습니다. 이유를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
typedef DWORD BP_UNBOUND_REASON;  
```  
  
```csharp  
public enum enum_BP_UNBOUND_REASON {   
   BPUR_UNKNOWN           = 0x0000,  
   BPUR_CODE_UNLOADED     = 0x0002,  
   BPUR_BREAKPOINT_REBIND = 0x0003,  
   BPUR_BREAKPOINT_ERROR  = 0x0004  
};  
```  
  
## <a name="members"></a>멤버  
 BPUR_UNKNOWN  
 이유를 알 수 없습니다.  
  
 BPUR_CODE_UNLOADED  
 중단점을 포함 하는 코드는 언로드 되었습니다.  
  
 BPUR_BREAKPOINT_REBIND  
 중단점을 다른 위치로 다시 바인딩. 이 편집 후 발생 하 고, 이동 또는 중단점을 더 이상 사용할 경로와 파일에 바인딩되어 있을 때 작업을 계속 수 없습니다.  
  
 BPUR_ BREAKPOINT_ERROR  
 중단점이 바인딩된 후 오류에 있는 것으로 결정 됩니다. 이 관리 되는 중단점 인 조건이 더 이상 유효에 발생 합니다.  
  
## <a name="remarks"></a>설명  
 반환 되는 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugbreakpointunboundevent2-getreason.md)
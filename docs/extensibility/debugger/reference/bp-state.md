---
title: BP_STATE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_STATE
helpviewer_keywords: BP_STATE enumeration
ms.assetid: 08aa6a3f-3e5f-4c83-8eca-7b7b5f8e208d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 51574fd91a338f7d05d38755884412202d33637b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="bpstate"></a>BP_STATE
바인딩된 중단점의 존재 여부를 지정 하 고 또한 사용 되는지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_BP_STATE {   
   BPS_NONE     = 0x0000,  
   BPS_DELETED  = 0x0001,  
   BPS_DISABLED = 0x0002,  
   BPS_ENABLED  = 0x0003  
};  
typedef DWORD BP_STATE;  
```  
  
```csharp  
public enum enum_BP_STATE {   
   BPS_NONE     = 0x0000,  
   BPS_DELETED  = 0x0001,  
   BPS_DISABLED = 0x0002,  
   BPS_ENABLED  = 0x0003  
};  
```  
  
## <a name="members"></a>멤버  
 BPS_NONE  
 중단점이 있음을 지정 합니다.  
  
 BPS_DELETED  
 중단점 삭제 했을 지정 합니다.  
  
 BPS_DISABLED  
 중단점을 사용할 수 없다는 것을 지정 합니다.  
  
 BPS_ENABLED  
 중단점이 설정 되었음을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 반환 되는 [우편 번호](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [우편 번호](../../../extensibility/debugger/reference/idebugboundbreakpoint2-getstate.md)
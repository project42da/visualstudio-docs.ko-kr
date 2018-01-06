---
title: BP_PASSCOUNT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_PASSCOUNT
helpviewer_keywords: BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 62c523ee3d65a7149f8e25304e0b719470242685
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bppasscount"></a>BP_PASSCOUNT
조건부 중단점을 발생 수와 조건을 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _BP_PASSCOUNT {   
   DWORD              dwPassCount;  
   BP_PASSCOUNT_STYLE stylePassCount;  
} BP_PASSCOUNT;  
```  
  
```csharp  
public struct BP_PASSCOUNT {   
   public uint dwPassCount;  
   public uint stylePassCount;  
};  
```  
  
## <a name="members"></a>멤버  
 `dwPassCount`  
 이 내보내기 전에 중단점을 통해 전달할 수 횟수입니다.  
  
 `stylePassCount`  
 값은 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md) 테스트 횟수 중단점의 스타일을 지정 하는 열거형입니다.  
  
## <a name="remarks"></a>설명  
 이 구조는의 구성원은 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) 구조입니다.  
  
 이 구조에 대 한 매개 변수로 전달 되는[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md) 및[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)
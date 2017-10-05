---
title: IDebugThread2::Suspend | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugThread2::Suspend
helpviewer_keywords:
- IDebugThread2::Suspend
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 3926456c8b625102dfc5df4d8818f3cacc3a2ce3
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="idebugthread2suspend"></a>IDebugThread2::Suspend
스레드 일시 중단합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Suspend (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
HRESULT Suspend (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwSuspendCount`  
 [out] 일시 중단 작업 후 일시 중단 횟수를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드를 호출할 때마다 0 위에 일시 중단 횟수가 증가 시킵니다. 이 일시 중단 횟수가에 표시 되는 **스레드** 디버그 창.  
  
 이 메서드를 호출할 때마다, 한 이후의 호출 있어야는 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md) 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)

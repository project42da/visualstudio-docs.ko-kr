---
title: IDebugThread2::GetLogicalThread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
caps.latest.revision: 11
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
ms.openlocfilehash: d7a5362aad3a8044ec484f70e71812e45e6a3a8d
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
디버그 엔진에서이 메서드를 구현 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetLogicalThread(   
   IDebugStackFrame2*     pStackFrame,  
   IDebugLogicalThread2** ppLogicalThread  
);  
```  
  
```csharp  
int GetLogicalThread(   
   IDebugStackFrame2        pStackFrame,  
   out IDebugLogicalThread2 ppLogicalThread  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStackFrame`  
 [in] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 스택 프레임을 나타내는 개체입니다.  
  
 `ppLogicalThread`  
 [out] 반환 된 `IDebugLogicalThread2` 관련된 논리 스레드를 나타내는 인터페이스입니다. 디버그 엔진 구현 null 값을 설정 해야 합니다.  
  
## <a name="return-value"></a>반환 값  
 디버그 엔진 구현 항상 반환 `E_NOTIMPL`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)

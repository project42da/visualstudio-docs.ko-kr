---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords: IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a6b0f74ef5b14fb9e8971c0d539cc2e875658341
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
연결 된 프로그램에 연결 하거나 연결 프로세스를 지연 된 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```csharp  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidProgramId`  
 [in] `GUID` 연결 된 프로그램에 할당할 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`합니다. 반환 `S_FALSE` 경우는 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드를 호출 해야 합니다. 그러지 않으면 오류 코드가 반환됩니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 연결 과정에서 전에 [연결](../../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드를 호출 합니다. `OnAttach` 메서드 자체 연결 프로세스를 수행할 수 (이 메서드가 반환 하는 경우에 `S_FALSE`) 또는 연결 프로세스를 지연는 `IDebugEngine2::Attach` 메서드 (의 `OnAttach` 메서드 반환 `S_OK`). 하거나 이벤트에 `OnAttach` 메서드 설정할 수 있습니다는 `GUID` 하려면 디버깅 중인 프로그램의는 주어진 `GUID`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)
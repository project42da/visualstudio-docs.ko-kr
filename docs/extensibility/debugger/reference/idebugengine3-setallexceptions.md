---
title: IDebugEngine3::SetAllExceptions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine3::SetAllExceptions
helpviewer_keywords: IDebugEngine3::SetAllExceptions
ms.assetid: 8f03a6ac-a854-42f7-933c-a2df1b351975
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 33801c7228e9f4b43c76ef3f29f26631bdad5edf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine3setallexceptions"></a>IDebugEngine3::SetAllExceptions
이 메서드는 모든 처리 중인 예외의 상태를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetAllExceptions(  
   EXCEPTION_STATE dwState  
);  
```  
  
```csharp  
int SetAllExceptions(  
   enum_EXCEPTION_STATE dwState  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwState`  
 [in] 중 하나는 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md) 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)
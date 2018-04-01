---
title: IDebugProcessEx2::Detach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProcessEx2::Detach
helpviewer_keywords:
- IDebugProcessEx2::Detach method
ms.assetid: 66d54c2c-9302-47c8-9975-f30ed988ab29
caps.latest.revision: 15
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 40176b654f1a108e995a778eb4c7495b062f6114
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocessex2detach"></a>IDebugProcessEx2::Detach
이 메서드는 세션에서 프로세스를 디버깅 더 이상이 프로세스에 알립니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Detach(   
   IDebugSession2* pSession  
);  
```  
  
```csharp  
int Detach(  
   IDebugSession2 pSession  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pSession`  
 [in] 이 프로세스에서 분리 하는 세션을 고유 하 게 식별 하는 값입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 인터페이스에 전달 `pSession` 쿠키로만 처리이 프로세스에 연결 하는 원래 세션 디버그 관리자를 고유 하 게 식별 하는 값 이며에 제공 된 인터페이스 메서드는 작동 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)
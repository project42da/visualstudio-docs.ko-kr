---
title: IDebugEngine3::SetJustMyCodeState | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine3::SetJustMyCodeState
helpviewer_keywords: IDebugEngine3::SetJustMyCodeState
ms.assetid: 8ec17fbf-df93-424a-b2ed-fd1e5ee51256
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 08d396d378f168b9a54e3b640e69dfeb3f6c9ba1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugengine3setjustmycodestate"></a>IDebugEngine3::SetJustMyCodeState
이 메서드는 JustMyCode 상태 정보에 대 한 디버그 엔진을 지시합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetJustMyCodeState(  
   BOOL           fUpdate,  
   DWORD          dwModules,  
   JMC_CODE_SPEC* rgJMCSpec  
);  
```  
  
```csharp  
int SetJustMyCodeState(  
   int             fUpdate,   
   uint            dwModules,   
   JMC_CODE_SPEC[] rgJMCSpec  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fUpdate`  
 [in] 0이 아닌 (`TRUE`) 현재 정보를 업데이트 하려면 0 (`FALSE`) 모든 정보 (이전에 설정 된 모든 것을 제외)를 다시 설정 합니다.  
  
 `dwModules`  
 [in] 정보 구조 수`rgJMCSpec.`  
  
 `rgJMCSpec`  
 [in] 배열 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md) 구조를 사용 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 JustMyCode 사용자 소유의 코드만 디버깅 하 고 시스템 코드와 같은 모든 중간 코드를 무시 하 여의 개념은-소스 코드를 해당 시스템 코드에 사용할 수 있는 경우에 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)
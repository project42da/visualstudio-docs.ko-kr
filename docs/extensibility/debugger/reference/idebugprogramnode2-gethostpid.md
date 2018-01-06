---
title: IDebugProgramNode2::GetHostPid | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNode2::GetHostPid
helpviewer_keywords: IDebugProgramNode2::GetHostPid
ms.assetid: e65b4b15-46d8-4ca7-9456-2b4c078f7cf9
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: eae4760575d88d89d501517f23b96d0d420320c8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnode2gethostpid"></a>IDebugProgramNode2::GetHostPid
프로그램을 호스트 하는 프로세스에 대 한 시스템 프로세스 식별자를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHostPid (   
   AD_PROCESS_ID * pdwHostPid  
);  
```  
  
```csharp  
int GetHostPid (   
   out AD_PROCESS_ID pdwHostPid  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwHostPid`  
 [out] 호스팅 프로세스에 대 한 시스템 프로세스 식별자를 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 간단한에이 메서드를 구현 하는 방법을 보여 줍니다 `CProgram` 구현 하는 개체는 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스입니다.  
  
```cpp  
HRESULT CProgram::GetHostPid(DWORD* pdwHostPid) {    
    // Check for valid argument.    
   if (pdwHostPid)    
    {    
        // Get the process identifier of the calling process.    
      *pdwHostPid = GetCurrentProcessId();    
  
        return S_OK;    
    }    
  
    return E_INVALIDARG;    
}    
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
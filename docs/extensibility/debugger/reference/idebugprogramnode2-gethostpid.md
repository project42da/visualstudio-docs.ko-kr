---
title: "IDebugProgramNode2::GetHostPid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramNode2::GetHostPid"
helpviewer_keywords: 
  - "IDebugProgramNode2::GetHostPid"
ms.assetid: e65b4b15-46d8-4ca7-9456-2b4c078f7cf9
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugProgramNode2::GetHostPid
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램을 호스팅하는 프로세스의 시스템 프로세스 id를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetHostPid (   
   AD_PROCESS_ID * pdwHostPid  
);  
```  
  
```c#  
int GetHostPid (   
   out AD_PROCESS_ID pdwHostPid  
);  
```  
  
#### 매개 변수  
 `pdwHostPid`  
 \[out\] 호스팅 프로세스의 시스템 프로세스 식별자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 다음 예제에서는 단순에이 메서드를 구현 하는 방법을 보여 줍니다. `CProgram` 를 구현 하는 개체는 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 인터페이스입니다.  
  
```cpp#  
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
  
## 참고 항목  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
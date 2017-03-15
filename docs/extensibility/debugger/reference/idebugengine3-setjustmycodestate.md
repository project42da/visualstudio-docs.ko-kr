---
title: "IDebugEngine3::SetJustMyCodeState | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine3::SetJustMyCodeState"
helpviewer_keywords: 
  - "IDebugEngine3::SetJustMyCodeState"
ms.assetid: 8ec17fbf-df93-424a-b2ed-fd1e5ee51256
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IDebugEngine3::SetJustMyCodeState
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 디버그 엔진 JustMyCode 상태 정보에 대 한 알 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT SetJustMyCodeState(  
   BOOL           fUpdate,  
   DWORD          dwModules,  
   JMC_CODE_SPEC* rgJMCSpec  
);  
```  
  
```c#  
int SetJustMyCodeState(  
   int             fUpdate,   
   uint            dwModules,   
   JMC_CODE_SPEC[] rgJMCSpec  
);  
```  
  
#### 매개 변수  
 `fUpdate`  
 \[in\] 0이 아닌 \(`TRUE`\) 최신 정보를 업데이트 하려면 0 \(`FALSE`\) \(아무 것도 이전에 설정 무시\) 모든 정보를 다시 설정 합니다.  
  
 `dwModules`  
 \[in\] 정보 구조에 수`rgJMCSpec.`  
  
 `rgJMCSpec`  
 \[in\] 배열 [JMC\_CODE\_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md) 구조를 사용 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 JustMyCode 되어 사용자에 게 속한 코드만 디버깅 및 시스템 코드와 같은 모든 중간 코드를 무시 합니다. 개념\-소스 코드에 대 한 시스템 코드에서 사용할 수 있는 경우에.  
  
## 참고 항목  
 [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)   
 [JMC\_CODE\_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)
---
title: "IDebugThread2::GetName | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugThread2::GetName"
helpviewer_keywords: 
  - "IDebugThread2::GetName"
ms.assetid: eec54b8f-4a0e-4919-b0f9-81d4bd1e0b6f
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugThread2::GetName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스레드 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetName (   
   BSTR* pbstrName  
);  
```  
  
```c#  
int GetName (   
   out string pbstrName  
);  
```  
  
#### 매개 변수  
 `pbstrName`  
 \[out\] 스레드의 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 검색된 이름 항상 표시 될 수 있는 이름입니다. 하 고 스레드가이 이름을 설명 합니다.  스레드 이름 지원 스레드에 명명 하거나 디버그 엔진에서 파생 된 이름을 수 있습니다 런타임 아키텍처에서 파생 될 수 있습니다.  또는 스레드의 이름을 호출 하 여 설정의 [SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md) 메서드가 있습니다.  
  
## 참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [SetThreadName](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)
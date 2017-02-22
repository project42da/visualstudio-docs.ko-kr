---
title: "IDebugQueryEngine2::GetEngineInterface | Microsoft Docs"
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
  - "IDebugQueryEngine2::GetEngineInterface"
helpviewer_keywords: 
  - "IDebugQueryEngine2::GetEngineInterface"
ms.assetid: ed84aa98-7ec7-48f3-97ae-821090bc3664
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugQueryEngine2::GetEngineInterface
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

사용자 지정 디버그 엔진 \(DE\) 인터페이스를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetEngineInterface(   
   IUnknown** ppUnk  
);  
```  
  
```c#  
int GetEngineInterface(   
   out object ppUnk  
);  
```  
  
#### 매개 변수  
 `ppUnk`  
 \[out\] 반환 된 `IUnknown` 개체가 나타내는 디버그 엔진 \(DE\)와는 DE와 관련 된 다른 올바른 인터페이스를 쿼리할 수 있습니다 \(예를 들어 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) 또는 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)\).  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에서 검색 인터페이스를 통해 호출 세션 디버그 관리자 처리 우회를 잘못 된 상태로 가져오는 또는 디버깅 하는 동안 오류를 생성 하는 SDM에 될 수 있습니다 때문에 결과 인터페이스 주의 해 서 사용 해야 합니다.  
  
## 참고 항목  
 [IDebugQueryEngine2](../../../extensibility/debugger/reference/idebugqueryengine2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
---
title: "IDebugEngineProgram2::WatchForThreadStep | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngineProgram2::WatchForThreadStep"
helpviewer_keywords: 
  - "IDebugEngineProgram2::WatchForThreadStep"
ms.assetid: b70922a3-1313-409a-b3b7-50c7cd13e394
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugEngineProgram2::WatchForThreadStep
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

실행에 대 한 감시를 실행에 대 한 감시를 중단 주어진된 스레드에서 발생 합니다.  
  
## 구문  
  
```cpp#  
HRESULT WatchForThreadStep(   
   IDebugProgram2* pOriginatingProgram,  
   DWORD           dwTid,  
   BOOL            fWatch,  
   DWORD           dwFrame  
);  
```  
  
```c#  
int WatchForThreadStep(   
   IDebugProgram2 pOriginatingProgram,  
   uint           dwTid,  
   int            fWatch,  
   uint           dwFrame  
);  
```  
  
#### 매개 변수  
 `pOriginatingProgram`  
 \[in\] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 실행 되는 프로그램을 나타내는 개체입니다.  
  
 `dwTid`  
 \[in\] 스레드를 감시 하는 식별자를 지정 합니다.  
  
 `fWatch`  
 \[in\] 0이 아닌 \(`TRUE`\) 의미를 시작 감시 하에서 식별 되는 스레드 실행에 대 한 `dwTid`. 그렇지 않으면 0 \(`FALSE`\) 수단을 중지에서 실행에 대 한 감시 `dwTid`.  
  
 `dwFrame`  
 \[in\] 단계 유형을 제어 하는 프레임 인덱스를 지정 합니다.  이 때 값은 0입니다 "단계별" 단계 형식이 고 스레드 식별 될 때마다 프로그램이 중지 해야 `dwTid` 를 실행 합니다.  때 `dwFrame` 0,이 "위에 step" 고만 스레드를 식별 하 여 경우 프로그램을 중지 단계 유형입니다 `dwTid` 인덱스 포함 되어 동일 하거나 보다 스택에 더 높은 프레임에서 실행 하는 `dwFrame`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 때로 식별 되는 프로그램을 단계를 세션 디버그 매니저 \(SDM\)는 `pOriginatingProgram` 매개 변수를 해당 알립니다 모든 다른 연결 된 프로그램이이 메서드를 호출 하 여.  
  
 이 메서드가 동일한 스레드를 단계별로 실행에 적용 됩니다.  
  
## 참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
---
title: "IDebugProgram3::ExecuteOnThread | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugProgram3::ExecuteOnThread"
ms.assetid: 2f5211e3-7a3f-47bf-9595-dfc8b4895d0d
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram3::ExecuteOnThread
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버거에서 프로그램을 실행합니다.  프로그램을 실행 하는 동안 사용자는 스레드를 보는 디버거 정보를 제공 하는 스레드가 반환 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT ExecuteOnThread(  
   [in] IDebugThread2* pThread)  
```  
  
```c#  
int ExecuteOnThread(  
   IDebugThread2 pThread  
);  
```  
  
#### 매개 변수  
 `pThread`  
 \[in\] [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버거 실행 중지 후 다시 시작 하는 세 가지 방법이 있습니다.  
  
-   실행 합니다: 모든 이전 단계를 취소 하 고에 다음 중단점까지 실행 합니다.  
  
-   단계: 모든 이전 단계를 취소 하 고 새 단계가 완료 될 때까지 실행 됩니다.  
  
-   계속: 다시 실행 하 고 이전 단계를 활성 상태로 둡니다.  
  
 스레드에 전달 `ExecuteOnThread` 는 취소 하려면 단계를 결정할 때 유용 합니다.  실행 실행 하는 스레드를 모르는 경우 모든 단계를 취소 합니다.  스레드 정보를 단계에서 활성 스레드를 취소 하려면 필요 합니다.  
  
## 참고 항목  
 [실행](../../../extensibility/debugger/reference/idebugprogram2-execute.md)   
 [IDebugProgram3](../../../extensibility/debugger/reference/idebugprogram3.md)
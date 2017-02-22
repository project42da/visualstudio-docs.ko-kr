---
title: "IDebugThread2::SetNextStatement | Microsoft Docs"
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
  - "IDebugThread2::SetNextStatement"
helpviewer_keywords: 
  - "IDebugThread2::SetNextStatement"
ms.assetid: 9e2834dd-4ecf-45af-8e6c-f9318ebdac06
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugThread2::SetNextStatement
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

현재 명령 포인터를 지정 된 코드 컨텍스트를 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT SetNextStatement (   
   IDebugStackFrame2*  pStackFrame,  
   IDebugCodeContext2* pCodeContext  
);  
```  
  
```c#  
int SetNextStatement (   
   IDebugStackFrame2  pStackFrame,  
   IDebugCodeContext2 pCodeContext  
);  
```  
  
#### 매개 변수  
 `pStackFrame`  
 나중에 사용 하도록 예약 됩니다. null 값으로 설정 합니다.  
  
 `pCodeContext`  
 \[in\] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 실행 될 코드 위치를 설명 하는 개체와 그 컨텍스트.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  다른 가능한 값은 다음과 같습니다.  
  
|값|설명|  
|-------|--------|  
|E\_CANNOT\_SET\_NEXT\_STATEMENT\_ON\_NONLEAF\_FRAME|다음 문을 스택 프레임 프레임 스택에 더 깊은 될 수 없습니다.|  
|E\_CANNOT\_SETIP\_TO\_DIFFERENT\_FUNCTION|다음 문은 스택의 모든 프레임에 연결 된 수 없습니다.|  
|E\_CANNOT\_SET\_NEXT\_STATEMENT\_ON\_EXCEPTION|일부 디버그 엔진 예외 발생 후 다음 문을 설정할 수 없습니다.|  
  
## 설명  
 다음 명령이 나 문을 실행 하는 명령 포인터를 나타냅니다.  이 메서드는 소스 코드 줄을 다시 시도 하십시오 또는 다른 함수에, 예를 들어 계속 실행할 강제로 사용 됩니다.  
  
## 참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
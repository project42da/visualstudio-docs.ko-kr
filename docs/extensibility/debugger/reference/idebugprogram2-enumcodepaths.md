---
title: "IDebugProgram2::EnumCodePaths | Microsoft Docs"
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
  - "IDebugProgram2::EnumCodePaths"
helpviewer_keywords: 
  - "IDebugProgram2::EnumCodePaths"
ms.assetid: fb100c3c-9c29-4d63-bd1f-a3e531cb395f
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::EnumCodePaths
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

소스 파일에서 지정 된 위치에 대 한 코드 경로 목록을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumCodePaths(   
   LPCOLESTR            pszHint,  
   IDebugCodeContext2*  pStart,  
   IDebugStackFrame2*   pFrame,  
   BOOL                 fSource,  
   IEnumCodePaths2**    ppEnum,  
   IDebugCodeContext2** ppSafety  
);  
```  
  
```c#  
int EnumCodePaths(   
   string                 pszHint,  
   IDebugCodeContext2     pStart,  
   IDebugStackFrame2      pFrame,  
   Int                    fSource,  
   out IEnumCodePaths2    ppEnum,  
   out IDebugCodeContext2 ppSafety  
);  
```  
  
#### 매개 변수  
 `pszHint`  
 \[in\] 커서 아래의 단어가 있는  **원본** 또는  **디스어셈블리** ide에서 보기.  
  
 `pStart`  
 \[in\] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 코드는 현재 컨텍스트를 나타내는 개체입니다.  
  
 `pFrame`  
 \[in\] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) 현재 중단점에 연결 된 스택 프레임을 나타내는 개체입니다.  
  
 `fSource`  
 \[in\] 0이 아닌 \(`TRUE`\)에  **소스** 보기 또는 0 \(`FALSE`\)에 있는  **디스어셈블리** 보기.  
  
 `ppEnum`  
 \[out\] 반환 된 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md) 코드 경로 목록을 포함 하는 개체입니다.  
  
 `ppSafety`  
 \[out\] 반환 된 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 입니다 건너뛴 코드 경로 선택한 경우에는 중단점을 설정할 수 있는 추가 코드 컨텍스트를 나타내는 개체입니다.  예를 들어 short\-circuited 부울 식의 경우 발생할 수 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 메서드 또는 실행 프로그램의 현재 시점에 호출 된 함수 이름을 코드 경로 설명 합니다.  코드 경로 목록을 호출 스택을 나타냅니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
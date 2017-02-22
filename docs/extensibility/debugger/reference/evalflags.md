---
title: "EVALFLAGS | Microsoft Docs"
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
  - "EVALFLAGS"
helpviewer_keywords: 
  - "EVALFLAGS 열거형"
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# EVALFLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

식 계산을 제어 하는 플래그를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```c#  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## Members  
 EVAL\_RETURNVALUE  
 있는 경우 반환 값을 계산할 수를 지정 합니다.  
  
 EVAL\_NOSIDEEFFECTS  
 부작용을 사용할 수 없음을 지정 합니다.  
  
 EVAL\_ALLOWBPS  
 중단 중단점을 지정합니다.  
  
 EVAL\_ALLOWERRORREPORT  
 호스트를 허용 하려면 보고 오류를 지정 합니다.  식 계산에서 Internet Explorer 스크립트에서 주로 사용 합니다.  
  
 EVAL\_FUNCTION\_AS\_ADDRESS  
 함수를 호출 하는 대신 주소를로 평가 될 수 강제로 작동 합니다.  
  
 EVAL\_NOFUNCEVAL  
 함수를에서 평가 되지 않습니다.  예로 `int` 토큰 식에서 `myExpression(int) + 10`.  주소를 있지만 않는 값으로이 함수를 정확 하 게 평가할 수 있습니다.  
  
 EVAL\_NOEVENTS  
 식 계산 중에 발생 하는 이벤트 세션 디버그 매니저 \(SDM\) 또는 IDE 보내지도록 없습니다 나타내는 플래그입니다.  
  
## 설명  
 이러한 플래그에 대 한 인수로 전달 되는 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 및 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) 방법입니다.  
  
 비트 OR로 이러한 플래그를 조합할 수 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)
---
title: "EVALFLAGS90 | Microsoft Docs"
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
  - "EVALFLAGS90 열거형"
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# EVALFLAGS90
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

유효한 값은 식 계산을 제어 하는 플래그를 열거 합니다.  이 열거형에 확장 되는 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 열거형입니다.  
  
## 구문  
  
```cpp#  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```c#  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### 매개 변수  
 EVAL90\_RETURNVALUE  
 있는 경우 반환 값을 계산할 수를 지정 합니다.  
  
 EVAL90\_NOSIDEEFFECTS  
 부작용을 사용할 수 없음을 지정 합니다.  
  
 EVAL90\_ALLOWBPS  
 중단 중단점을 지정합니다.  
  
 EVAL90\_ALLOWERRORREPORT  
 될 수 있는 호스트에 보고 하는 오류를 지정 합니다.  식 계산에서 Internet Explorer 스크립트에서 주로 사용 합니다.  
  
 EVAL90\_FUNCTION\_AS\_ADDRESS  
 함수를 호출 하는 대신 주소를로 평가 될 수 강제로 작동 합니다.  
  
 EVAL90\_NOFUNCEVAL  
 함수를에서 평가 되지 않습니다.  예로 `int` 토큰 식에서 `myExpression(int) + 10`.  주소를 있지만 않는 값으로이 함수를 정확 하 게 평가할 수 있습니다.  
  
 EVAL90\_NOEVENTS  
 식 계산 중에 발생 하는 이벤트 세션 디버그 매니저 \(SDM\) 또는 IDE 보내지도록 없습니다 나타내는 플래그입니다.  
  
 EVAL90\_DESIGN\_TIME\_EXPR\_EVAL  
 디자인 타임 식 계산을 활성화 합니다.  
  
 EVAL90\_ALLOW\_IMPLICIT\_VARS  
 암시적 변수를 만들 수 있습니다.  
  
 EVAL90\_FORCE\_EVALUATION\_NOW  
 즉시 수행 되도록 힘 평가 합니다.  사용자 요청과 같은 요청을 서비스 하는 경우에 유용 합니다.  
  
## 요구 사항  
 헤더: Msdbg90.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
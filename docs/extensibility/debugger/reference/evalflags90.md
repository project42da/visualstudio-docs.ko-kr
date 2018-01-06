---
title: EVALFLAGS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 80f281e65d4dd7b2df24233552bdc46d4b29bebe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="evalflags90"></a>EVALFLAGS90
식 계산을 제어 하는 플래그에 대 한 유효한 값을 열거 합니다. 이 열거형 확장는 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 열거 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
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
  
```csharp  
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
  
#### <a name="parameters"></a>매개 변수  
 EVAL90_RETURNVALUE  
 있는 경우 반환 값을 평가할 지정 합니다.  
  
 EVAL90_NOSIDEEFFECTS  
 파생 작업이 허용 되지 않음을 지정 합니다.  
  
 EVAL90_ALLOWBPS  
 중단점에서 중지를 지정합니다.  
  
 EVAL90_ALLOWERRORREPORT  
 해당 오류를 사용 하려면 호스트에 보고를 지정 합니다. Internet Explorer에서 스크립트에서 식 평가에 주로 사용 됩니다.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 함수를 호출 하는 대신 주소로 평가 될 강제로 함수입니다.  
  
 EVAL90_NOFUNCEVAL  
 확인할 함수를 방지 합니다. 예를 들어는 `int` 식에 토큰 `myExpression(int) + 10`합니다. 이 함수는 주소로 시 키 지 않고 값을 올바르게 평가할 수 있습니다.  
  
 EVAL90_NOEVENTS  
 식 평가 중 발생 하는 이벤트 보내지 않아야 세션 디버그 관리자 (SDM) 또는 IDE에 표시 하는 플래그입니다.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 디자인 타임 식 계산을 사용 하도록 설정 합니다.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 암시적 변수 만들기를 허용 합니다.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 즉시 실행 되도록 평가 수행 하도록 합니다. 사용자 요청과 같은 요청을 처리 하는 경우에 유용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
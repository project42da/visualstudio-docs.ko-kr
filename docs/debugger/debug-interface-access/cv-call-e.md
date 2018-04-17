---
title: CV_call_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fbfde2000b0d22241d795cbb89aa8c28fc330293
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="cvcalle"></a>CV_call_e
함수에 대 한 호출 규칙을 지정합니다.  
  
> [!NOTE]
>  가장 일반적인 열거형 값만 여기에 설명 되어 있습니다. 전체 열거형은 cvconst.h 헤더 파일에 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
typedef enum CV_call_e {   
   CV_CALL_NEAR_C    = 0x00,  
   CV_CALL_NEAR_FAST = 0x04,  
   CV_CALL_NEAR_STD  = 0x07,  
   CV_CALL_NEAR_SYS  = 0x09,  
   CV_CALL_THISCALL  = 0x0b,  
   CV_CALL_CLRCALL   = 0x16  
} CV_call_e;  
```  
  
## <a name="elements"></a>요소  
 CV_CALL_NEAR_C  
 Near 오른쪽에서 왼쪽으로 푸시를 사용 하 여 함수 호출 규칙을 지정 합니다. 호출 함수의 스택을 지웁니다.  
  
 CV_CALL_NEAR_FAST  
 레지스터와 가까운 왼쪽에서 오른쪽 푸시를 사용 하 여 함수 호출 규칙을 지정 합니다. 호출된 된 함수 매개 변수 바이트를 사용 하 여 스택을 지웁니다.  
  
 CV_CALL_NEAR_STD  
 Near 표준 호출 (오른쪽에서 왼쪽으로 푸시)을 사용 하는 함수 호출 규칙을 지정 합니다.  
  
 CV_CALL_NEAR_SYS  
 Near 시스템 호출을 사용 하는 함수 호출 규칙을 지정 합니다.  
  
 CV_CALL_THISCALL  
 사용 하 여 함수 호출 규칙 지정 `this` 호출 (`this` 포인터 레지스터에서 전달).  
  
 CV_CALL_CLRCALL  
 여는 CLR 공용 언어 런타임 () (또는 관리 되는 코드를 호출 규칙)를 사용 되는 함수 호출 규칙을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값에 대 한 호출에서 반환될지는 [idiasymbol:: Get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
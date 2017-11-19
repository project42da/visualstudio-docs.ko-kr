---
title: "JS_NATIVE_FRAME 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: JS_NATIVE_FRAME
apilocation: jscript9diag.dll
ms.assetid: 5afa2ee1-b3e2-47cb-b304-84f96e6fbb14
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c7e93041a6dec767cb3bb11382abfb562068c925
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsnativeframe-structure"></a>JS_NATIVE_FRAME 구조체
스택 프레임을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct {  
    UINT64 InstructionOffset;    UINT64 ReturnOffset;    UINT64 FrameOffset;    UINT64 StackOffset;  
} JS_NATIVE_FRAME;  
```  
  
## <a name="members"></a>멤버  
 `InstructionOffset`  
 명령 포인터입니다.  
  
 `ReturnOffset`  
 반환 주소입니다.  
  
 `FrameOffset`  
 프레임 포인터입니다.  
  
 `StackOffset`  
 스택 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `JS_NATIVE_FRAME` 구조체에서 사용 하는 `IJsStackFrameEnumerator`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)
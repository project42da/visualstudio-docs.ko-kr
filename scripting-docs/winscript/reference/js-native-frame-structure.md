---
title: "JS_NATIVE_FRAME 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: JS_NATIVE_FRAME
apilocation: jscript9diag.dll
ms.assetid: 5afa2ee1-b3e2-47cb-b304-84f96e6fbb14
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# JS_NATIVE_FRAME 구조체
스택 프레임을 나타냅니다.  
  
## 구문  
  
```  
typedef struct {  
    UINT64 InstructionOffset;  
    UINT64 ReturnOffset;  
    UINT64 FrameOffset;  
    UINT64 StackOffset;  
} JS_NATIVE_FRAME;  
```  
  
## Members  
 `InstructionOffset`  
 명령 포인터입니다.  
  
 `ReturnOffset`  
 반환 주소입니다.  
  
 `FrameOffset`  
 프레임에 대 한 포인터입니다.  
  
 `StackOffset`  
 스택 포인터입니다.  
  
## 설명  
 `JS_NATIVE_FRAME` 구조체는 `IJsStackFrameEnumerator`에서 사용됩니다.  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)
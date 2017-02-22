---
title: "CV_call_e | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CV_call_e 열거형"
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# CV_call_e
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

함수의 호출 규칙을 지정합니다.  
  
> [!NOTE]
>  여기 가장 일반적인 열거형 값이 나와 있습니다.  전체 열거의 cvconst.h 헤더 파일을 사용할 수 있습니다.  
  
## 구문  
  
```cpp#  
typedef enum CV_call_e {   
   CV_CALL_NEAR_C    = 0x00,  
   CV_CALL_NEAR_FAST = 0x04,  
   CV_CALL_NEAR_STD  = 0x07,  
   CV_CALL_NEAR_SYS  = 0x09,  
   CV_CALL_THISCALL  = 0x0b,  
   CV_CALL_CLRCALL   = 0x16  
} CV_call_e;  
```  
  
## Elements  
 CV\_CALL\_NEAR\_C  
 가까운 오른쪽에서 왼쪽으로 푸시를 사용 하 여 함수 호출 규칙을 지정 합니다.  호출 하는 함수는 스택을 지웁니다.  
  
 CV\_CALL\_NEAR\_FAST  
 가까운 왼쪽에서 오른쪽으로 밀어넣기 레지스터를 사용 하는 함수 호출 규칙을 지정 합니다.  호출된 되는 함수 매개 변수의 바이트 수의 합계를 사용 하 여 스택을 선택 취소 합니다.  
  
 CV\_CALL\_NEAR\_STD  
 거의 표준 호출 \(왼쪽으로 오른쪽 누름\)을 사용 하는 함수의 호출 규칙을 지정 합니다.  
  
 CV\_CALL\_NEAR\_SYS  
 거의 시스템 호출을 사용 하 여 함수 호출 규칙을 지정 합니다.  
  
 CV\_CALL\_THISCALL  
 사용 하 여 함수 호출 규칙을 지정 합니다. `this` 호출 \(`this` 레지스터에 전달\).  
  
 CV\_CALL\_CLRCALL  
 CLR \(공용 언어 런타임 여\) \(호출 규칙이 라고도 하는 관리 되는 코드\)에 사용 되는 함수 호출 규칙을 지정 합니다.  
  
## 설명  
 값이 열거형에서를 호출 하 여 반환 되는 [IDiaSymbol::get\_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md) 메서드.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get\_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
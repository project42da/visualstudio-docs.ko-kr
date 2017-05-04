---
title: "APPBREAKFLAGS 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: APPBREAKFLAGS
apilocation: scrobj.dll
helpviewer_keywords: 
  - "APPBREAKFLAGS 상수"
ms.assetid: ea8ed80f-2ddb-4800-bb3b-52b76ba6c7a0
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# APPBREAKFLAGS 열거형
응용 프로그램 및 스레드에 대 한 현재 디버그 상태를 나타냅니다.  
  
## 구문  
  
```cpp  
enum enum_APPBREAKFLAGS  
{  
APPBREAKFLAG_DEBUGGER_BLOCK= 0x00000001,  
APPBREAKFLAG_DEBUGGER_HALT= 0x00000002,  
APPBREAKFLAG_STEP= 0x00010000,  
APPBREAKFLAG_NESTED= 0x00020000,  
APPBREAKFLAG_STEPTYPE_SOURCE= 0x00000000,  
APPBREAKFLAG_STEPTYPE_BYTECODE= 0x00100000,  
APPBREAKFLAG_STEPTYPE_MACHINE= 0x00200000,  
APPBREAKFLAG_STEPTYPE_MASK= 0x00F00000,  
APPBREAKFLAG_IN_BREAKPOINT= 0x80000000  
};  
  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|APPBREAKFLAG\_DEBUGGER\_BLOCK|0x00000001|언어 엔진은 BREAKREASON\_DEBUGGER\_BLOCK와 모든 스레드를 즉시 중단 해야 합니다.|  
|APPBREAKFLAG\_DEBUGGER\_HALT|0x00000002|언어 엔진 BREAKREASON\_DEBUGGER\_HALT을 즉시 중단 해야 합니다.|  
|APPBREAKFLAG\_STEP|0x00010000|언어 엔진 BREAKREASON\_STEP와 스테핑 스레드를 즉시 중단 해야 합니다.|  
|APPBREAKFLAG\_NESTED|0x00020000|중단점에서 실행을 중첩 된 응용 프로그램이입니다.|  
|APPBREAKFLAG\_STEPTYPE\_SOURCE|0x00000000|디버거에서 소스 수준 단계별 실행입니다.|  
|APPBREAKFLAG\_STEPTYPE\_BYTECODE|0x00100000|디버거 바이트 코드 수준 단계별 실행 됩니다.|  
|APPBREAKFLAG\_STEPTYPE\_MACHINE|0x00200000|디버거 컴퓨터 수준 단계별 실행입니다.|  
|APPBREAKFLAG\_STEPTYPE\_MASK|0x00F00000|단계 유형을 분류 하는 마스크입니다.|  
|APPBREAKFLAG\_IN\_BREAKPOINT|0x80000000|중단점은 진행 중입니다.|  
  
## 설명  
 단계별 실행 모드 디버거를 다른 플래그를 지정 하는 동안 언어 엔진 다음 기회에 중단 해야 몇 가지 플래그를 지정 합니다.  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)   
 [BREAKREASON 열거형](../../winscript/reference/breakreason-enumeration.md)
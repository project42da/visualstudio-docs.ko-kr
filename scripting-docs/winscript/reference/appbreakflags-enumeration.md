---
title: "APPBREAKFLAGS 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- APPBREAKFLAGS
apilocation:
- scrobj.dll
helpviewer_keywords:
- APPBREAKFLAGS constants
ms.assetid: ea8ed80f-2ddb-4800-bb3b-52b76ba6c7a0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 126dcd704a60b591b71913f2e8e739de35c14636
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="appbreakflags-enumeration"></a>APPBREAKFLAGS 열거형
현재 응용 프로그램 및 스레드에 대한 디버그 상태를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_APPBREAKFLAGS{APPBREAKFLAG_DEBUGGER_BLOCK= 0x00000001,APPBREAKFLAG_DEBUGGER_HALT= 0x00000002,APPBREAKFLAG_STEP= 0x00010000,APPBREAKFLAG_NESTED= 0x00020000,APPBREAKFLAG_STEPTYPE_SOURCE= 0x00000000,APPBREAKFLAG_STEPTYPE_BYTECODE= 0x00100000,APPBREAKFLAG_STEPTYPE_MACHINE= 0x00200000,APPBREAKFLAG_STEPTYPE_MASK= 0x00F00000,APPBREAKFLAG_IN_BREAKPOINT= 0x80000000};  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|APPBREAKFLAG_DEBUGGER_BLOCK|0x00000001|언어 엔진이 BREAKREASON_DEBUGGER_BLOCK와 모든 스레드에서 즉시 중단 해야 합니다.|  
|APPBREAKFLAG_DEBUGGER_HALT|0x00000002|언어 엔진이 BREAKREASON_DEBUGGER_HALT와 즉시 중단 해야 합니다.|  
|APPBREAKFLAG_STEP|0x00010000|언어 엔진이 BREAKREASON_STEP 단계별 실행 스레드 즉시 중단 해야 합니다.|  
|APPBREAKFLAG_NESTED|0x00020000|응용 프로그램을 중단점에서 실행을 중첩된 합니다.|  
|APPBREAKFLAG_STEPTYPE_SOURCE|0x00000000|디버거는 소스 수준에서 단계별 실행 합니다.|  
|APPBREAKFLAG_STEPTYPE_BYTECODE|0x00100000|디버거는 바이트 코드 수준에서 단계별 실행 합니다.|  
|APPBREAKFLAG_STEPTYPE_MACHINE|0x00200000|디버거는 시스템 수준에서 단계별 실행 합니다.|  
|APPBREAKFLAG_STEPTYPE_MASK|0x00F00000|단계 유형이 서비스에 대 한 마스크입니다.|  
|APPBREAKFLAG_IN_BREAKPOINT|0x80000000|중단점 진행 중입니다.|  
  
## <a name="remarks"></a>설명  
 일부 언어 엔진을 나눔을 다음 기회에 다른 플래그는 디버거에서의 단계별 실행 모드를 지정 하는 동안 지정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)   
 [BREAKREASON 열거형](../../winscript/reference/breakreason-enumeration.md)
---
title: "DebugStackFrameDescriptor 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: DebugStackFrameDescriptor
apilocation: scrobj.dll
helpviewer_keywords: 
  - "DebugStackFrameDescriptor 구조체"
ms.assetid: a86bcb99-41e4-4a26-a1dd-e1458fb73139
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# DebugStackFrameDescriptor 구조체
스택 프레임을 열거 하 고 출력 하면 같은 스레드의 여러 열거자에서 병합 합니다.  
  
## 구문  
  
```  
typedef struct tagDebugStackFrameDescriptor {  
   IDebugStackFrame *pdsf;  
   DWORD_PTR        dwMin;  
   DWORD_PTR        dwLim;  
   BOOL             fFinal;  
   IUnknown         *punkFinal;  
} DebugStackFrameDescriptor;  
```  
  
## Members  
 `pdsf`  
 스택 프레임 개체입니다.  
  
 `dwMin`  
 이 스택 프레임과 연결 된 실제 주소 범위의 컴퓨터에 따라 나타냅니다.  
  
 `dwLim`  
 이 스택 프레임과 연결 된 실제 주소 범위의 상위 시스템에 따라 나타냅니다.  
  
 `fFinal`  
 프레임 처리 중임을 나타내는 플래그입니다.  
  
 `punkFinal`  
 이 매개 변수가 없는 경우 `NULL`현재 열거자 병합을 중지 하 고 새로 시작 해야 합니다.  새 열거를 시작 하는 개체를 나타냅니다.  
  
## 설명  
 프로세스 디버그 관리자가이 구조를 사용 하 여 여러 스크립트 엔진에서 스택 프레임을 정렬 합니다.  규칙에 따라 스택 아래로 증가 합니다.  따라서 스택 위치 자라 아키텍처에서의 보완 주소 여야 합니다.  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)
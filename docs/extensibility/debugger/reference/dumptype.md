---
title: "DUMPTYPE | Microsoft Docs"
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
  - "DUMPTYPE"
helpviewer_keywords: 
  - "DUMPTYPE 열거형"
ms.assetid: ea8160db-8732-4056-a1d7-892ef72da71e
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# DUMPTYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

덤프를 어느 정도 프로그램 상태 \(예: 실행 중인 스레드, 스택 프레임 및 현재 명령 주소\)를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
typedef DWORD DUMPTYPE;  
```  
  
```c#  
public enum enum_DUMPTYPE {   
   DUMP_MINIDUMP = 0,  
   DUMP_FULLDUMP = 1  
};  
```  
  
## Members  
 DUMP\_MINIDUMP  
 작은, 소형 덤프를 지정합니다.  
  
 DUMP\_FULLDUMP  
 대규모의 전체 덤프를 지정합니다.  
  
## 설명  
 인수로 전달 되는 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [WriteDump](../../../extensibility/debugger/reference/idebugprogram2-writedump.md)
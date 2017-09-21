---
title: "IDebugProgram2::WriteDump | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::WriteDump"
helpviewer_keywords: 
  - "IDebugProgram2::WriteDump"
ms.assetid: 375afb8c-882d-44db-bfa7-e2c9eb555122
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugProgram2::WriteDump
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

덤프 파일에 기록 합니다.  
  
## 구문  
  
```cpp#  
HRESULT WriteDump(   
   DUMPTYPE  DumpType,  
   LPCOLESTR pszDumpUrl  
);  
```  
  
```c#  
int WriteDump(   
   enum_DUMPTYPE  DumpType,  
   string         pszDumpUrl  
);  
```  
  
#### 매개 변수  
 `DumpType`  
 \[in\] 값은 [DUMPTYPE](../../../extensibility/debugger/reference/dumptype.md) 덤프의 유형을 지정 예를 들어, 간단한 열거형 또는 장기.  
  
 `pszDumpUrl`  
 \[in\] 덤프를 작성 하는 URL입니다.  일반적으로이 형식으로 된  `file://c:\path\filename.ext`, 모든 유효한 URL 이지만.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 프로그램 덤프를 일반적으로 포함 됩니다 현재 스택 프레임, 스택 자체, 프로그램, 및 프로그램을 소유 하 고 가능한 경우 메모리에서 실행 중인 스레드 목록입니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
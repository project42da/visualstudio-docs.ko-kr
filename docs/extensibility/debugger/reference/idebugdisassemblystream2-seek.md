---
title: "IDebugDisassemblyStream2::Seek | Microsoft Docs"
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
  - "IDebugDisassemblyStream2::Seek"
helpviewer_keywords: 
  - "IDebugDisassemblyStream2::Seek"
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugDisassemblyStream2::Seek
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디스어셈블리 스트림에 지정된 된 명령에 지정 된 위치를 기준으로 수 읽기 포인터를 이동합니다.  
  
## 구문  
  
```cpp#  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```c#  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### 매개 변수  
 `dwSeekStart`  
 \[in\] 값은 [SEEK\_START](../../../extensibility/debugger/reference/seek-start.md) 는 검색 프로세스를 시작 하는 상대 위치를 지정 하는 열거형입니다.  
  
 `pCodeContext`  
 \[in\] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 찾기 작업 기준으로 되는 코드 컨텍스트를 나타내는 개체입니다.  이 매개 변수는 경우에 사용 됩니다 `dwSeekStart` \= `SEEK_START_CODECONTEXT`. 그렇지 않으면이 매개 변수가 무시 되 고 null 값을 사용할 수 있습니다.  
  
 `uCodeLocationId`  
 \[in\] 검색 작업 기준으로 된 코드 위치 식별자입니다.  하는 경우이 매개 변수를 사용 `dwSeekStart` \= `SEEK_START_CODELOCID`. 그렇지 않으면이 매개 변수가 무시 되 고 0으로 설정할 수 있습니다.  비고 섹션을 참고 하십시오를 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) 메서드에 대 한 코드 위치 식별자에 대 한 설명입니다.  
  
 `iInstructions`  
 \[in\] 지정 된 위치에 상대적인 이동 명령의 수를 `dwSeekStart`.  이 값은 뒤로 이동 하는 음수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 경우 검색 위치입니다. 사용할 수 있는 명령 목록 외를 시점으로 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 목록의 처음 이전 위치로 검색 한 경우 첫 번째 명령 목록에서 읽기 위치 설정 됩니다.  읽기 위치 참고 목록 끝 이후 위치를 경우 마지막 명령 목록에 설정 됩니다.  
  
## 참고 항목  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK\_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)
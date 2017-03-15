---
title: "IDebugDisassemblyStream2::Read | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDisassemblyStream2::Read"
helpviewer_keywords: 
  - "IDebugDisassemblyStream2::Read"
ms.assetid: 7db5f6bb-73ee-45bc-b187-c1b6aa2dfdd5
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDisassemblyStream2::Read
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디스어셈블리 스트림 내의 현재 위치에서 시작 하는 지침을 읽습니다.  
  
## 구문  
  
```cpp#  
HRESULT Read(   
   DWORD                     dwInstructions,  
   DISASSEMBLY_STREAM_FIELDS dwFields,  
   DWORD*                    pdwInstructionsRead,  
   DisassemblyData*          prgDisassembly  
);  
```  
  
```c#  
int Read(   
   uint                           dwInstructions,  
   enum_DISASSEMBLY_STREAM_FIELDS dwFields,  
   out uint                       pdwInstructionsRead,  
   DisassemblyData[]              prgDisassembly  
);  
```  
  
#### 매개 변수  
 `dwInstructions`  
 \[in\] 명령 디스어셈블할 수입니다.  이 값의 최대 길이 이기도 `prgDisassembly` 배열입니다.  
  
 `dwFields`  
 \[in\] 플래그의 조합에서 [DISASSEMBLY\_STREAM\_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) 필드를 지정 하는 열거형 `prgDisassembly` 데이터를 입력할 수 있습니다.  
  
 `pdwInstructionsRead`  
 \[out\] 실제로 분리 된 명령의 수를 반환 합니다.  
  
 `prgDisassembly`  
 \[out\] 배열 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 구조의 분해 된 명령 당 하나의 구조 디스어셈블된 코드를 사용 하 여 입력 됩니다.  이 배열의 길이에 따라 되는 `dwInstructions` 매개 변수.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 현재 범위에서 사용할 수 있는 명령 최대 수를 호출 하 여 얻을 수 있는 [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md) 메서드.  
  
 호출 하 여 다음 명령입니다 읽을 위치에서 현재 위치를 변경할 수 있는 [검색](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) 메서드.  
  
 `DSF_OPERANDS_SYMBOLS` 플래그를 추가할 수는 `DSF_OPERANDS` 에 플래그를 지정은 `dwFields` 지침을 분해 하면 기호 이름을 사용 하도록 지정 하려면 매개 변수.  
  
## 참고 항목  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [DISASSEMBLY\_STREAM\_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)   
 [검색](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)
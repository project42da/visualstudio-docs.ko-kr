---
title: "DISASSEMBLY_STREAM_FIELDS | Microsoft Docs"
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
  - "DISASSEMBLY_STREAM_FIELDS"
helpviewer_keywords: 
  - "DISASSEMBLY_STREAM_FIELDS 열거형"
ms.assetid: cfc9b4de-c756-4844-bea7-d9f186a51d1b
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# DISASSEMBLY_STREAM_FIELDS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

필드에 대 한 디스어셈블리를 검색할 정보를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
typedef DWORD DISASSEMBLY_STREAM_FIELDS;  
```  
  
```c#  
public enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
```  
  
## Members  
 DSF\_ADDRESS  
 초기화\/사용의 `bstrAddress` 필드입니다.  
  
 DSF\_ADDRESSOFFSET  
 초기화\/사용의 `bstrAddressOffset` 필드입니다.  
  
 DSF\_CODEBYTES  
 초기화\/사용의 `bstrCodeBytes` 필드입니다.  
  
 DSF\_OPCODE  
 초기화\/사용의 `bstrOpCode` 필드입니다.  
  
 DSF\_OPERANDS  
 초기화\/사용의 `bstrOperands` 필드입니다.  
  
 DSF\_SYMBOL  
 초기화\/사용의 `bstrSymbol` 필드입니다.  
  
 DSF\_CODELOCATIONID  
 초기화\/사용의 `uCodeLocationId` 필드입니다.  
  
 DSF\_POSITION  
 초기화\/사용의 `posBeg` 및 `posEnd` 필드입니다.  
  
 DSF\_DOCUMENTURL  
 초기화\/사용의 `bstrDocumentUrl` 필드입니다.  
  
 DSF\_BYTEOFFSET  
 초기화\/사용의 `dwByteOffset` 필드입니다.  
  
 DSF\_FLAGS  
 초기화\/사용의 `dwFlags` \([DISASSEMBLY\_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)\) 필드입니다.  
  
 DSF\_OPERANDS\_SYMBOLS  
 기호 이름에 포함 되어 있는 `bstrOperands` 필드입니다.  
  
 DSF\_ALL  
 디스어셈블리 스트림에 대 한 모든 필드를 지정합니다.  
  
## 설명  
 매개 변수로 전달 되는 [읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) 필드의 나타내도록 메서드는 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 된 구조를 초기화 합니다.  
  
 사용 되는 `dwFields` 의 멤버는 `DisassemblyData` 구조 구조 반환 될 때 필드 사용 되는 및 잘못 된 것을 나타냅니다.  
  
 이 값이 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [읽기](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY\_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)
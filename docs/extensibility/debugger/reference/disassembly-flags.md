---
title: "DISASSEMBLY_FLAGS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DISASSEMBLY_FLAGS"
helpviewer_keywords: 
  - "DISASSEMBLY_FLAGS 열거형"
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# DISASSEMBLY_FLAGS
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디스어셈블리에 대 한 플래그를 지정합니다.  
  
## 구문  
  
```cpp#  
enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
typedef DWORD DISASSEMBLY_FLAGS;  
```  
  
```c#  
public enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
```  
  
## Members  
 DF\_DOCUMENTCHANGE  
 이 지침은 이전 것과 다른 문서 임을 나타냅니다.  
  
 DF\_DISABLED  
 이 명령을 실행할 수 있음을 나타냅니다.  
  
 DF\_INSTRUCTION\_ACTIVE  
 이 명령을 실행 하려면 다음 지침 중 하나입니다 \(있을 수 둘 이상\).  
  
 DF\_DATA  
 이 명령을 실제 데이터 \(코드\)입니다.  
  
 DF\_HASSOURCE  
 이 명령은 원본 했음을 나타냅니다.  프로 파일링 또는 가비지 컬렉션 코드와 같은 몇 가지 지침을 해당 소스가 있습니다.  
  
 DF\_DOCUMENT\_CHECKSUM  
 `bstrDocumentUrl` 필드 문서 URL 뒤 체크섬 데이터가 포함 됩니다.  비고 섹션을 참고 하십시오를 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 체크섬 데이터 저장 방법에 대 한 구조입니다.  
  
## 설명  
 사용 되는 `dwFlags` 의 멤버는 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 구조.  
  
 이러한 플래그의 비트와 함께 사용할 수 있습니다 `OR`.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
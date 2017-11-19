---
title: DISASSEMBLY_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DISASSEMBLY_FLAGS
helpviewer_keywords: DISASSEMBLY_FLAGS enumeration
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1959b101ed5c2aca4c1d806781952ad4e4e6b1ad
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
디스어셈블리에 대 한 플래그를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
typedef DWORD DISASSEMBLY_FLAGS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
```  
  
## <a name="members"></a>멤버  
 DF_DOCUMENTCHANGE  
 이 명령은 이전 보다 다른 문서에 임을 나타냅니다.  
  
 DF_DISABLED  
 이 명령은 실행 되지 않습니다 나타냅니다.  
  
 DF_INSTRUCTION_ACTIVE  
 이 명령을 실행 하려면 다음 지침 중 하나 임을 나타냅니다 (있을 수 있습니다 하나 이상).  
  
 DF_DATA  
 실제로이 명령이 데이터 (코드) 임을 나타냅니다.  
  
 DF_HASSOURCE  
 이 명령은 소스에 있음을 나타냅니다. 프로 파일링 또는 가비지 컬렉션 번호와 같은 몇 가지 지침 있어야 해당 원본에 없습니다.  
  
 DF_DOCUMENT_CHECKSUM  
 나타냅니다 `bstrDocumentUrl` 필드 문서 URL 후 체크섬 데이터를 포함 합니다. 설명 부분 참조는 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 체크섬 데이터가 저장 되는 방식에 대 한 구조입니다.  
  
## <a name="remarks"></a>설명  
 로 사용 된 `dwFlags` 의 멤버는 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 구조입니다.  
  
 이러한 플래그 비트와 함께 `OR`합니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)
---
title: IDebugDisassemblyStream2::Read | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDisassemblyStream2::Read
helpviewer_keywords: IDebugDisassemblyStream2::Read
ms.assetid: 7db5f6bb-73ee-45bc-b187-c1b6aa2dfdd5
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: edc41da40c4f0c292523ed338419fbc4a7253dcf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdisassemblystream2read"></a>IDebugDisassemblyStream2::Read
디스어셈블리 스트림 내의 현재 위치에서 시작 하는 지침을 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT Read(   
   DWORD                     dwInstructions,  
   DISASSEMBLY_STREAM_FIELDS dwFields,  
   DWORD*                    pdwInstructionsRead,  
   DisassemblyData*          prgDisassembly  
);  
```  
  
```csharp  
int Read(   
   uint                           dwInstructions,  
   enum_DISASSEMBLY_STREAM_FIELDS dwFields,  
   out uint                       pdwInstructionsRead,  
   DisassemblyData[]              prgDisassembly  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwInstructions`  
 [in] 디스어셈블 명령의 수입니다. 또한이 값은의 최대 길이 `prgDisassembly` 배열입니다.  
  
 `dwFields`  
 [in] 플래그의 조합 된 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md) 의 필드를 나타내는 열거형 `prgDisassembly` 작성 됩니다.  
  
 `pdwInstructionsRead`  
 [out] 실제로 디스어셈블 명령의 수를 반환 합니다.  
  
 `prgDisassembly`  
 [out] 배열을 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) 구조를 디스어셈블된 명령 당 하나의 구조와 디스어셈블된 코드를 사용 하 여 채워집니다. 이 배열의 길이 따라 결정 됩니다는 `dwInstructions` 매개 변수입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 호출 하 여 현재 범위에서 사용할 수 있는 명령의 최대 수를 가져올 수 있습니다는 [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md) 메서드.  
  
 호출 하 여 현재 위치에서 다음 명령이 읽기 위치를 변경할 수는 [Seek](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md) 메서드.  
  
 `DSF_OPERANDS_SYMBOLS` 플래그에 추가할 수 있습니다는 `DSF_OPERANDS` 플래그는 `dwFields` 지침 디스어셈블할 때는 기호 이름을 사용 해야 함을 나타내는 매개 변수를 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [DISASSEMBLY_STREAM_FIELDS](../../../extensibility/debugger/reference/disassembly-stream-fields.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [GetSize](../../../extensibility/debugger/reference/idebugdisassemblystream2-getsize.md)   
 [검색](../../../extensibility/debugger/reference/idebugdisassemblystream2-seek.md)
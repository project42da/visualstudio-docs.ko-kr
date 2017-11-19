---
title: IDebugProgramEngines2::EnumPossibleEngines | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramEngines2::EnumPossibleEngines
helpviewer_keywords: IDebugProgramEngines2::EnumPossibleEngines
ms.assetid: 993d70a4-f6a5-4e47-a603-0b162b9fde00
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d1cf3eead4b268dbbca5ad4333adcc647522b051
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugprogramengines2enumpossibleengines"></a>IDebugProgramEngines2::EnumPossibleEngines
모든 가능한 있는 디버그 엔진 (DE)이이 프로그램을 디버깅할 수에 대 한 Guid를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT EnumPossibleEngines(   
   DWORD  celtBuffer,  
   GUID*  rgguidEngines,  
   DWORD* pceltEngines  
);  
```  
  
```csharp  
int EnumPossibleEngines(   
   uint      celtBuffer,  
   GUID[]    rgguidEngines,  
   ref DWORD pceltEngines  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celtBuffer`  
 [in] 반환할 DE Guid 수입니다. 최대 크기 지정은 `rgguidEngines` 배열입니다.  
  
 `rgguidEngines`  
 [out에서] 배열 채울 DE Guid입니다.  
  
 `pceltEngines`  
 [out] 반환 되는 DE Guid의 실제 수를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그러지 않으면 오류 코드가 반환 됩니다. [C + +] 반환 `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` 또는 [C#] 0x8007007A 버퍼가 충분히 큰 경우.  
  
## <a name="remarks"></a>설명  
 엔진 수를 확인 하기 위해 한 번이 메서드를 호출 하는 `celtBuffer` 매개 변수를 0으로 설정 및 `rgguidEngines` 매개 변수는 null 값으로 설정 합니다. 반환 합니다. `HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)` (C#에 대 한 0x8007007A) 및 `pceltEngines` 매개 변수 버퍼의 필요한 크기를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramEngines2](../../../extensibility/debugger/reference/idebugprogramengines2.md)
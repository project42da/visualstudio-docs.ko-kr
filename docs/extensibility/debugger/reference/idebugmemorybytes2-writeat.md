---
title: IDebugMemoryBytes2::WriteAt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4d1d79d88baf9688fe68ff44d59dcd4d19baf9f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
지정 된 수가 지정된 된 주소에서 시작 하는 메모리의 바이트를 씁니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT WriteAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory  
);  
```  
  
```csharp  
int WriteAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 바이트 쓰기를 시작할 위치를 지정 하는 개체입니다.  
  
 `dwCount`  
 [in] 쓸 바이트 수입니다.  
  
 `rgbMemory`  
 [in] 쓸 바이트입니다. 이 배열은 적어도 것으로 간주 됩니다 `dwCount` 바이트 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`, 그렇지 않으면 반환 `S_FALSE` 모든 바이트를 작성할 수 또는 오류 코드를 반환 하는 경우 (일반적으로 `E_FAIL`).  
  
## <a name="remarks"></a>설명  
 시작 주소 받았습니다 표시 하는 메모리 창의 내 없으면 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) 개체 쓰기 발생 하 고 오류 코드 `E_FAIL` 반환 됩니다-작성할 양을 메모리 공간에 겹치는 경우에 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
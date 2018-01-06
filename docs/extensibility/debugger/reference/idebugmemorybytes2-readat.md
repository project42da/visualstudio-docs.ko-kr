---
title: IDebugMemoryBytes2::ReadAt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f4c71da3152394442d63c937b77e4f6538fcc1ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
지정된 된 위치에서 시작 하는 바이트의 시퀀스를 읽습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT ReadAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory,  
   DWORD*                pdwRead,  
   DWORD*                pdwUnreadable  
);  
```  
  
```csharp  
int ReadAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory,  
   out uint             pdwRead,  
   ref uint             pdwUnreadable  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 바이트 읽기를 시작할 위치를 지정 하는 개체입니다.  
  
 `dwCount`  
 [in] 읽을 바이트 수입니다. 또한의 길이 지정 된 `rgbMemory` 배열입니다.  
  
 `rgbMemory`  
 [out에서] 실제로 읽은 바이트를 사용 하 여 입력 하는 배열입니다.  
  
 `pdwRead`  
 [out] 실제로 읽는 연속 된 바이트 수를 반환 합니다.  
  
 `pdwUnreadable`  
 [out에서] 읽을 수 없는 바이트 수를 반환합니다. 클라이언트가 읽을 수 없는 바이트 수에 관심이 있으면 null 값이 될 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 s_ok이 고; 반환 그렇지 않은 경우 오류 코드를 반환합니다.  
  
## <a name="remarks"></a>설명  
 100 바이트 요청 및 첫 번째 50을 읽을 수, 다음 20 개 읽을 수는 않으며 나머지 30 대가 읽을 수 있는,이 메서드를 반환 합니다.  
  
 *`pdwRead` = 50  
  
 *`pdwUnreadable` = 20  
  
 이 경우 때문에 `*pdwRead + *pdwUnreadable < dwCount`, 호출자에 게 요청 된 원래 100의 나머지 30 바이트를 읽으려고 추가 호출 해야 합니다. 및 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) 에 전달 된 개체는 `pStartContext` 매개 변수 이동 70입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
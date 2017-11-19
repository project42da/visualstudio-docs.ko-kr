---
title: IDebugApplication110::CallableWaitForHandles | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugApplication110::CallableWaitForHandles
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b259f5296f8e0b32def793a81e4c2e1069643306
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
신호를 받을 수 있도록 하는 동안 지정 된 핸들에 대 한 대기 크로스 스레드 호출 본에 게시 합니다. 디버거 스레드에서이 메서드를 호출 해야 합니다.  
  
> [!IMPORTANT]
>  [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `handleCount`  
 대기 핸들의 수입니다.  
  
 `pHandles`  
 집합에 대 한 대기에 대 한 핸들입니다.  
  
 `pIndex`  
 HRESULT 값이 s_ok이 고에 대 한 인덱스 `pHandles` 신호를 받은 핸들에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md)
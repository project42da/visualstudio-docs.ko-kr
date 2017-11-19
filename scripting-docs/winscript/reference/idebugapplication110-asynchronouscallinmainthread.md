---
title: IDebugApplication110::AsynchronousCallInMainThread | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IDebugApplication110::AsynchronousCallInMainThread
ms.assetid: 13b80ff0-4bed-48c1-8031-d4147b51bf6c
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 236a6585d5d5844f282d8ecf5820ac8fdfb49648
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplication110asynchronouscallinmainthread"></a>IDebugApplication110::AsynchronousCallInMainThread
주 스레드에서 비동기 호출을 만듭니다.  
  
> [!IMPORTANT]
>  [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT AsynchronousCallInMainThread([in] IDebugThreadCall* pptc, [in] DWORD_PTR dwParam1, [in] DWORD_PTR dwParam2, [in] DWORD_PTR dwParam3);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pptc`  
 [IDebugThreadCall 인터페이스](../../winscript/reference/idebugthreadcall-interface.md) 호출할 개체입니다.  
  
 `dwParam1`  
 호출의 첫 번째 매개 변수입니다.  
  
 `dwParam1`  
 호출의 첫 번째 매개 변수입니다.  
  
 `dwParam2`  
 호출의 두 번째 매개 변수입니다.  
  
 `dwParam3`  
 호출의 세 번째 매개 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md)
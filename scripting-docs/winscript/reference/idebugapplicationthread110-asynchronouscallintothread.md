---
title: IDebugApplicationThread110::AsynchronousCallIntoThread | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 06b3031a-4aec-4a47-afaa-04642a4c4870
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d4275d42ec102557cce12127f47a33a53c4dba6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationthread110asynchronouscallintothread"></a>IDebugApplicationThread110::AsynchronousCallIntoThread
주 스레드에서 비동기 호출을 만듭니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
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
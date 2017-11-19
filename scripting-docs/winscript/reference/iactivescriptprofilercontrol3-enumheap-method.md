---
title: "Iactivescriptprofilercontrol3:: Enumheap 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 2799d06d-20dd-4c12-9646-554c0ea3606e
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7d6fc79a9d6d35e35181c3505e07af2d9a1962c2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrol3enumheap-method"></a>IActiveScriptProfilerControl3::EnumHeap 메서드
인터페이스를 반환 ([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md))는 관련된 스크립트 엔진의 컨텍스트에서 GC 힙 개체에 대 한 반복 사용할 수 있는 합니다.  
  
 디버그 중 하나에서이 메서드를 호출 하거나 모드를 해제할 수 있습니다. UI 스레드 유휴 상태일 때이 메서드를 호출 해야 합니다. 메서드가 호출 된 후 없는 연산을 수행 하는 제외 하 고 스크립트 엔진에 대해 [iactivescriptprofilerheapenum:: Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md) 될 때까지 [iactivescriptprofilerheapenum:: Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)S_FALSE를 반환 또는 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md) 인터페이스 포인터를 해제 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumHeap([out] IActiveScriptProfilerHeapEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>매개 변수  
 ppEnum  
 [out] 반환 된 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT입니다.
---
title: "Iactivescriptprofilercontrol5:: Enumheap2 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a25859eb-ac28-4a97-bcb3-33788982a76b
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c493acdb2843877c506d9d84e145a79ac2d60d7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilercontrol5enumheap2-method"></a>IActiveScriptProfilerControl5::EnumHeap2 메서드
인터페이스를 반환 ([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md))는 관련된 스크립트 엔진의 컨텍스트에서 GC 힙 개체에 대 한 반복 사용할 수 있는 합니다.  
  
 디버그 중 하나에서이 메서드를 호출 하거나 모드를 해제할 수 있습니다. UI 스레드 유휴 상태일 때이 메서드를 호출 해야 합니다. 메서드가 호출 된 후 없는 연산을 수행 하는 제외 하 고 스크립트 엔진에 대해 [iactivescriptprofilerheapenum:: Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md) 될 때까지 [iactivescriptprofilerheapenum:: Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)S_FALSE를 반환 또는 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md) 인터페이스 포인터를 해제 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumHeap2(    [in] PROFILER_HEAP_ENUM_FLAGS enumFlags,    [out] IActiveScriptProfilerHeapEnum** ppEnum);  
```  
  
#### <a name="parameters"></a>매개 변수  
 enumFlags  
 개체 관계에서 가리키는 개체에 대 한 추가 정보 노출 되는지 여부를 지정 하는 값입니다. 추가 정보는 가리키는 개체가 인지 getter 또는 setter 메서드를 나타낼 수 있습니다. 자세한 내용은 참조 하십시오. [PROFILER_HEAP_ENUM_FLAGS 열거형](../../winscript/reference/profiler-heap-enum-flags-enumeration.md)합니다.  
  
 ppEnum  
 [out] 반환 된 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT를 반환 합니다. 다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|성공적으로 완료 힙 열거형입니다.|  
|`E_OUTOFMEMORY`|충분 한 메모리 힙 열거를 수행할 수 없습니다.|  
|`E_FAIL`|내부 오류가 발생 했습니다.|
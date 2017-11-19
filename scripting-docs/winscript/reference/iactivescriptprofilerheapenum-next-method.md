---
title: "Iactivescriptprofilerheapenum:: Next 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0336286f-1dcd-4df9-adf5-76b59b4e74bb
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3927743a1de1d3048537327aebd24a847a7d22e5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilerheapenumnext-method"></a>IActiveScriptProfilerHeapEnum::Next 메서드
힙 개체에서 집합의 개체 또는 개체를 가져옵니다는 [iactivescriptprofilercontrol3:: Enumheap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next (    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] PROFILER_HEAP_OBJECT** heapObjects,     [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `celt`  
 반환할 개체의 수입니다.  
  
 `heapObjects`  
 [out] 다음 [PROFILER_HEAP_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조입니다.  
  
 `pceltFetched`  
 [out] 반환 되는 개체 수  
  
## <a name="return-value"></a>반환 값  
 HRESULT입니다.
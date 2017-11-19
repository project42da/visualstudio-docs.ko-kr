---
title: IActiveScriptProfilerHeapEnum::GetNameIdMap | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 88514c93-850b-48d4-9a68-1e27d7411f0d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0761517236fbcc05655365d77ce2990e9d1c566
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilerheapenumgetnameidmap"></a>IActiveScriptProfilerHeapEnum::GetNameIdMap
에 해당 하는 문자열 이름을 반환 합니다. [PROFILER_HEAP_OBJECT_NAME_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md) 값입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNameIdMap (    [out, size_is(,*pcelt)] LPCWSTR* pNameList[],     [out] UINT *pcelt);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pNameList`  
 [out] 와 연결 된 이름의 배열 [PROFILER_HEAP_OBJECT_NAME_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md) 값입니다.  
  
 `pcelt`  
 [out] 배열에는 이름 수를 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 HRESULT입니다.
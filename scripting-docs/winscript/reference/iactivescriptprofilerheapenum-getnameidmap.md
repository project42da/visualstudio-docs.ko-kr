---
title: "IActiveScriptProfilerHeapEnum::GetNameIdMap | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 88514c93-850b-48d4-9a68-1e27d7411f0d
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IActiveScriptProfilerHeapEnum::GetNameIdMap
해당 문자열 이름을 반환 하는 [PROFILER\_HEAP\_OBJECT\_NAME\_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md) 값입니다.  
  
## 구문  
  
```  
HRESULT GetNameIdMap (  
    [out, size_is(,*pcelt)] LPCWSTR* pNameList[],   
    [out] UINT *pcelt);  
```  
  
#### 매개 변수  
 `pNameList`  
 \[out\] 관련 된 이름 배열을 [PROFILER\_HEAP\_OBJECT\_NAME\_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md) 값입니다.  
  
 `pcelt`  
 \[out\] 수 배열의 이름입니다.  
  
## 반환 값  
 HRESULT입니다.
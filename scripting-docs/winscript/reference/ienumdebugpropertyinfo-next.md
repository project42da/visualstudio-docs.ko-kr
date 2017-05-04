---
title: "IEnumDebugPropertyInfo::Next | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugPropertyInfo.Next
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IEnumDebugPropertyInfo::Next"
ms.assetid: 052837ac-1599-49cc-9a5a-ba90f992eeff
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugPropertyInfo::Next
지정 된 수의 검색 `DebugPropertyInfo` 는 열거 시퀀스에서 구조.  
  
## 구문  
  
```  
HRESULT Next (  
   ULONG celt,  
   DebugPropertyInfo*rgelt,  
   ULONG* pceltFetched  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 수가 `DebugPropertyInfo`구조를 검색 합니다.  
  
 `rgelt`  
 \[out\] 배열을 `DebugPropertyInfo` 구조를 검색 합니다.  
  
 `pceltFetched`  
 \[out\] 개수를 반환 합니다. `DebugPropertyInfo` 구조를 실제로 검색 합니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IEnumDebugPropertyInfo 인터페이스](../../winscript/reference/ienumdebugpropertyinfo-interface.md)   
 [DebugPropertyInfo 구조체](../../winscript/reference/debugpropertyinfo-structure.md)
---
title: "IEnumDebugExtendedPropertyInfo::Next | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugExtendedPropertyInfo.Next
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IEnumDebugExtendedPropertyInfo::Next"
ms.assetid: ac41c9a3-19d1-4596-8a87-01c10b131be3
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugExtendedPropertyInfo::Next
지정 된 수의 검색`ExtendedDebugPropertyInfo` 는 열거 시퀀스에서 구조.  
  
## 구문  
  
```  
HRESULT Next (  
   ULONG celt,  
   ExtendedDebugPropertyInfo *rgelt,  
   ULONG* pceltFetched  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 수가 `ExtendedDebugPropertyInfo`구조를 검색 합니다.  
  
 `rgelt`  
 \[out\] 배열을 `ExtendedDebugPropertyInfo` 구조를 검색 합니다.  
  
 `pceltFetched`  
 \[out\] 수 `ExtendedDebugPropertyInfo` 구조를 실제로 검색 합니다.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  
  
## 참고 항목  
 [IEnumDebugExtendedPropertyInfo 인터페이스](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)   
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)
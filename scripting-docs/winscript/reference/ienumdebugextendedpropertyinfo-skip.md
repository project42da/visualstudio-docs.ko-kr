---
title: "IEnumDebugExtendedPropertyInfo::Skip | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugExtendedPropertyInfo.Skip
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IEnumDebugExtendedPropertyInfo::Skip"
ms.assetid: a0b4a9fc-e122-482b-9384-b83c460b61fe
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugExtendedPropertyInfo::Skip
지정 된 개수의 생략 `ExtendedDebugPropertyInfo` 는 열거 시퀀스에서 구조.  
  
## 구문  
  
```  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 수 `ExtendedDebugPropertyInfo` 구조를 건너뛰려면 열거 시퀀스에서.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  반환 `S_FALSE` 경우 열거형의 끝에는 현재 요소 포인터를 설정 하 고 `celt` 열거자의 왼쪽 요소 수보다 큽니다.  
  
## 참고 항목  
 [IEnumDebugExtendedPropertyInfo 인터페이스](../../winscript/reference/ienumdebugextendedpropertyinfo-interface.md)   
 [ExtendedDebugPropertyInfo 구조체](../../winscript/reference/extendeddebugpropertyinfo-structure.md)
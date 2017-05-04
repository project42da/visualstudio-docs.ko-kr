---
title: "IEnumDebugPropertyInfo::Skip | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugPropertyInfo.Skip
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IEnumDebugPropertyInfo::Skip"
ms.assetid: 2f6361fb-d66d-4fc0-8fe0-c859593a183f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugPropertyInfo::Skip
지정 된 개수의 생략 `DebugPropertyInfo` 는 열거 시퀀스에서 구조.  
  
## 구문  
  
```  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 수 `DebugPropertyInfo` 구조를 건너뛰려면 열거 시퀀스에서.  
  
## 반환 값  
 유효한 반환 `HRESULT`, 일반적으로 `S_OK`.  반환 `S_FALSE` 경우 열거형의 끝에는 현재 요소 포인터를 설정 하 고 `celt` 열거자의 왼쪽 요소 수보다 큽니다.  
  
## 참고 항목  
 [IEnumDebugPropertyInfo 인터페이스](../../winscript/reference/ienumdebugpropertyinfo-interface.md)   
 [DebugPropertyInfo 구조체](../../winscript/reference/debugpropertyinfo-structure.md)
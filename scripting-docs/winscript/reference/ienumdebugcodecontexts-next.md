---
title: "IEnumDebugCodeContexts::Next | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugCodeContexts.Next
apilocation: jscript.dll
helpviewer_keywords: 
  - "IEnumDebugCodeContexts::Next"
ms.assetid: 844cc353-ae0b-45e1-84a6-32b0bb67f57f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugCodeContexts::Next
열거형 시퀀스에서 지정된 수의 세그먼트를 검색합니다.  
  
## 구문  
  
```  
HRESULT Next(  
   ULONG                celt,  
   IDebugCodeContext**  pscc,  
   ULONG*               pceltFetched  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 검색 하는 세그먼트의 수입니다.  
  
 `pscc`  
 \[out\] 배열을 반환 합니다. `IDebugCodeContext` 인터페이스를 검색 하는 세그먼트를 나타냅니다.  
  
 `pceltFetched`  
 \[out\] 실제 수 열거자에서 반입 되는 세그먼트입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 세그먼트 열거 시퀀스에서 지정한 개수의 검색합니다.  
  
## 참고 항목  
 [IEnumDebugCodeContexts 인터페이스](../../winscript/reference/ienumdebugcodecontexts-interface.md)
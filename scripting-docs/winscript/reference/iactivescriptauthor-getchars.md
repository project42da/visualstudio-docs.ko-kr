---
title: "IActiveScriptAuthor::GetChars | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.GetChars
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::GetChars"
ms.assetid: a73ba263-12f7-4d5f-b4c8-9ad7e2d5d3cb
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# IActiveScriptAuthor::GetChars
완성을 요청 된 컨텍스트에 대해 완료 문자 집합을 반환합니다.  
  
## 구문  
  
```  
HRESULT GetChars(  
   DWORD            fRequestedList,  
   BSTR             *pbstrChars  
);  
```  
  
#### 매개 변수  
 `fRequestedList`  
 \[in\] 요청한 완료 컨텍스트입니다.  
  
|상수|값|설명|  
|--------|-------|--------|  
|SCRIPT\_CMPL\_ENUM\_TRIGGER|0x0001|왼쪽 열거를 요청합니다.|  
|SCRIPT\_CMPL\_MEMBER\_TRIGGER|0x0002|구성원 완료 컨텍스트를 요청합니다.|  
|SCRIPT\_CMPL\_PARAM\_TRIGGER|0x0003|매개 변수 목록을 요청합니다.|  
|SCRIPT\_CMPL\_COMMIT|0x0004|요청 완료 매개 변수 목록입니다.|  
  
 `pbstrChars`  
 \[out\] 요청한 완료 컨텍스트에 해당 하는 문자입니다.  
  
|`fRequestedList` 매개 변수|반환 되는 문자|  
|----------------------------|--------------|  
|SCRIPT\_CMPL\_ENUM\_TRIGGER|"."|  
|SCRIPT\_CMPL\_MEMBER\_TRIGGER|"\="|  
|SCRIPT\_CMPL\_PARAM\_TRIGGER|"\(,"|  
|SCRIPT\_CMPL\_COMMIT|"\(\)"|  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)
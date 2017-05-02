---
title: "IScriptEntry::GetBody | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.GetBody
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::GetBody"
ms.assetid: 419c8c11-a1f8-4b97-ab00-e8af2b2f9bfc
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IScriptEntry::GetBody
본문에 해당 하는 텍스트를 반환 된 `IScriptEntry` 스크립트 블록, 함수 블록 또는 스크립트릿.  
  
## 구문  
  
```  
HRESULT GetBody(  
   BSTR               *pbstr  
);  
```  
  
#### 매개 변수  
 `pbstr`  
 \[out\] 다음 중 하나의 본문에 있는 텍스트:  
  
-   `IScriptEntry` 스크립트 블록  
  
-   `IScriptEntry` 함수에서 함수 블록  
  
-   `IScriptEntry` 스크립트릿 이벤트 처리기  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)
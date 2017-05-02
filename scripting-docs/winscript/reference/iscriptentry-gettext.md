---
title: "IScriptEntry::GetText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.GetText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::GetText"
ms.assetid: 105b8244-1972-4b39-ac18-965f1f345ef2
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IScriptEntry::GetText
해당 텍스트를 반환의 `IScriptEntry` 에 포함 된 소스 코드 또는 스크립트 블록은 `IScriptScriptlet` 이벤트 처리기.  
  
## 구문  
  
```  
HRESULT GetText(  
   BSTR               *pbstr  
);  
```  
  
#### 매개 변수  
 `pbstr`  
 \[out\] 텍스트에는 `IScriptEntry` 에 포함 된 소스 코드 또는 스크립트 블록을 `IScriptScriptlet` 이벤트 처리기.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)
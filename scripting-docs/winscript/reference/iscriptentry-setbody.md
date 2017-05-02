---
title: "IScriptEntry::SetBody | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IScriptEntry.SetBody
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IScriptEntry::SetBody"
ms.assetid: 719062e4-98e4-4a7b-946d-6e5dbbcc5225
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# IScriptEntry::SetBody
본문에 있는 텍스트를 설정 하는 `IScriptEntry` 스크립트 블록 또는 `IScriptScriptlet` 스크립트릿.  
  
## 구문  
  
```  
HRESULT SetBody(  
   LPCOLESTR          psz  
);  
```  
  
#### 매개 변수  
 `psz`  
 \[in\] 에 `IScriptEntry` 스크립트 블록 `psz` 는 스크립트 태그 안에 있는 텍스트입니다.  
  
 에 `IScriptEntry` 함수 블록 `psz` 함수 본문입니다.  
  
 에 `IScriptScriptlet` 개체 \(파생 되는에서 `IScriptEntry`\), `psz` 는 스크립트릿 스크립트 텍스트입니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)   
 [IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)
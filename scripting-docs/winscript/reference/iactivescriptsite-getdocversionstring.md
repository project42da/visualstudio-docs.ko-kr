---
title: "IActiveScriptSite::GetDocVersionString | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.GetDocVersionString
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_GetDocVersionString"
ms.assetid: ab3f892d-06d3-4cb5-9ea5-20c4a1e518cd
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite::GetDocVersionString
현재 문서 버전을 고유 하 게 식별 하는 호스트 정의 문자열을 검색 합니다.  스크립팅 엔진 관련된 문서 변경 Windows 스크립트 \(예: 메모장에서 편집 중인 HTML 페이지의 경우\)의 범위를 벗어나는 경우이 스크립트를 로드할 때의 재컴파일 강제로 유지 된 상태로 함께 저장할 수 있습니다.  
  
## 구문  
  
```  
HRESULT GetDocVersionString(  
    BSTR *pbstrVersionString  // address of document version string  
);  
```  
  
#### 매개 변수  
 `pstrVersionString`  
 \[out\] 문서 호스트 정의 버전 문자열의 주소입니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_NOTIMPL` 이 메서드가 지원 되지 않는 경우.  
  
## 설명  
 경우 `E_NOTIMPL` 반환 합니다 스크립팅 엔진이 가정 스크립트 문서와 동기화 됩니다.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
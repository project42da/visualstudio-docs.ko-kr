---
title: "IActiveScriptAuthor::AddScriptlet | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.AddScriptlet
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::AddScriptlet"
ms.assetid: 879a6651-f187-4934-b130-c1247549900b
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IActiveScriptAuthor::AddScriptlet
코드 스크립트릿 루트 수준 자식으로 추가 `IScriptNode` 개체입니다.  호스트에만 두 수준이 스크립트릿의 정규화 된 이름을 수 있습니다.  
  
## 구문  
  
```  
HRESULT AddScriptlet(  
   LPCOLESTR pszDefaultName,  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszSubItemName,  
   LPCOLESTR pszEventName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### 매개 변수  
 `pszDefaultName`  
 \[in\] 주소 스크립트릿으로 연결할 기본 이름입니다.  
  
 `pszCode`  
 \[in\] 주소 스크립트릿 텍스트입니다.  
  
 `pszItemName`  
 \[in\] 버퍼 주소 호스트에서 이름 정규화 스크립트릿 최상위 식별자입니다.  
  
 `pszSubItemName`  
 \[in\] 버퍼 주소 호스트에서 이름 정규화 스크립트릿의 두 번째 수준 식별자입니다.  이름에 하나의 수준이 있는 경우 NULL로 설정 합니다.  
  
 `pszEventName`  
 \[in\] 스크립트릿의 이벤트 처리기는 이벤트 이름이 들어 있는 버퍼의 주소입니다.  
  
 `pszDelimiter`  
 \[in\] 주소 끝의 스크립트 블록 구분 기호입니다.  때 `pszCode` 구문 분석 텍스트 스트림에서 호스트 일반적으로 구분 \(예: 두 개의 작은따옴표\)를 스크립트 블록의 끝을 검색 합니다.  스크립트 블록의 끝 구분 기호를 표시 하지 않을 경우이 매개 변수는 NULL로 설정 합니다.  
  
 `dwCookie`  
 \[in\] 스크립트릿의 호스트 개체에 연결 하는 데 사용 되는 응용 프로그램 정의 값입니다.  
  
 `dwFlags`  
 \[in\] 사용되지 않습니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)
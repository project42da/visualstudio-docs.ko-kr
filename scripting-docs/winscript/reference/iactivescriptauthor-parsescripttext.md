---
title: "IActiveScriptAuthor::ParseScriptText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthor.ParseScriptText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthor::ParseScriptText"
ms.assetid: ebe212e8-6789-423d-ad22-92be984dc7ad
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# IActiveScriptAuthor::ParseScriptText
스크립트 텍스트를 구문 분석 하 고 스크립트 엔진을 제작 하는 텍스트를 추가 생성 된 `IScriptEntry` 스크립트 블록에 해당 하는 개체.  
  
## 구문  
  
```  
HRESULT ParseScriptText(  
   LPCOLESTR pszCode,  
   LPCOLESTR pszItemName,  
   LPCOLESTR pszDelimiter,  
   DWORD dwCookie,  
   DWORD dwFlags  
);  
```  
  
#### 매개 변수  
 `pszCode`  
 \[in\] 스크립트 구문 분석할 텍스트입니다.  
  
 `pszItemName`  
 \[in\] 스크립트 블록에 연결 된 항목 이름을 포함 하는 버퍼 주소입니다.  
  
 `pszDelimiter`  
 \[in\] 주소 끝의 스크립트 블록 구분 기호입니다.  때 `pszCode` 구문 분석 텍스트 스트림에서 호스트 일반적으로 구분 \(예: 두 개의 작은따옴표\)를 스크립트 블록의 끝을 검색 합니다.  경우 스크립트 블록의 끝을 나타내려면 구분 기호 없음이 매개 변수를 NULL로 설정 합니다.  
  
 `dwCookie`  
 \[in\] 새 연결 된 응용 프로그램 정의 값 `IScriptEntry` 개체입니다.  
  
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
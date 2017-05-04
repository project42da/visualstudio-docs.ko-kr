---
title: "IActiveScriptAuthorProcedure::ParseProcedureText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptAuthorProcedure.ParseProcedureText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptAuthorProcedure::ParseProcedureText"
ms.assetid: cb6c29c5-c749-48d7-a6a8-ccbf0f9119ec
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# IActiveScriptAuthorProcedure::ParseProcedureText
프로시저 코드를 구문 분석 하 고 스크립트 엔진을 제작 하는 코드를 프로시저의 텍스트를 추가 생성 된 `IScriptEntry` 코드 프로시저에 해당 하는 개체.  
  
## 구문  
  
```  
HRESULT ParseProcedureText(  
   LPCOLESTR   pszCode,  
   LPCOLESTR   pszFormalParams,  
   LPCOLESTR   pszProcedureName,  
   LPCOLESTR   pszItemName,  
   LPCOLESTR   pszDelimiter,  
   DWORD       dwCookie,  
   DWORD       dwFlags,  
   IDispatch   *pdispFor  
);  
```  
  
#### 매개 변수  
 `pszCode`  
 \[in\] 스크립트 구문 분석할 텍스트입니다.  
  
 `pszFormalParams`  
 \[in\] 형식 매개 변수 이름 프로시저의 주소입니다.  스크립트 엔진 제작에 대 한 적절 한 구분 기호 매개 변수 이름은 구분 해야 합니다.  이름이 괄호 안에 묶여 있으면 안 됩니다.  
  
 `pszProcedureName`  
 \[in\] 주소 구문 분석할 프로시저 이름입니다.  
  
 `pszItemName`  
 \[in\] 관련 된 항목 이름을 포함 하는 버퍼 주소는 `IScriptEntry` 개체입니다.  
  
 `pszDelimiter`  
 \[in\] 주소 끝의 스크립트 블록 구분 기호입니다.  때 `pszCode` 구문 분석 텍스트 스트림에서 호스트 일반적으로 구분 \(예: 두 개의 작은따옴표\)를 스크립트 블록의 끝을 검색 합니다.  스크립트 블록의 끝을 표시 하려면 구분 기호 없음 경우이 매개 변수를 NULL로 설정.  
  
 `dwCookie`  
 \[in\] 새 연결 된 응용 프로그램 정의 값 `IScriptEntry` 개체입니다.  
  
 `dwFlags`  
 \[in\] 사용되지 않습니다.  
  
 `pdispFor`  
 \[in\] 사용되지 않습니다.  
  
## 반환 값  
 `HRESULT`입니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 현재 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 엔진이이 메서드를 구현 하지 않습니다.  
  
## 참고 항목  
 [IActiveScriptAuthorProcedure 인터페이스](../../winscript/reference/iactivescriptauthorprocedure-interface.md)
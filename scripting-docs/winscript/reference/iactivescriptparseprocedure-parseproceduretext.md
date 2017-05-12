---
title: "IActiveScriptParseProcedure::ParseProcedureText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptParseProcedure.ParseProcedureText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptParseProcedure_ParseProcedureText"
ms.assetid: 345a74ae-b4e8-42b2-abd8-633a370e8e7f
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptParseProcedure::ParseProcedureText
지정 된 코드 프로시저를 구문 분석 하 고 프로시저 이름 공간에 추가 합니다.  
  
## 구문  
  
```  
HRESULT ParseProcedureText(  
    LPCOLESTR pstrCode,              // address of procedure text  
    LPCOLESTR pstrFormalParams,      // address of formal parameter names  
    LPCOLESTR pstrProcedureName,     // address of procedure name  
    LPCOLESTR pstrItemName,          // address of item name  
    IUnknown *punkContext,           // address of debugging context  
    LPCOLESTR pstrDelimiter,         // address of end-of-procedure delimiter  
    DWORD_PTR dwSourceContextCookie, // application-defined value for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // procedure flags  
    IDispatch **ppdisp               // receives IDispatch pointer  
);  
```  
  
#### 매개 변수  
 `pstrCode`  
 \[in\] 평가 절차 텍스트의 주소입니다.  이 문자열을 해석 하기 위해서 스크립트 언어에 따라 달라 집니다.  
  
 `pstrFormalParams`  
 \[in\] 주소 형식 매개 변수 이름 프로시저입니다.  스크립팅 엔진에 대 한 적절 한 구분 기호를 매개 변수 이름은 구분 해야 합니다.  이름은 괄호로 묶어야 합니다 없습니다.  
  
 `pstrProcedureName`  
 \[in\] 주소 구문 분석 하는 프로시저 이름입니다.  
  
 `pstrItemName`  
 \[in\] 주소 항목 이름의 프로시저 평가 컨텍스트를 제공 합니다.  이 매개 변수가 `NULL`, 코드의 스크립팅 엔진이 전역 컨텍스트에서 계산 됩니다.  
  
 `punkContext`  
 \[in\] 컨텍스트 개체의 주소입니다.  이 개체는 이러한 컨텍스트는 현재 실행 컨텍스트를 나타내는 디버거에서 제공 될 수 있습니다 디버깅 환경에서 사용 하기 위해 예약 되어 있습니다.  이 매개 변수가 `NULL`, 엔진을 사용 하 여 `pstrItemName` 컨텍스트를 식별 합니다.  
  
 `pstrDelimiter`  
 \[in\] 프로시저의 끝 구분 기호 주소입니다.  때 `pstrCode` 구문 분석 절차의 끝을 검색 합니다 \('\) 작은따옴표 2 개 같은 텍스트 스트림에서 호스트 일반적으로 구분 기호를 사용 합니다.  호스트 허용 일부 조건부 기본 전처리를 제공 하는 스크립팅 엔진 사용 구분이 매개이 변수를 지정 \(예를 들어, 작은 따옴표 \['\]에 두 개의 작은따옴표를 구분 기호로 사용 대체\).  정확 하 게 하는 방법 \(및 if\)는 스크립팅 엔진에서는 스크립팅 엔진에서이 정보를 사용에 따라 다릅니다.  이 매개 변수를 설정 `NULL` 호스트 프로시저의 끝을 표시 하는 구분 기호로 사용 하지 않은 경우.  
  
 `dwSourceContextCookie`  
 \[in\] 디버깅 목적으로 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ulStartingLineNumber`  
 \[in\] 구문 분석에서 시작 되는 줄부터 값입니다.  
  
 `dwFlags`  
 \[in\] 프로시저에 관련 된 플래그입니다.  이러한 값의 조합을 사용할 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|SCRIPTPROC\_ISEXPRESSION|코드에서 `pstrCode` 프로시저의 반환 값을 나타내는 식입니다.  기본적으로, 식, 문, 목록 또는 프로시저에서 스크립트 언어에 의해 허용 되는 다른 모든 코드를 포함할 수 있습니다.|  
|SCRIPTPROC\_IMPLICIT\_THIS|`this` 포인터를 프로시저의 범위에 포함 됩니다.|  
|SCRIPTPROC\_IMPLICIT\_PARENTS|상위의 `this` 포인터를 프로시저의 범위에 포함 됩니다.|  
  
 `ppdisp`  
 \[out\] 스크립트의 전역 메서드 및 속성을 포함 하는 개체에 대 한 포인터의 주소입니다.  이러한 개체를 스크립팅 엔진을 지원 하지 않는 경우 `NULL` 이 반환 됩니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다.  프로시저 이름 공간에 추가 런타임 스크립트를 지원 하지 않습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 초기화 되지 않았거나 닫힌 상태에서 스크립트 엔진입니다\).|  
|`OLESCRIPT_E_SYNTAX`|알 수 없는 구문 오류가 프로시저에서 발생 합니다.|  
|`S_FALSE`|스크립팅 엔진이 디스패치 개체를 지원 하지 않습니다. `ppdisp` 매개 변수가 설정 되어 `NULL`.|  
  
## 설명  
 스크립트 코드가이 호출 하는 동안 계산 됩니다. 대신 프로시저 위치는 스크립트에 의해 나중에 호출할 수 있습니다 스크립트 상태로 컴파일됩니다.  
  
## 참고 항목  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)
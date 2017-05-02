---
title: "IActiveScriptParseProcedureOld::ParseProcedureText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptParseProcedureOld.ParseProcedureText
apilocation: jscript.dll
helpviewer_keywords: 
  - "IActiveScriptParseProcedureOld::ParseProcedureText"
ms.assetid: 21a21313-35ce-432d-b9a6-7999065f19ac
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptParseProcedureOld::ParseProcedureText
주어진된 코드 프로시저를 구문 분석 하 고는 익명 프로시저 이름 공간에 추가 합니다.  
  
## 구문  
  
```  
HRESULT ParseProcedureText(  
   LPCOLESTR    pstrCode,  
   LPCOLESTR    pstrFormalParams,  
   LPCOLESTR    pstrItemName,  
   IUnknown*    punkContext,  
   LPCOLESTR    pstrDelimiter,  
   DWORD_PTR    dwSourceContextCookie,  
   ULONG        ulStartingLineNumber,  
   DWORD        dwFlags,  
   IDispatch**  ppdisp  
);  
```  
  
#### 매개 변수  
 `pstrCode`  
 \[in\] 평가 절차 텍스트입니다.  이 문자열을 해석 하기 위해서 스크립트 언어에 따라 달라 집니다.  
  
 `pstrFormalParams`  
 \[in\] 프로시저의 형식 매개 변수 이름입니다.  스크립팅 엔진에 대 한 적절 한 구분 기호를 매개 변수 이름은 구분 해야 합니다.  이름은 괄호로 묶어야 합니다 없습니다.  
  
 `pstrItemName`  
 \[in\] 절차 평가 컨텍스트를 제공 하는 명명 된 항목의 이름입니다.  이 매개 변수가 `NULL`, 코드의 스크립팅 엔진이 전역 컨텍스트에서 계산 됩니다.  
  
 `punkContext`  
 \[in\] 컨텍스트 개체입니다.  이 개체는 이러한 컨텍스트는 현재 실행 컨텍스트를 나타내는 디버거에서 제공 될 수 있습니다 디버깅 환경에서 사용 하기 위해 예약 되어 있습니다.  이 매개 변수가 `NULL`, 엔진을 사용 하 여 `pstrItemName` 컨텍스트를 식별 합니다.  
  
 `pstrDelimiter`  
 \[in\] 프로시저의 끝 구분 기호입니다.  때 `pstrCode` 구문 분석 절차의 끝을 검색 합니다 \('\) 작은따옴표 2 개 같은 텍스트 스트림에서 호스트 일반적으로 구분 기호를 사용 합니다.  이 매개 변수는 호스트 스크립팅 엔진 일부 조건부를 제공할 수 있도록 사용 되는 구분 기호 지정 기본 전처리 \(예를 들어, 두 개의 작은따옴표를 구분 기호로 사용에 작은 따옴표 \['\]로 대체\).  정확 하 게 하는 방법 \(및 if\) 스크립팅 엔진 사용 스크립팅 엔진에서이 정보에 따라 다릅니다.  이 매개 변수를 설정 `NULL` 호스트 프로시저의 끝을 표시 하는 구분 기호로 사용 하지 않은 경우.  
  
 `dwSourceContextCookie`  
 \[in\] 디버깅 목적으로 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ulStartingLineNumber`  
 \[in\] 줄에는 구문 분석을 시작할 0부터 시작 값입니다.  
  
 `dwFlags`  
 \[in\] 프로시저에 관련 된 플래그입니다.  이러한 값의 조합을 사용할 수 있습니다.  
  
|상수|값|의미|  
|--------|-------|--------|  
|SCRIPTPROC\_ISEXPRESSION|0x00000020|코드에서 `pstrCode` 프로시저의 반환 값을 나타내는 식입니다.|  
|SCRIPTPROC\_IMPLICIT\_THIS|0x00000100|`this` 포인터를 프로시저의 범위에 포함 됩니다.|  
|SCRIPTPROC\_IMPLICIT\_PARENTS|0x00000200|상위의 `this` 포인터를 프로시저의 범위에 포함 됩니다.|  
  
 `ppdisp`  
 \[out\] 기본 메서드이며이 메서드에 의해 구문 분석 절차 디스패치 래퍼를 반환 합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다.  프로시저 이름 공간에 추가 런타임 스크립트를 지원 하지 않습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 초기화 되지 않았거나 닫힌 상태에서 스크립트 엔진입니다\).|  
|`OLESCRIPT_E_SYNTAX`|알 수 없는 구문 오류가 프로시저에서 발생 합니다.|  
|`S_FALSE`|스크립팅 엔진이 디스패치 개체를 지원 하지 않습니다. the `ppdisp`parameter is set to `NULL`.|  
  
## 설명  
 스크립트 코드가이 호출 하는 동안 계산 됩니다. 대신 프로시저를 메서드로에 컴파일됩니다 `ppdisp` 위치는 호출 스크립트에서 나중에.  
  
 이 인터페이스의 기준으로 사용 되지 않습니다의 `IActiveScriptParseProcedure` 인터페이스.  `IActiveScriptParseProcedure::ParseProcedureText` 메서드는이 메서드와 하지만 프로시저 이름을 지정할 수 있습니다.  모든 상황에서 `IActiveScriptParseProcedure::ParseProcedureText` 사용 해야 합니다.  
  
## 참고 항목  
 [IActiveScriptParseProcedureOld 인터페이스](../../winscript/reference/iactivescriptparseprocedureold-interface.md)   
 [IActiveScriptParseProcedure::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure-parseproceduretext.md)
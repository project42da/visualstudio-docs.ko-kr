---
title: IActiveScriptParseProcedure::ParseProcedureText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptParseProcedure.ParseProcedureText
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptParseProcedure_ParseProcedureText
ms.assetid: 345a74ae-b4e8-42b2-abd8-633a370e8e7f
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c2a877f6ebc692f9f54d69597e06db501f642802
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparseprocedureparseproceduretext"></a>IActiveScriptParseProcedure::ParseProcedureText
지정 된 코드 프로시저를 구문 분석 하 고 네임 스페이스에는 프로시저를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `pstrCode`  
 [in] 평가 하 여 프로시저 텍스트의 주소입니다. 이 문자열의 해석 스크립트 언어에 따라 달라 집니다.  
  
 `pstrFormalParams`  
 [in] 프로시저에 대 한 형식 매개 변수 이름의 주소입니다. 매개 변수 이름은 스크립팅 엔진에 대 한 적절 한 구분 기호 구분 되어야 합니다. 이름은 괄호로 묶지 말아야 합니다.  
  
 `pstrProcedureName`  
 [in] 프로시저 이름 구문 분석할 수의 주소입니다.  
  
 `pstrItemName`  
 [in] 프로시저를 평가할의 컨텍스트를 제공 하는 항목 이름의 주소입니다. 이 매개 변수가 `NULL`, 스크립팅 엔진의 전역 컨텍스트에서 코드를 계산 합니다.  
  
 `punkContext`  
 [in] 컨텍스트 개체의 주소입니다. 이 개체를 활성는 런타임에 컨텍스트를 나타내는 디버거를 통해 이러한 컨텍스트를 제공 하는 위치는 디버깅 환경에서 사용 하기 위해 예약 되어 있습니다. 이 매개 변수가 `NULL`, 엔진에서 사용 하 여 `pstrItemName` 컨텍스트를 식별 하 합니다.  
  
 `pstrDelimiter`  
 [in] 주소 프로시저 끝 구분 기호입니다. 때 `pstrCode` 구문 분석 되 텍스트의 스트림에서 호스트 일반적으로 사용 하 여 구분 기호, 예: 두 개의 작은 따옴표 ("), 프로시저의 끝을 검색 합니다. 이 매개 변수 지정 호스트 사용 조건부 몇 가지 기본 전처리를 제공 하는 스크립팅 엔진 수 있도록 하는 구분 기호 (예를 들어 작은따옴표로 구분 기호로 사용 하기 위해 두 개의 작은따옴표 ['] 교체) 됩니다. 방식을 정확 하 게 (및 if) 스크립팅 엔진 사용 하면이 정보의 사용 스크립팅 엔진에 따라 달라 집니다. 이 매개 변수를 설정 `NULL` 호스트 프로시저의 끝을 표시 하는 구분 기호를 사용 하지 않은 경우.  
  
 `dwSourceContextCookie`  
 [in] 디버깅 목적으로 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ulStartingLineNumber`  
 [in] 구문 분석은에서 시작 된 줄을 지정 하는 0부터 시작 값입니다.  
  
 `dwFlags`  
 [in] 프로시저에 연결 된 플래그입니다. 이러한 값의 조합 될 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTPROC_ISEXPRESSION|나타냅니다의 코드 `pstrCode` 식 프로시저의 반환 값을 나타내는입니다. 기본적으로 코드 식, 문, 목록 또는 다른 스크립트 언어에 따라 프로시저에서 허용 하는 아무 것도 포함 될 수 있습니다.|  
|SCRIPTPROC_IMPLICIT_THIS|나타냅니다는 `this` 포인터 프로시저의 범위에 포함 합니다.|  
|SCRIPTPROC_IMPLICIT_PARENTS|나타냅니다의 부모는 `this` 포인터 프로시저의 범위에 포함 됩니다.|  
  
 `ppdisp`  
 [out] 스크립트의 전역 메서드 및 속성을 포함 하는 개체에 대 한 포인터의 주소입니다. 스크립팅 엔진에서 이러한 개체를 지원 하지 않으면 `NULL` 반환 됩니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다. 스크립팅 엔진에서 네임 스페이스에는 프로시저의 실행 시간 추가 지원 하지 않습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진은 초기화 되지 않은 또는 닫힘 상태).|  
|`OLESCRIPT_E_SYNTAX`|절차에서 지정 되지 않은 구문 오류가 발생 했습니다.|  
|`S_FALSE`|스크립팅 엔진 디스패치 개체;를 지원 하지 않습니다. `ppdisp` 로 설정 된 `NULL`합니다.|  
  
## <a name="remarks"></a>설명  
 스크립트 코드가 없습니다;이 호출 중에 평가 됩니다. 대신, 절차는 위치를 호출할 수 있습니다 스크립트에서 나중에 스크립트 상태로 컴파일됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)
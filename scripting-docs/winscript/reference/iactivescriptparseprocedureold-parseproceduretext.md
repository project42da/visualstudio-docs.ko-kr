---
title: IActiveScriptParseProcedureOld::ParseProcedureText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptParseProcedureOld.ParseProcedureText
apilocation:
- jscript.dll
helpviewer_keywords:
- IActiveScriptParseProcedureOld::ParseProcedureText
ms.assetid: 21a21313-35ce-432d-b9a6-7999065f19ac
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cab546deb390535fa8ff71e116a0ad42d33cc104
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparseprocedureoldparseproceduretext"></a>IActiveScriptParseProcedureOld::ParseProcedureText
지정 된 코드 프로시저를 구문 분석 하 고 프로시저를 익명 네임 스페이스에 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `pstrCode`  
 [in] 프로시저의 텍스트는 계산입니다. 이 문자열의 해석 스크립트 언어에 따라 달라 집니다.  
  
 `pstrFormalParams`  
 [in] 프로시저에 대 한 형식 매개 변수 이름입니다. 매개 변수 이름은 스크립팅 엔진에 대 한 적절 한 구분 기호 구분 되어야 합니다. 이름은 괄호로 묶지 말아야 합니다.  
  
 `pstrItemName`  
 [in] 프로시저를 평가할의 컨텍스트를 제공 하는 명명 된 항목의 이름입니다. 이 매개 변수가 `NULL`, 스크립팅 엔진의 전역 컨텍스트에서 코드를 계산 합니다.  
  
 `punkContext`  
 [in] 컨텍스트 개체입니다. 이 개체를 활성는 런타임에 컨텍스트를 나타내는 디버거를 통해 이러한 컨텍스트를 제공 하는 위치는 디버깅 환경에서 사용 하기 위해 예약 되어 있습니다. 이 매개 변수가 `NULL`, 엔진에서 사용 하 여 `pstrItemName` 컨텍스트를 식별 하 합니다.  
  
 `pstrDelimiter`  
 [in] 프로시저 끝 구분 기호입니다. 때 `pstrCode` 구문 분석 되 텍스트의 스트림에서 호스트 일반적으로 사용 하 여 구분 기호, 예: 두 개의 작은 따옴표 ("), 프로시저의 끝을 검색 합니다. 이 매개 변수 지정 호스트 사용 일부 조건부를 제공 하는 스크립팅 엔진 수 있도록 하는 구분 기호 (예: 작은따옴표로 구분 기호로 사용 하기 위해 두 개의 작은따옴표 ['] 바꿉니다) 기본 전처리 합니다. 방식을 정확 하 게 (및 if)의 스크립팅 엔진이 사용 하는 스크립팅 엔진에이 정보에 따라 달라 집니다. 이 매개 변수를 설정 `NULL` 호스트 프로시저의 끝을 표시 하는 구분 기호를 사용 하지 않은 경우.  
  
 `dwSourceContextCookie`  
 [in] 디버깅 목적으로 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ulStartingLineNumber`  
 [in] 구문 분석 하는 줄을 지정 하는 0부터 시작 값이 시작 됩니다.  
  
 `dwFlags`  
 [in] 프로시저에 연결 된 플래그입니다. 이러한 값의 조합 수 있습니다.  
  
|상수|값|의미|  
|--------------|-----------|-------------|  
|SCRIPTPROC_ISEXPRESSION|0x00000020|나타냅니다의 코드 `pstrCode` 식 프로시저의 반환 값을 나타내는입니다.|  
|SCRIPTPROC_IMPLICIT_THIS|0x00000100|나타냅니다는 `this` 포인터 프로시저의 범위에 포함 합니다.|  
|SCRIPTPROC_IMPLICIT_PARENTS|0x00000200|나타냅니다의 부모는 `this` 포인터 프로시저의 범위에 포함 됩니다.|  
  
 `ppdisp`  
 [out] 기본 방법은이 방법으로 구문 분석 하는 절차는 디스패치 래퍼를 반환 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다. 스크립팅 엔진에서 네임 스페이스에는 프로시저의 실행 시간 추가 지원 하지 않습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진은 초기화 되지 않은 또는 닫힘 상태).|  
|`OLESCRIPT_E_SYNTAX`|절차에서 지정 되지 않은 구문 오류가 발생 했습니다.|  
|`S_FALSE`|스크립팅 엔진 디스패치 개체;를 지원 하지 않습니다. `ppdisp`로 설정 된 `NULL`합니다.|  
  
## <a name="remarks"></a>설명  
 스크립트 코드가 없습니다;이 호출 중에 평가 됩니다. 프로시저를 컴파일할 메서드로 대신, `ppdisp` 위치를 호출할 수 있습니다 스크립트에서 나중에 있습니다.  
  
 이 인터페이스는 기준 사용 되지 않습니다는 `IActiveScriptParseProcedure` 인터페이스입니다. `IActiveScriptParseProcedure::ParseProcedureText` 메서드는이 메서드에 없지만 프로시저 이름을 지정할 수 있습니다. 모든 상황에서 `IActiveScriptParseProcedure::ParseProcedureText` 사용 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptParseProcedureOld 인터페이스](../../winscript/reference/iactivescriptparseprocedureold-interface.md)   
 [IActiveScriptParseProcedure::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure-parseproceduretext.md)
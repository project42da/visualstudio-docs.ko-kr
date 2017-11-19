---
title: IActiveScriptParse::ParseScriptText | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptParse.ParseScriptText
apilocation: scrobj.dll
helpviewer_keywords: IActiveScriptParse_ParseScriptText
ms.assetid: 2d237d6c-cc65-415b-8808-72791304a136
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70d17807b47468f2238c0254cc39b339df616411
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparseparsescripttext"></a>IActiveScriptParse::ParseScriptText
네임 스페이스에 선언 추가 하 고 평가 하는 코드를 적절 하 게 지정 된 코드 스크립틀릿을 구문 분석 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ParseScriptText(  
    LPCOLESTR pstrCode,              // address of scriptlet text  
    LPCOLESTR pstrItemName,          // address of item name  
    IUnknown *punkContext,           // address of debugging context  
    LPCOLESTR pstrDelimiter,         // address of end-of-scriptlet delimiter  
    DWORD_PTR dwSourceContextCookie, // cookie for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // scriptlet flags  
    VARIANT *pvarResult,             // address of buffer for results  
    EXCEPINFO *pexcepinfo            // address of buffer for error data  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|`pstrCode`|[in] 평가할 스크립틀릿 텍스트의 주소입니다. 이 문자열의 해석 스크립트 언어에 따라 달라 집니다.|  
|`pstrItemName`|[in] 주소는 스크립틀릿 계산할 컨텍스트를 제공 하는 항목 이름입니다. 이 매개 변수가 NULL 인 경우 코드는 스크립팅 엔진의 전역 컨텍스트에서 평가 됩니다.|  
|`punkContext`|[in] 컨텍스트 개체의 주소입니다. 이 개체를 활성는 런타임에 컨텍스트를 나타내는 디버거를 통해 이러한 컨텍스트를 제공 하는 위치는 디버깅 환경에서 사용 하기 위해 예약 되어 있습니다. 엔진에서 사용 하 여이 매개 변수가 NULL 이면 `pstrItemName` 컨텍스트를 식별 하 합니다.|  
|`pstrDelimiter`|[in] 주소는 스크립틀릿 끝 구분 기호입니다. 때 `pstrCode` 구문 분석 되 텍스트의 스트림에서 호스트 일반적으로 사용 하 여 구분 기호, 예: 두 개의 작은 따옴표 (")는 스크립틀릿의 끝을 검색 합니다. 이 매개 변수 지정 호스트 사용 조건부 몇 가지 기본 전처리를 제공 하는 스크립팅 엔진 수 있도록 하는 구분 기호 (예를 들어 작은따옴표로 구분 기호로 사용 하기 위해 두 개의 작은따옴표 ['] 교체) 됩니다. 방식을 정확 하 게 (및 if) 스크립팅 엔진 사용 하면이 정보의 사용 스크립팅 엔진에 따라 달라 집니다. 이 매개 변수를 설정 `NULL` 호스트는 스크립틀릿의 끝을 표시 하는 구분 기호를 사용 하지 않은 경우.|  
|`dwSourceContextCookie`|[in] 디버깅 목적으로 사용 되는 쿠키입니다.|  
|`ulStartingLineNumber`|[in] 구문 분석은에서 시작 된 줄을 지정 하는 0부터 시작 값입니다.|  
|`dwFlags`|[in] 스크립틀릿와 관련 된 플래그입니다. 이러한 값의 조합 될 수 있습니다.|  
  
|값|의미|  
|-----------|-------------|  
|SCRIPTTEXT_ISEXPRESSION|계산 식과 문을 간의 차이 중요 하지만 구문상 모호한 스크립트 언어의 경우이 플래그는 문 또는 문 목록이 아니라 식으로 해석 해야 하는 스크립틀릿 임을 지정 합니다. 기본적으로 올바른 스크립틀릿 텍스트 구문에서 확인할 수 있는 경우가 아니면 문은 간주 됩니다.|  
|SCRIPTTEXT_ISPERSISTENT|스크립팅 엔진에 저장 된 경우이 호출 하는 동안 추가 된 코드를 저장 해야 할지 나타냅니다 (예를 들어 호출을 통해 `IPersist*::Save`), 또는 다시 초기화 된 상태로 전환을 통해 스크립팅 엔진을 다시 설정 합니다.|  
|SCRIPTTEXT_ISVISIBLE|스크립트 텍스트를 표시 해야 함을 나타냅니다 (그리고이 이름으로 호출할 수)는 스크립트의 네임 스페이스에서 전역 메서드로 합니다.|  
  
|||  
|-|-|  
|`pvarResult`|[out] 스크립틀릿 처리의 결과 받는 버퍼의 주소 또는 `NULL` 호출자 결과가 없습니다. 필요한 경우 (즉 SCRIPTTEXT_ISEXPRESSION 값은 설정 되지 않음).|  
|`pexcepinfo`|[out] 예외 정보를 수신 하는 구조체의 주소입니다. 이 구조 채워진 경우 `IActiveScriptParse::ParseScriptText` DISP_E_EXCEPTION를 반환 합니다.|  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`DISP_E_EXCEPTION`|처리는 스크립틀릿에 예외가 발생 했습니다. `pexcepinfo` 매개 변수는 예외에 대 한 정보를 포함 합니다.|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다. 스크립팅 엔진의 식 또는 문으로 런타임에 평가 지원 하지 않습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에는 초기화 되지 않은 또는 닫힘 상태로 또는 SCRIPTTEXT_ISEXPRESSION 플래그가 설정 된 있고 스크립팅 엔진 형식은 초기화 된 상태에서).|  
|`OLESCRIPT_E_SYNTAX`|스크립틀릿에 지정 되지 않은 구문 오류가 발생 했습니다.|  
  
## <a name="remarks"></a>설명  
 스크립팅 엔진에서 초기화 된 상태 이면이 호출 하는 동안 코드 없이 평가 실제로 됩니다. 이러한 코드 대기 되 고로 (또는 통해) 스크립팅 엔진 전환 될 때 실행 되는 대신, 시작 됨된 상태입니다. 실행에 초기화 된 상태에 허용 되지 않습니다 되므로 SCRIPTTEXT_ISEXPRESSION 플래그 초기화 된 상태에 있을 때 사용 하 여이 메서드를 호출 하면 오류가 발생 합니다.  
  
 스크립틀릿 식, 문, 목록 또는 스크립트 언어에서 허용 하는 아무 것도 될 수 있습니다. 예를 들어이 메서드는 평가 하는 데 html \<스크립트 > 태그를 HTML 페이지 생성 되 방금 스크립트 상태로 컴파일하는 대신 때 실행할 문을 허용 합니다.  
  
 이 메서드에 전달 된 코드는 유효 하 고 전체 코드의 일부 여야 합니다. 예를 들어 VBScript에는 다음와 함께 두 번째로 Sub Function(x)로 한 번이 메서드를 호출 하려면 `End Sub`합니다. 파서가는 서브루틴을 완료 하려면 두 번째 호출에 대 한 대기 하지 않아야 하지만 대신 해야 생성 구문 분석 오류 서브루틴 선언을 시작 되었지만 완료 되지 때문에.  
  
 스크립트 상태에 대 한 자세한 내용은의 스크립트 엔진 상태 섹션을 참조 하십시오. [Windows 스크립트 엔진](../../winscript/windows-script-engines.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)
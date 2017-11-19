---
title: IActiveScriptParse32::AddScriptlet | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fcf11eb2-8e71-4cca-afda-a91791c243ff
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 7b4ea62bf8afa4247fc7c4fdbea40c6b7c772661
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptparse32addscriptlet"></a>IActiveScriptParse32::AddScriptlet
스크립트에 코드 스크립틀릿을 추가 합니다. 스크립트의 영구 상태는 호스트 문서와 얽혀 호스트는 스크립트를 복원 하는 환경에서이 메서드는 통하지 않고는 `IPersist*` 인터페이스입니다. 기본 예제는 내부 이벤트에 연결 될 HTML 문서에 포함 된 코드의 스크립틀릿을 허용 하는 HTML 스크립팅 언어 (예를 들어, ONCLICK="button1.text='Exit'").  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT AddScriptlet(  
    LPCOLESTR pstrDefaultName,       // address of default name of scriptlet  
    LPCOLESTR pstrCode,              // address of scriptlet text  
    LPCOLESTR pstrItemName,          // address of item name  
    LPCOLESTR pstrSubItemName,       // address of subitem name  
    LPCOLESTR pstrEventName,         // address of event name  
    LPCOLESTR pstrDelimiter,         // address of end-of-scriptlet delimiter  
    DWORD_PTR dwSourceContextCookie, // application-defined value for debugging  
    ULONG ulStartingLineNumber,      // starting line of the script  
    DWORD dwFlags,                   // scriptlet flags  
    BSTR *pbstrName,                 // address of actual name of scriptlet  
    EXCEPINFO *pexcepinfo            // address of exception information  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstrDefaultName`  
 [in] 주소는 스크립틀릿와 연결할 기본 이름입니다. 스크립틀릿에 명명 정보 (예: 위의 ONCLICK 예제)이 없는 경우는 스크립틀릿을 식별 하이 이름은 사용 합니다. 이 매개 변수가 `NULL`, 스크립팅 엔진 필요한 경우 고유한 이름을 만듭니다.  
  
 `pstrCode`  
 [in] 추가할 스크립틀릿 텍스트의 주소입니다. 이 문자열의 해석 스크립트 언어에 따라 달라 집니다.  
  
 `pstrItemName`  
 [in] 이 스크립틀릿와 관련 된 항목 이름을 포함 하는 버퍼의 주소입니다. 이 매개 변수를 외에에서 `pstrSubItemName`는 스크립틀릿 이벤트 처리기 개체를 식별 합니다.  
  
 `pstrSubItemName`  
 [in] 이름을 포함 하는 버퍼의 주소는 `subobject` 이 스크립틀릿 연결 되어 있는;이 이름은 명명 된 항목의 형식 정보에서 발견 되어야 하는 명명 된 항목의 합니다. 스크립틀릿 대신 명명 된 항목에 연결 해야 하면이 매개 변수는 NULL는 `subitem`합니다. 이 매개 변수를 외에에서 `pstrItemName`는 스크립틀릿은 이벤트 처리기는 특정 개체를 식별 합니다.  
  
 `pstrEventName`  
 [in] 이 이벤트는 스크립틀릿은 이벤트 처리기의 이름을 포함 하는 버퍼의 주소입니다.  
  
 `pstrDelimiter`  
 [in] 주소는 스크립틀릿 끝 구분 기호입니다. 경우는 `pstrCode` 매개 변수는 텍스트의 스트림에서 구문 분석, 호스트는 일반적으로 구분 기호를 사용 예: 두 개의 작은 따옴표 (")는 스크립틀릿의 끝을 검색 합니다. 이 매개 변수 지정 호스트 사용 조건부 몇 가지 기본 전처리를 제공 하는 스크립팅 엔진 수 있도록 하는 구분 기호 (예를 들어 작은따옴표로 구분 기호로 사용 하기 위해 두 개의 작은따옴표 ['] 교체) 됩니다. 방식을 정확 하 게 (및 if) 스크립팅 엔진 사용 하면이 정보의 사용 스크립팅 엔진에 따라 달라 집니다. 호스트는 스크립틀릿의 끝을 표시 하는 구분 기호를 사용 하지 않은 경우이 매개 변수를 NULL로 설정 합니다.  
  
 `dwSourceContextCookie`  
 [in] 디버깅 목적으로 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ulStartingLineNumber`  
 [in] 구문 분석은에서 시작 된 줄을 지정 하는 0부터 시작 값입니다.  
  
 `dwFlags`  
 [in] 스크립틀릿와 관련 된 플래그입니다. 다음 값의 조합 될 수 있습니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|SCRIPTTEXT_ISVISIBLE|스크립트 텍스트를 표시 해야 함을 나타냅니다 (그리고이 이름으로 호출할 수)는 스크립트의 네임 스페이스에서 전역 메서드로 합니다.|  
|SCRIPTTEXT_ISPERSISTENT|스크립팅 엔진에 저장 된 경우이 호출 하는 동안 추가 된 코드를 저장 해야 할지 나타냅니다 (예를 들어 호출을 통해 `IPersist*::Save`), 또는 다시 초기화 된 상태로 전환을 통해 스크립팅 엔진을 다시 설정 합니다. 이 상태에 대 한 자세한 내용은 스크립트 엔진 상태를 참조 하십시오.|  
  
 `pbstrName` ,  
 [out] 스크립틀릿을 식별 하는 데는 실제 이름입니다. 이 기본 설정 순서에 포함 되도록: 이름이 스크립틀릿 텍스트에 명시적으로 지정에 제공 된 기본 이름을 `pstrDefaultName`, 또는 합성 스크립팅 엔진에서 고유한 이름입니다.  
  
 `pexcepinfo` ,  
 [out] 예외 정보를 포함 하는 구조체의 주소입니다. DISP_E_EXCEPTION 반환 되 면이 구조 채워야 합니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`DISP_E_EXCEPTION`|스크립틀릿을 구문 분석에서 예외가 발생 했습니다. `pexcepinfo` 매개 변수는 예외에 대 한 정보를 포함 합니다.|  
|`E_INVALIDARG`|인수가 올바르지 않습니다.|  
|`E_NOTIMPL`|이 메서드가 지원 되지 않습니다. 스크립팅 엔진 이벤트 싱크 스크립틀릿을 추가 하는 것을 지원 하지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화) 및 않아 실패 했습니다.|  
|`OLESCRIPT_E_INVALIDNAME`|제공 된 기본 이름에 스크립팅 언어로 올바르지 않습니다.|  
|`OLESCRIPT_E_SYNTAX`|스크립틀릿에 지정 되지 않은 구문 오류가 발생 했습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptParse32](../../winscript/reference/iactivescriptparse32.md)
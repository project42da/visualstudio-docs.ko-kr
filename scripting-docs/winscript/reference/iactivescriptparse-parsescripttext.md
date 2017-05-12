---
title: "IActiveScriptParse::ParseScriptText | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptParse.ParseScriptText
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptParse_ParseScriptText"
ms.assetid: 2d237d6c-cc65-415b-8808-72791304a136
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IActiveScriptParse::ParseScriptText
네임 스페페이스 선언을 추가하고 코드를 평가하여 주어진 코드 스크립트릿 구문 분석을 합니다.  
  
## 구문  
  
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
  
#### 매개 변수  
  
|||  
|-|-|  
|`pstrCode`|\[in\] 확인할 scriptlet 텍스트의 주소입니다.  스크립트 언어에 따라 이 문자열의 해석이 달라집니다.|  
|`pstrItemName`|\[in\] scriptlet을 평가할 컨텍스트를 제공하는 항목 이름의 주소입니다.  이 매개 변수가 NULL인 경우 엔진의 전역 컨텍스트를 스크립팅하여 코드가 평가됩니다.|  
|`punkContext`|\[in\] 컨텍스트 개체의 주소입니다.  이 개체는 디버깅 환경에서 사용하도록 예약되어 있습니다. 이러한 컨텍스트는 활성 런타임 컨텍스트를 나타내도록 디버거에서 제공할 수 있습니다.  이 매개 변수가 NULL인 경우 엔진에서 `pstrItemName`를 사용하여 컨텍스트를 식별합니다.|  
|`pstrDelimiter`|\[in\] scriptlet의 끝 구분 기호의 주소입니다.  `pstrCode`가 텍스트 스트림에서 구문 분석되는 경우 호스트는 일반적으로 작은따옴표 두 개\(''\)와 같은 구분 기호를 사용하여 스크립트릿의 끝을 검색합니다.  이 매개 변수는 호스트가 사용한 구분 기호를 지정하여 스크립팅 엔진에서 일부 조건 기본 전처리\(예: 구분 기호로 사용하기 위해 작은따옴표\['\]를 큰따옴표로 교체\)를 제공하도록 합니다.  스크립팅 엔진이 정확하게 얼마나 \(그리고 혹시\) 이 정보를 사용하는지는 스크립팅 엔진에 따라 달라집니다.  호스트가 한정자를 사용하여 scriptlet의 끝을 표시하지 않은 경우 이 매개 변수를 `NULL`로 설정합니다.|  
|`dwSourceContextCookie`|\[in\] 디버깅 목적으로 사용되는 쿠키입니다.|  
|`ulStartingLineNumber`|\[in\] 구문 분석이 시작되는 줄을 지정하는 0부터 시작하는 값입니다.|  
|`dwFlags`|\[in\] scriptlet과 연결된 플래그입니다.  다음 값을 조합하여 사용할 수 있습니다.|  
  
|값|의미|  
|-------|--------|  
|SCRIPTTEXT\_ISEXPRESSION|계산 식과 문 사이의 구분이 중요하지만 스크립트 언어에서 구문상 모호한 경우 이 플래그는 scriptlet을 문 또는 문 목록이 아닌 식으로 해석하도록 지정합니다.  기본적으로 문은 scriptlet 텍스트의 구문에서 올바른 선택을 결정할 수 없는 경우 가정합니다.|  
|SCRIPTTEXT\_ISPERSISTENT|이 호출 동안 추가된 코드는 스크립팅 엔진이 저장된 경우\(예: `IPersist*::Save` 호출을 통해\) 또는 스크립팅 엔진이 초기화된 상태로 다시 전환하여 재설정된 경우 저장되어야 함을 나타냅니다.|  
|SCRIPTTEXT\_ISVISIBLE|스크립트 텍스트가 스크립트의 네임스페이스에서 전역 변수로 표시되어야 함을 나타냅니다\(따라서 이름으로 호출이 가능\).|  
  
|||  
|-|-|  
|`pvarResult`|\[out\] 호출자가 아무런 결과를 예상하지 않을 경우\(즉, SCRIPTTEXT\_ISEXPRESSION 값이 설정되지 않음\) scriptlet 처리의 결과 또는 `NULL`를 받는 버퍼의 주소입니다.|  
|`pexcepinfo`|\[out\] 예외 정보를 받는 구조체의 주소입니다.  이 구조체는 `IActiveScriptParse::ParseScriptText`가 DISP\_E\_EXCEPTION을 반환할 경우에 채워집니다.|  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`DISP_E_EXCEPTION`|scriptlet 처리 시 예외가 발생하였습니다.  `pexcepinfo` 매개 변수에는 예외에 대한 정보가 포함됩니다.|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못된 포인터가 지정되었습니다.|  
|`E_NOTIMPL`|이 메서드는 지원되지 않습니다.  스크립팅 엔진은 식이나 문에서 런타임 계산을 지원하지 않습니다.|  
|`E_UNEXPECTED`|예상된 호출이 아닙니다\(예: 스크립팅 엔진이 초기화 되지 않았거나 종료 상태인 경우 또는 SCRIPTTEXT\_ISEXPRESSION 플래그가 설정되고 스크립팅 엔진이 초기화 상태인 경우\).|  
|`OLESCRIPT_E_SYNTAX`|scriptlet에 지정되지 않은 구문 오류가 발생했습니다.|  
  
## 설명  
 스크립팅 엔진이 초기화된 상태에 있는 경우 이 호출 동안에는 실제로 코드가 평가되지 않습니다. 오히려 이런 코드는 큐에 들어가 스크립팅 엔진이 시작된 상태로 전환\(또는 진행\)될 때 실행됩니다.  초기화된 상태에서는 실행이 허용되지 않으므로 초기화된 상태에서 SCRIPTTEXT\_ISEXPRESSION 플래그를 사용하여 이 메서드를 호출하는 것은 오류입니다.  
  
 스크립트릿은 식, 문 목록 또는 스크립트 언어에서 허용되는 모든 것이 될 수 있습니다.  예를 들어, 이 메서드는 HTML \<SCRIPT\> 태그의 평가에 사용됩니다. HTML 페이지로 실행할 문은 스크립트 상태로 컴파일되기 보다는 작성됩니다.  
  
 이 메서드에 전달된 코드는 코드의 유효하고 완료된 부분이어야 합니다.  예를 들어, VBScript에서는 Sub Function\(x\)을 사용하여 이 메서드를 한 번 호출한 다음 `End Sub`를 사용하여 두 번째로 호출하는 것은 잘못된 것입니다.  파서는 서브루틴을 완료하려면 두 번째 호출을 기다려서는 안 되지만 서브루틴 선언이 시작되었고 완료되지 않았기 때문에 구문 분석 오류를 생성해야 합니다.  
  
 스크립트 상태에 대한 자세한 내용은 [Windows 스크립트 엔진](../../winscript/windows-script-engines.md)의 스크립트 엔진 상태 섹션을 참조하십시오.  
  
## 참고 항목  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)
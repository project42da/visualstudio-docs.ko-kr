---
title: "IActiveScriptParse::AddScriptlet | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptParse.AddScriptlet
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptParse_AddScriptlet"
ms.assetid: 824929f4-4dd3-473a-92d9-0b96acea2f14
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptParse::AddScriptlet
코드 스크립트릿 스크립트에 추가합니다.  스크립트의 영구 상태 호스트 문서와 얽혀 되 고 환경에 있는 호스트는 스크립트를 복원 하는 데 담당이 메서드를 사용 하지 않고 통과 `IPersist*` 인터페이스.  내부 이벤트를 연결할 HTML 문서에 포함 된 코드의 스크립틀릿 허용 HTML 스크립팅 언어 기본 예제입니다 \(예를 들어, ONCLICK\="button1.text\='Exit'"\).  
  
## 구문  
  
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
  
#### 매개 변수  
 `pstrDefaultName`  
 \[in\] 주소 스크립트릿으로 연결할 기본 이름입니다.  이 이름에서 스크립트릿 명명 정보 \(ONCLICK 위의 예와\) 없으면 스크립트릿을 식별할 수 사용 됩니다.  이 매개 변수가 `NULL`, 필요한 경우 고유 이름, 스크립팅 엔진을 제조 합니다.  
  
 `pstrCode`  
 \[in\] 주소 추가 스크립트릿 텍스트입니다.  이 문자열을 해석 하기 위해서 스크립트 언어에 따라 달라 집니다.  
  
 `pstrItemName`  
 \[in\] 이 스크립트릿와 연관 된 항목 이름을 포함 하는 버퍼의 주소입니다.  이외에이 매개 변수를 `pstrSubItemName`, 스크립트릿에 있는 이벤트 처리기 개체를 식별 합니다.  
  
 `pstrSubItemName`  
 \[in\] 이름이 들어 있는 버퍼의 주소는 `subobject` 의 명명 된 항목이이 스크립트릿 된 연결. 이 이름에서 명명 된 항목의 형식 정보를 찾을 수 합니다.  스크립트릿은 대신 명명 된 항목에 연결 될 경우이 매개 변수가 NULL이 있는 `subitem`.  이외에이 매개 변수를 `pstrItemName`, 스크립트릿에는 이벤트 처리기는 특정 개체를 식별 합니다.  
  
 `pstrEventName`  
 \[in\] 스크립트릿의 이벤트 처리기는 이벤트의 이름이 들어 있는 버퍼의 주소입니다.  
  
 `pstrDelimiter`  
 \[in\] 주소 스크립트릿의 끝 구분 기호입니다.  경우는 `pstrCode` 매개 변수는 텍스트 스트림을 구문 분석, 스크립트릿의 끝을 검색 합니다 \('\) 작은따옴표 2 개 같은 호스트 일반적으로 구분 기호를 사용 합니다.  호스트 허용 일부 조건부 기본 전처리를 제공 하는 스크립팅 엔진 사용 구분이 매개이 변수를 지정 \(예를 들어, 작은 따옴표 \['\]에 두 개의 작은따옴표를 구분 기호로 사용 대체\).  정확 하 게 하는 방법 \(및 if\)는 스크립팅 엔진에서는 스크립팅 엔진에서이 정보를 사용에 따라 다릅니다.  호스트 스크립트릿의 끝을 표시 하는 구분 기호로 사용 하지 않은 경우이 매개 변수는 NULL로 설정 합니다.  
  
 `dwSourceContextCookie`  
 \[in\] 디버깅 목적으로 사용 되는 응용 프로그램 정의 값입니다.  
  
 `ulStartingLineNumber`  
 \[in\] 구문 분석에서 시작 되는 줄부터 값입니다.  
  
 `dwFlags`  
 \[in\] 스크립트릿와 연결 된 플래그입니다.  다음 값 조합이 될 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|SCRIPTTEXT\_ISVISIBLE|스크립트 텍스트를 표시 해야 함을 나타냅니다 \(및 따라서 이름으로 호출할 수\) 이름 공간의 스크립트의 전역 메서드로.|  
|SCRIPTTEXT\_ISPERSISTENT|스크립트를 저장 하는 경우이 호출 하는 동안 추가 코드를 저장 하도록 나타냅니다 \(예를 들어, 한 호출을 통해 `IPersist*::Save`\), 또는 스크립팅 엔진이 초기화 상태로 전환을 통해 다시 설정 됩니다.  이 상태에 대 한 자세한 내용은 스크립트 엔진 상태를 참조 하십시오.|  
  
 `pbstrName` ,  
 \[out\] 실제 이름 스크립트릿을 식별 하는 데 사용 합니다.  이 순서 대로 하는 것: 기본 이름을 제공 스크립트릿 텍스트를 명시적으로 지정 하는 이름, `pstrDefaultName`, 또는 고유한 이름을 스크립트 엔진에서 합성.  
  
 `pexcepinfo` ,  
 \[out\] 예외 정보가 포함 된 구조체의 주소입니다.  DISP\_E\_EXCEPTION이 반환 된 경우이 구조 입력 해야 합니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`DISP_E_EXCEPTION`|스크립트릿의 구문 분석에서 예외가 발생 했습니다.  `pexcepinfo` 매개 변수는 예외에 대 한 정보를 포함 합니다.|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_NOTIMPL`|이 메서드는 지원 되지 않습니다. 스크립팅 엔진 스크립틀릿 이벤트 싱크를 추가 하는 것을 지원 하지 않습니다.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\) 및 따라서 실패 합니다.|  
|`OLESCRIPT_E_INVALIDNAME`|이 스크립팅 언어에 제공 된 기본 이름이 올바르지 않습니다.|  
|`OLESCRIPT_E_SYNTAX`|알 수 없는 구문 오류가 스크립트릿에서 발생 했습니다.|  
  
## 참고 항목  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)
---
title: "디버깅을 위한 SDK 도우미 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dbgmetric.lib"
  - "레지스트리, SDK 디버깅"
  - "디버깅 SDK, 레지스트리 위치"
  - "dbgmetric.h"
  - "메트릭 [디버깅 SDK]"
ms.assetid: 80a52e93-4a04-4ab2-8adc-a7847c2dc20b
caps.latest.revision: 28
caps.handback.revision: 28
ms.author: "gregvanl"
manager: "ghogen"
---
# 디버깅을 위한 SDK 도우미
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이러한 함수 및 선언을 c \+ \+에서 디버그 엔진, 식 계산기 및 기호 공급자 구현에 대 한 전역 도우미 함수입니다.  
  
> [!NOTE]
>  이 지금은 이러한 함수와 선언은 관리 되는 버전입니다.  
  
## 개요  
 Visual Studio 사용 하는 순서에 디버깅 엔진, 식 계산기 및 기호 공급자는 등록 되어야 합니다.  이 레지스트리 하위 키 및 항목 "설정은 메트릭."로 알려져, 설정 하 여 수행 됩니다. 다음 전역 함수는 이러한 메트릭을 업데이트 하는 프로세스를 간편 하 게 디자인 되었습니다.  이러한 함수에서 업데이트 된 각 레지스트리 하위 키의 레이아웃을 확인 하려면 레지스트리 위치를 참조 하십시오.  
  
## 일반적인 메트릭은 함수  
 이러한 디버그 엔진에 사용 되는 일반적인 기능입니다.  함수 식 계산기에 대 한 특별 한 기호 공급자는 나중에 자세히 설명 되어 있습니다.  
  
### GetMetric 메서드  
 메트릭 값을 레지스트리에서 검색합니다.  
  
```cpp#  
HRESULT GetMetric(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   DWORD * pdwValue,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parameter|설명|  
|---------------|--------|  
|pszMachine|\[in\] 해당 등록 작성 된 가능 하면 원격 컴퓨터의 이름 \(`NULL` 로컬 컴퓨터를 의미\)입니다.|  
|pszType|\[in\] 미터법 형식 중 하나입니다.|  
|guidSection|\[in\] 특정 엔진, 계산기, 예외 등의 GUID입니다.  이 하위 섹션에서 특정 요소에 대 한 미터법 형식 지정합니다.|  
|pszMetric|\[in\] 가져올 메트릭입니다.  이 특정 값 이름에 해당합니다.|  
|pdwValue|\[in\] 메트릭은 값의 저장소 위치입니다.  여러 가지 맛의 GetMetric DWORD \(이 예에서 같이\), BSTR, GUID 또는 Guid의 배열을 반환할 수 있습니다.|  
|pszAltRoot|\[in\] 사용 하 여 대체 레지스트리 루트입니다.  설정 `NULL` 기본값을 사용 합니다.|  
  
### SetMetric 메서드  
 레지스트리에서 지정 된 메트릭 값을 설정합니다.  
  
```cpp#  
HRESULT SetMetric(  
         LPCWSTR pszType,  
         REFGUID guidSection,  
         LPCWSTR pszMetric,  
   const DWORD   dwValue,  
         bool    fUserSpecific,  
         LPCWSTR pszAltRoot  
);  
```  
  
|Parameter|설명|  
|---------------|--------|  
|pszType|\[in\] 미터법 형식 중 하나입니다.|  
|guidSection|\[in\] 특정 엔진, 계산기, 예외 등의 GUID입니다.  이 하위 섹션에서 특정 요소에 대 한 미터법 형식 지정합니다.|  
|pszMetric|\[in\] 가져올 메트릭입니다.  이 특정 값 이름에 해당합니다.|  
|dwValue|\[in\] 저장소 위치는 미터법의 값입니다.  여러 가지 맛의 SetMetric DWORD \(이 예에서\), BSTR, GUID 또는 Guid의 배열을 저장할 수 있습니다.|  
|fUserSpecific|\[in\] 사용자 고유의 메트릭입니다 및 로컬 시스템 하이브를 대신 사용자의 하이브를 작성 해야 하는 경우 TRUE입니다.|  
|pszAltRoot|\[in\] 사용 하 여 대체 레지스트리 루트입니다.  설정 `NULL` 기본값을 사용 합니다.|  
  
### RemoveMetric 메서드  
 지정 된 메트릭의 레지스트리에서 제거합니다.  
  
```cpp#  
HRESULT RemoveMetric(  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parameter|설명|  
|---------------|--------|  
|pszType|\[in\] 미터법 형식 중 하나입니다.|  
|guidSection|\[in\] 특정 엔진, 계산기, 예외 등의 GUID입니다.  이 하위 섹션에서 특정 요소에 대 한 미터법 형식 지정합니다.|  
|pszMetric|\[in\] 제거할 메트릭입니다.  이 특정 값 이름에 해당합니다.|  
|pszAltRoot|\[in\] 사용 하 여 대체 레지스트리 루트입니다.  설정 `NULL` 기본값을 사용 합니다.|  
  
### EnumMetricSections 메서드  
 다양 한 메트릭 섹션 레지스트리에서 열거합니다.  
  
```cpp#  
HRESULT EnumMetricSections(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   GUID *  rgguidSections,  
   DWORD * pdwSize,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parameter|설명|  
|---------------|--------|  
|pszMachine|\[in\] 해당 등록 작성 된 가능 하면 원격 컴퓨터의 이름 \(`NULL` 로컬 컴퓨터를 의미\)입니다.|  
|pszType|\[in\] 미터법 형식 중 하나입니다.|  
|rgguidSections|\[in, out\] 미리 할당 된 배열에서 Guid입니다.|  
|pdwSize|\[in\] 최대 저장할 수 있는 Guid는 `rgguidSections` 배열입니다.|  
|pszAltRoot|\[in\] 사용 하 여 대체 레지스트리 루트입니다.  설정 `NULL` 기본값을 사용 합니다.|  
  
## 식 계산기 기능  
  
|Function|설명|  
|--------------|--------|  
|GetEEMetric|메트릭 값을 레지스트리에서 검색합니다.|  
|SetEEMetric|레지스트리에서 지정 된 메트릭 값을 설정합니다.|  
|RemoveEEMetric|지정 된 메트릭의 레지스트리에서 제거합니다.|  
|GetEEMetricFile|파일 이름에서 지정 된 메트릭을 가져옵니다 및 로드 파일 내용을 문자열로 반환 합니다.|  
  
## 예외 함수  
  
|Function|설명|  
|--------------|--------|  
|GetExceptionMetric|메트릭 값을 레지스트리에서 검색합니다.|  
|SetExceptionMetric|레지스트리에서 지정 된 메트릭 값을 설정합니다.|  
|RemoveExceptionMetric|지정 된 메트릭의 레지스트리에서 제거합니다.|  
|RemoveAllExceptionMetrics|모든 예외 메트릭스를 레지스트리에서 제거합니다.|  
  
## 공급자가 함수 기호  
  
|Function|설명|  
|--------------|--------|  
|GetSPMetric|메트릭 값을 레지스트리에서 검색합니다.|  
|SetSPMetric|레지스트리에서 지정 된 메트릭 값을 설정합니다.|  
|RemoveSPMetric|지정 된 메트릭의 레지스트리에서 제거합니다.|  
  
## 열거 함수  
  
|Function|설명|  
|--------------|--------|  
|EnumMetricSections|모든 메트릭을 메트릭 지정 된 형식에 대해 열거합니다.|  
|EnumDebugEngine|등록 된 디버깅 엔진을 열거합니다.|  
|EnumEEs|등록 된 식 계산기를 열거합니다.|  
|EnumExceptionMetrics|모든 예외 메트릭스를 열거합니다.|  
  
## 메트릭 정의  
 이러한 정의 대 한 미리 정의 된 메트릭 이름 사용할 수 있습니다.  다양 한 레지스트리 키 및 값 이름 및 모든 와이드 문자 문자열로 정의 된 이름에 해당 합니다: 예를 들어, `extern LPCWSTR metrictypeEngine`.  
  
|미리 정의 된 메트릭 형식|설명 합니다: 기본 키에 대해....|  
|--------------------|--------------------------|  
|metrictypeEngine|모든 엔진이 메트릭스를 디버그합니다.|  
|metrictypePortSupplier|모든 포트 공급자 메트릭입니다.|  
|metrictypeException|모든 예외 메트릭이 있습니다.|  
|metricttypeEEExtension|모든 식 계산기 확장 합니다.|  
  
|디버그 엔진 속성|설명|  
|---------------|--------|  
|metricAddressBP|주소 중단점에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricAlwaysLoadLocal|항상 로컬로 디버그 엔진을 로드 하려면 0이 아닌 설정.|  
|metricLoadInDebuggeeSession|사용 하지 않는|  
|metricLoadedByDebuggee|디버그 엔진 항상 또는 디버깅 중인 프로그램에 의해 로드 됩니다 나타내는 0이 아닌 설정.|  
|metricAttach|첨부 파일을 기존 프로그램에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricCallStackBP|호출 스택 중단점에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricConditionalBP|조건부 중단점의 설정에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricDataBP|중단점에서 데이터 변경의 설정에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricDisassembly|생산 하는 분해 목록에 대 한 지원을 나타내기 위해 0이 아닌 설정 합니다.|  
|metricDumpWriting|덤프 \(는 출력 장치 메모리 덤프\) 쓰기에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricENC|편집 하며 계속 하기에 대 한 지원을 나타낼 수를 0이 아닌 설정 합니다. **Note:**  사용자 지정 디버그 엔진이 되지 않도록 설정 해야 합니다 또는 항상 0으로 설정 해야 합니다.|  
|metricExceptions|예외에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricFunctionBP|\(특정 함수 이름을 호출할 때 중단 중단점\) 명명 된 중단점에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricHitCountBP|중단점 \(만 되 고 특정 횟수에 도달 하면 트리거되는 중단점\) "방문 포인트"의 설정에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricJITDebug|0이 아닌\-의 시간 \(실행 중인 프로세스에 예외가 발생 하면 디버거에서 시작 됩니다\) 디버깅을 지원 하기에 설정 합니다.|  
|metricMemory|사용 하지 않는|  
|metricPortSupplier|하나 구현 되는 경우 포트 공급자의 CLSID에 설정 합니다.|  
|metricRegisters|사용 하지 않는|  
|metricSetNextStatement|\(어떤 중간 문 실행을 건너뜁니다\) 다음 문을 설정에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricSuspendThread|스레드 실행을 일시 중단 하는 것에 대 한 지원을 나타내기 위해 0이 아닌 설정.|  
|metricWarnIfNoSymbols|기호가 있는 경우 사용자가 알림을 받을 수 나타내려면 0 이외의 설정 하십시오.|  
|metricProgramProvider|이 프로그램 공급자의 CLSID에 설정 합니다.|  
|metricAlwaysLoadProgramProviderLocal|이 0이 아닌 프로그램 공급자가 항상 로컬로 로드 된 것을 나타냅니다에 설정 합니다.|  
|metricEngineCanWatchProcess|디버그 엔진 프로그램 공급자의 이벤트 처리에 대 한 감시를 나타내기 위해 0이 아닌 설정 합니다.|  
|metricRemoteDebugging|원격 디버깅을 지원 하려면 0이 아닌 설정 합니다.|  
|metricEncUseNativeBuilder|이 0이 아닌 편집 하며 계속 하는 관리자는 디버그 엔진 encbuild.dll을 편집 하며 계속 하기에 대 한 빌드를 사용할 수를 설정 합니다. **Note:**  사용자 지정 디버그 엔진이 되지 않도록 설정 해야 합니다 또는 항상 0으로 설정 해야 합니다.|  
|metricLoadUnderWOW64|디버그 엔진 디버기 프로세스에서 WOW에서 64 비트 프로세스를 디버깅할 때 로드 하도록 나타내는 0 이외의 설정 합니다. 그렇지 않으면 디버그 엔진 \(w o w 64에서 실행 되 고\)는 Visual Studio 프로세스에서 로드 됩니다.|  
|metricLoadProgramProviderUnderWOW64|프로그램 공급자는 WOW에서 64 비트 프로세스를 디버깅할 때 디버기가 프로세스에서 로드 된 것을 나타냅니다에 0 이외의 설정 합니다. 그렇지 않으면 Visual Studio 프로세스에서 로드 됩니다.|  
|metricStopOnExceptionCrossingManagedBoundary|처리 되지 않은 예외 코드 관리\/비관리 경계를 넘어 발생 하는 경우 프로세스를 중지 하도록 지정 하는 0 이외의 설정 합니다.|  
|metricAutoSelectPriority|이 자동 선택 디버그 엔진 \(높은 값은 높은 우선 순위\)의 우선 순위를 설정 합니다.|  
|metricAutoSelectIncompatibleList|자동 선택 영역을 무시 합니다 디버깅 엔진에 대 한 Guid를 지정 하는 항목을 포함 하는 레지스트리 키입니다.  이러한 항목에는 숫자입니다 \(0, 1, 2, 등\)으로 GUID는 문자열로 표현 합니다.|  
|metricIncompatibleList|이 디버그 엔진과 호환 되지 않는 디버깅 엔진에 대 한 Guid를 지정 하는 항목을 포함 하는 레지스트리 키입니다.|  
|metricDisableJITOptimization|디버깅 하는 동안 적시에 최적화 \(예: 관리 되는 코드\)를 사용 하지 않도록 지정 하려면 0이 아닌 설정 합니다.|  
  
|식 평가기 속성|설명|  
|--------------|--------|  
|metricEngine|지정 된 식 계산기는 지원 되는 디버깅 엔진의 수를 보유 합니다.|  
|metricPreloadModules|이 프로그램에 대해 식 계산기를 시작 하는 경우 모듈 미리 로드 합니다 나타내려면 0이 아닌 설정.|  
|metricThisObjectName|이것을 "이" 개체 이름으로 설정 합니다.|  
  
|식 평가기 확장 속성|설명|  
|-----------------|--------|  
|metricExtensionDll|이 확장을 지 원하는 dll의 이름입니다.|  
|metricExtensionRegistersSupported|지원 되는 레지스터의 목록입니다.|  
|metricExtensionRegistersEntryPoint|레지스터에 액세스 하기 위한 시작 지점입니다.|  
|metricExtensionTypesSupported|지원 되는 형식의 목록입니다.|  
|metricExtensionTypesEntryPoint|형식에 액세스 하는 것에 대 한 진입점입니다.|  
  
|포트 공급자 속성|설명|  
|---------------|--------|  
|metricPortPickerCLSID|\(대화 상자 사용자 포트를 선택 하 고 디버깅 하는 데 사용 하는 포트를 추가할 수 있습니다\) 포트 선택기의 CLSID입니다.|  
|metricDisallowUserEnteredPorts|사용자가 입력 한 포트 포트 공급자에 추가할 수 없으면 0이 아닌 \(이 포트 선택 대화 상자의 기본적으로 읽기 전용으로 설정\) 합니다.|  
|metricPidBase|포트 공급자가 프로세스 Id를 할당 하는 경우 사용 되는 기본 프로세스 ID.|  
  
|미리 정의 된 SP 저장소 형식|설명|  
|-----------------------|--------|  
|storetypeFile|기호를 별도 파일에 저장 됩니다.|  
|storetypeMetadata|기호는 어셈블리의 메타 데이터로 저장 됩니다.|  
  
|기타 속성|설명|  
|-----------|--------|  
|metricShowNonUserCode|Nonuser 코드를 표시 하는 0 이외의 설정 합니다.|  
|metricJustMyCodeStepping|이 단계별 실행 사용자 코드에만 발생할 수 있습니다 나타내기 위해 0이 아닌 설정.|  
|metricCLSID|미터는 특정 종류의 개체에 대 한 CLSID입니다.|  
|metricName|미터는 특정 종류의 개체에 대 한 친숙 한 이름입니다.|  
|metricLanguage|언어 이름입니다.|  
  
## 레지스트리 위치  
 메트릭을 읽기 \/ 특별히에 있는 레지스트리에 기록 되는 `VisualStudio` 하위 키입니다.  
  
> [!NOTE]
>  대부분의 경우 메트릭 HKEY\_LOCAL\_MACHINE 키에 기록 됩니다.  그러나 때로는 HKEY\_CURRENT\_USER 키 대상 됩니다.  Dbgmetric.lib 두 키를 처리합니다.  메트릭을 가져오는 경우 HKEY\_CURRENT\_USER 검색 한 첫 번째, 다음 HKEY\_LOCAL\_MACHINE입니다.  메트릭을 설정 하는 경우 최상위 수준 키를 사용 하 여 매개 변수를 지정 합니다.  
  
 *\[레지스트리 키\]*\\  
  
 `Software`\\  
  
 `Microsoft`\\  
  
 `VisualStudio`\\  
  
 *\[버전 루트\]*\\  
  
 *\[메트릭 루트\]*\\  
  
 *\[메트릭 형식\]*\\  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
|자리 표시자|설명|  
|------------|--------|  
|*\[레지스트리 키\]*|`HKEY_CURRENT_USER` 또는 `HKEY_LOCAL_MACHINE`|  
|*\[버전 루트\]*|Visual Studio 버전 \(예를 들어, `7.0`, `7.1`, 또는 `8.0`\).  그러나이 루트를 사용 하 여 수정할 수도 있습니다 해당 **\/rootsuffix** 전환 **devenv.exe**.  VSIP에 대 한 버전 루트, 예를 들어, 8.0Exp 이므로이 한정자 Exp를 일반적입니다.|  
|*\[메트릭 루트\]*|이 중 하나입니다 `AD7Metrics` 또는 `AD7Metrics(Debug)`dbgmetric.lib의 디버그 버전 사용 여부에 따라. **Note:**  Dbgmetric.lib를 사용 하는지 여부 디버그 및 릴리스 간에 차이가 있는 경우이 명명 규칙 준수 될 해야 합니다 버전에서 레지스트리를 반영 해야 합니다.|  
|*\[메트릭 형식\]*|쓸 미터법의 종류: `Engine`, `ExpressionEvaluator`, `SymbolProvider`등.  모두에서 dbgmetric.h로 정의 된 `metricTypeXXXX`, 어디 `XXXX` 특정 유형의 이름입니다.|  
|*\[메트릭\]*|메트릭을 설정에 값이 할당 될 수 있는 항목의 이름입니다.  실제 회사 메트릭을 메트릭 형식에 따라 달라 집니다.|  
|*\[메트릭 값\]*|미터법에 할당 되는 값입니다.  값 \(문자열, 숫자, 등\)가 있어야 형식을 미터법에 따라 달라 집니다.|  
  
> [!NOTE]
>  모든 Guid 형식으로 저장 된 `{GUID}`.  예를 들면 `{123D150B-FA18-461C-B218-45B3E4589F9B}`와 같습니다.  
  
### 디버그 엔진  
 다음 디버그 엔진 메트릭 레지스트리에서 조직입니다.  `Engine`디버그 엔진에 대 한 미터법 형식 이름으로 서 해당  *\[메트릭 형식\]* 위의 레지스트리 하위 트리에 있습니다.  
  
 `Engine`\\  
  
 *\[guid 엔진\]*\\  
  
 `CLSID`\=  *\[클래스 guid\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 `PortSupplier`\\  
  
 `0`\=  *\[포트 공급자 guid\]*  
  
 `1`\=  *\[포트 공급자 guid\]*  
  
|자리 표시자|설명|  
|------------|--------|  
|*\[엔진 guid\]*|디버그 엔진의 GUID입니다.|  
|*\[클래스 guid\]*|이 디버그 엔진을 구현 하는 클래스의 GUID를 지정 합니다.|  
|*\[포트 공급자 guid\]*|있는 경우 포트 공급자의 GUID입니다.  디버그 엔진 기본 포트 공급자를 사용 하 고 따라서 자신의 공급 업체를 지정 하지.  이 경우에 하위 키 `PortSupplier` 것입니다.|  
  
### 포트 공급자  
 다음 레지스트리에서 포트 공급자 메트릭을 조직입니다.  `PortSupplier`포트 공급자에 대 한 미터법 형식 이름으로 서 해당  *\[메트릭 형식\]*.  
  
 `PortSupplier`\\  
  
 *\[포트 공급자 guid\]*\\  
  
 `CLSID`\=  *\[클래스 guid\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
|자리 표시자|설명|  
|------------|--------|  
|*\[포트 공급자 guid\]*|포트 공급자의 GUID를|  
|*\[클래스 guid\]*|이 포트 공급자를 구현 하는 클래스의 GUID를|  
  
### 기호 공급자  
 다음의 기호 협력 업체 메트릭스는 레지스트리에서 구성입니다.  `SymbolProvider`미터법 형식 이름이 기호 공급자 및 해당  *\[메트릭 형식\]*.  
  
 `SymbolProvider`\\  
  
 *\[공급자 guid 기호\]*\\  
  
 `file`\\  
  
 `CLSID`\=  *\[클래스 guid\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 `metadata`\\  
  
 `CLSID`\=  *\[클래스 guid\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
|자리 표시자|설명|  
|------------|--------|  
|*\[기호 공급자 guid\]*|기호 공급자의 GUID를|  
|*\[클래스 guid\]*|이 기호 공급자를 구현 하는 클래스의 GUID를|  
  
### 식 계산기  
 다음의 식 계산기 메트릭 레지스트리에서 구성입니다.  `ExpressionEvaluator`식 계산기는 미터법 형식 이름입니다 및 해당  *\[메트릭 형식\]*.  
  
> [!NOTE]
>  미터법 형식에 대 한 `ExpressionEvaluator` 식 계산기에 대 한 메트릭 변경 내용을 모두 적절 한 식 계산기 미터 기능을 통해 진행 될 것으로 간주 되는 dbgmetric.h에 정의 되어 있지 않습니다 \(의 레이아웃은 `ExpressionEvaluator` dbgmetric.lib 안에 표시 되지 않도록 하위 키가 다소 복잡 한 것\).  
  
 `ExpressionEvaluator`\\  
  
 *\[언어 guid\]*\\  
  
 *\[공급 업체 guid\]*\\  
  
 `CLSID`\=  *\[클래스 guid\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 `Engine`\\  
  
 `0`\=  *\[엔진 guid 디버그\]*  
  
 `1`\=  *\[엔진 guid 디버그\]*  
  
|자리 표시자|설명|  
|------------|--------|  
|*\[언어 guid\]*|언어의 GUID|  
|*\[공급 업체 guid\]*|공급 업체의 GUID|  
|*\[클래스 guid\]*|이 식 계산기를 구현 하는 클래스의 GUID를|  
|*\[디버그 엔진 guid\]*|계산 열이 사용 되는 디버그 엔진의 GUID|  
  
### 식 계산기를 확장  
 다음 레지스트리에서 식 계산기 확장 기준을 조직입니다.  `EEExtensions`미터법 형식 이름 식 계산기 확장명입니다 및 해당  *\[메트릭 형식\]*.  
  
 `EEExtensions`\\  
  
 *\[확장 guid\]*\\  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
|자리 표시자|설명|  
|------------|--------|  
|*\[확장 guid\]*|식 평가기 확장의 GUID|  
  
### 예외  
 다음 예외 기준을 레지스트리에서 조직입니다.  `Exception`예외에 대 한 미터법 형식 이름으로 서 해당  *\[메트릭 형식\]*.  
  
 `Exception`\\  
  
 *\[디버깅 엔진 guid\]*\\  
  
 *\[예외 형식\]*\\  
  
 *\[예외\]*\\  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[예외\]*\\  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
 *\[메트릭\] \= \[메트릭 값\]*  
  
|자리 표시자|설명|  
|------------|--------|  
|*\[디버그 엔진 guid\]*|예외를 지 원하는 디버그 엔진의 GUID입니다.|  
|*\[예외 형식\]*|처리할 수 있는 예외 클래스를 식별 하는 하위 키에 대 한 일반 제목입니다.  Typical names are **C\+\+ Exceptions**, **Win32 Exceptions**, **Common Language Runtime Exceptions**, and **Native Run\-Time Checks**.  이 이름에 사용자의 특정 클래스를 식별할 수도 사용 됩니다.|  
|*\[예외\]*|예외 이름: 예를 들어, **\_com\_error** 또는 **Control\-Break**.  이러한 이름은 특정 예외가 사용자에 게 확인 하도 사용 됩니다.|  
  
## 요구 사항  
 이러한 파일에는 있는 [!INCLUDE[vs_dev10_ext](../../../extensibility/debugger/reference/includes/vs_dev10_ext_md.md)] SDK 설치 디렉터리 \(기본적으로  *\[드라이브\]*\\Program Files\\Microsoft Visual Studio 2010 SDK\\\).  
  
 헤더: includes\\dbgmetric.h  
  
 라이브러리: libs\\ad2de.lib, libs\\dbgmetric.lib  
  
## 참고 항목  
 [API 참조](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)
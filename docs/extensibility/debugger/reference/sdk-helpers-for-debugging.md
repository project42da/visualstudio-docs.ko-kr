---
title: "디버깅에 대 한 SDK 도우미 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dbgmetric.lib
- registry, Debugging SDK
- Debugging SDK, registry locations
- dbgmetric.h
- metrics [Debugging SDK]
ms.assetid: 80a52e93-4a04-4ab2-8adc-a7847c2dc20b
caps.latest.revision: "28"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9c5d24c8a3a2bb81c87b2cc405a6885b8f23374
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="sdk-helpers-for-debugging"></a>디버깅을 위한 도우미 SDK
이러한 함수 및 선언에는 c + +에서 디버그 엔진, 식 계산기 및 기호 공급자를 구현 하기 위한 전역 도우미 함수입니다.  
  
> [!NOTE]
>  이 이번에는 이러한 함수 및 선언 없는 관리 되는 버전이 있습니다.  
  
## <a name="overview"></a>개요  
 Visual Studio에서 사용할 디버그 엔진, 식 계산기 및 기호 공급자에 대 한 순서에 등록 해야 합니다. 이 레지스트리 하위 키와 "설정 메트릭." 라고도 하는 항목을 설정 하 여 작업 수행 다음 전역 함수는 이러한 메트릭을 업데이트를 손쉽게 설계 되었습니다. 이러한 함수에 의해 업데이트 되는 각 레지스트리 하위 키의 레이아웃을 알아보려면 레지스트리 위치에는 섹션을 참조 합니다.  
  
## <a name="general-metric-functions"></a>일반 메트릭을 함수  
 이들은 디버그 엔진에서 사용 하는 일반적인 기능입니다. 식 계산기에 대 한 함수를 특수화할 및 기호 공급자는 나중에 자세히 설명 합니다.  
  
### <a name="getmetric-method"></a>GetMetric 메서드  
 레지스트리에서 메트릭 값을 검색합니다.  
  
```cpp  
HRESULT GetMetric(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   DWORD * pdwValue,  
   LPCWSTR pszAltRoot  
);  
```  
  
|매개 변수|설명|  
|---------------|-----------------|  
|pszMachine|[in] 해당 레지스터를 쓸 수 있는 원격 컴퓨터의 이름 (`NULL` 로컬 컴퓨터를 의미).|  
|pszType|[in] 메트릭 형식 중 하나입니다.|  
|guidSection|[in] 특정 엔진, 계산기, 예외 등의 GUID입니다. 이 하위 섹션에서 특정 요소에 대 한 메트릭 유형 지정합니다.|  
|pszMetric|[in] 가져올 메트릭입니다. 이 특정 값 이름에 해당합니다.|  
|pdwValue|[in] 에 대 한 메트릭에서 값의 저장소 위치입니다. 여러 버전의이 예제와 같이이 DWORD, BSTR, GUID 또는 Guid의 배열을 반환할 수 있는 GetMetric 가지가 있습니다.|  
|pszAltRoot|[in] 사용 하는 대체 레지스트리 루트입니다. 로 설정 `NULL` 기본값을 사용 하도록 합니다.|  
  
### <a name="setmetric-method"></a>SetMetric 메서드  
 레지스트리에 지정된 된 메트릭 값을 설정 합니다.  
  
```cpp  
HRESULT SetMetric(  
         LPCWSTR pszType,  
         REFGUID guidSection,  
         LPCWSTR pszMetric,  
   const DWORD   dwValue,  
         bool    fUserSpecific,  
         LPCWSTR pszAltRoot  
);  
```  
  
|매개 변수|설명|  
|---------------|-----------------|  
|pszType|[in] 메트릭 형식 중 하나입니다.|  
|guidSection|[in] 특정 엔진, 계산기, 예외 등의 GUID입니다. 이 하위 섹션에서 특정 요소에 대 한 메트릭 유형 지정합니다.|  
|pszMetric|[in] 가져올 메트릭입니다. 이 특정 값 이름에 해당합니다.|  
|dwValue|[in] 에 대 한 메트릭에 있는 값의 저장소 위치입니다. 여러 운영 체제 (이 예제의) DWORD, BSTR, GUID 또는 Guid의 배열에 저장할 수 있는 SetMetric의 가지가 있습니다.|  
|fUserSpecific|[in] 에 대 한 메트릭을 사용자 고유의 로컬 컴퓨터 하이브 대신 사용자의 하이브에 써야 하는 경우 TRUE입니다.|  
|pszAltRoot|[in] 사용 하는 대체 레지스트리 루트입니다. 로 설정 `NULL` 기본값을 사용 하도록 합니다.|  
  
### <a name="removemetric-method"></a>RemoveMetric 메서드  
 지정 된 메트릭에 레지스트리에서 제거합니다.  
  
```cpp  
HRESULT RemoveMetric(  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   LPCWSTR pszAltRoot  
);  
```  
  
|매개 변수|설명|  
|---------------|-----------------|  
|pszType|[in] 메트릭 형식 중 하나입니다.|  
|guidSection|[in] 특정 엔진, 계산기, 예외 등의 GUID입니다. 이 하위 섹션에서 특정 요소에 대 한 메트릭 유형 지정합니다.|  
|pszMetric|[in] 제거할 메트릭입니다. 이 특정 값 이름에 해당합니다.|  
|pszAltRoot|[in] 사용 하는 대체 레지스트리 루트입니다. 로 설정 `NULL` 기본값을 사용 하도록 합니다.|  
  
### <a name="enummetricsections-method"></a>EnumMetricSections 메서드  
 레지스트리에서 메트릭 다양 한 섹션을 열거합니다.  
  
```cpp  
HRESULT EnumMetricSections(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   GUID *  rgguidSections,  
   DWORD * pdwSize,  
   LPCWSTR pszAltRoot  
);  
```  
  
|매개 변수|설명|  
|---------------|-----------------|  
|pszMachine|[in] 해당 레지스터를 쓸 수 있는 원격 컴퓨터의 이름 (`NULL` 로컬 컴퓨터를 의미).|  
|pszType|[in] 메트릭 형식 중 하나입니다.|  
|rgguidSections|[out에서] 미리 할당 된 배열에서를 입력 하도록 하는 Guid입니다.|  
|pdwSize|[in] Guid에 저장할 수 있는 최대 수는 `rgguidSections` 배열입니다.|  
|pszAltRoot|[in] 사용 하는 대체 레지스트리 루트입니다. 로 설정 `NULL` 기본값을 사용 하도록 합니다.|  
  
## <a name="expression-evaluator-functions"></a>식 계산기 함수  
  
|함수|설명|  
|--------------|-----------------|  
|GetEEMetric|레지스트리에서 메트릭 값을 검색합니다.|  
|SetEEMetric|레지스트리에 지정된 된 메트릭 값을 설정 합니다.|  
|RemoveEEMetric|지정 된 메트릭에 레지스트리에서 제거합니다.|  
|GetEEMetricFile|지정 된 메트릭에에서 파일 이름을 가져옵니다 로드 파일 콘텐츠를 문자열로 반환 합니다.|  
  
## <a name="exception-functions"></a>예외 함수  
  
|함수|설명|  
|--------------|-----------------|  
|GetExceptionMetric|레지스트리에서 메트릭 값을 검색합니다.|  
|SetExceptionMetric|레지스트리에 지정된 된 메트릭 값을 설정 합니다.|  
|RemoveExceptionMetric|지정 된 메트릭에 레지스트리에서 제거합니다.|  
|RemoveAllExceptionMetrics|모든 예외 메트릭을 레지스트리에서 제거합니다.|  
  
## <a name="symbol-provider-functions"></a>기호 공급자 함수  
  
|함수|설명|  
|--------------|-----------------|  
|GetSPMetric|레지스트리에서 메트릭 값을 검색합니다.|  
|SetSPMetric|레지스트리에 지정된 된 메트릭 값을 설정 합니다.|  
|RemoveSPMetric|지정 된 메트릭에 레지스트리에서 제거합니다.|  
  
## <a name="enumeration-functions"></a>열거 함수  
  
|함수|설명|  
|--------------|-----------------|  
|EnumMetricSections|지정된 된 메트릭 형식에 대 한 모든 메트릭을 열거합니다.|  
|EnumDebugEngine|등록 된 디버그 엔진을 열거합니다.|  
|EnumEEs|등록 된 식 계산기를 열거합니다.|  
|EnumExceptionMetrics|모든 예외 메트릭을 열거합니다.|  
  
## <a name="metric-definitions"></a>메트릭 정의  
 미리 정의 된 메트릭 이름에 대 한 이러한 정의 사용할 수 있습니다. 이름은 와이드 문자 문자열으로 정의 된 모든 다양 한 레지스트리 키 및 값 이름에 해당 합니다: 예를 들어 `extern LPCWSTR metrictypeEngine`합니다.  
  
|미리 정의 된 메트릭 형식|설명:에 대 한 기본 키 중...|  
|-----------------------------|---------------------------------------|  
|metrictypeEngine|모든 디버그 엔진 메트릭.|  
|metrictypePortSupplier|포트의 모든 공급 업체 메트릭입니다.|  
|metrictypeException|모든 예외 메트릭입니다.|  
|metricttypeEEExtension|모든 식 계산기 확장입니다.|  
  
|디버그 엔진 속성|설명|  
|-----------------------------|-----------------|  
|metricAddressBP|로 설정 주소 중단점에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricAlwaysLoadLocal|로 설정 항상 로컬로 디버그 엔진을 로드 하기 위해 0이 아닌 합니다.|  
|metricLoadInDebuggeeSession|사용 되지 않음|  
|metricLoadedByDebuggee|로 설정 하거나 디버깅 중인 프로그램 디버그 엔진 로드 항상은 0이 아닌 합니다.|  
|metricAttach|로 설정 하 고 기존 프로그램 첨부 파일에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricCallStackBP|로 설정 호출 스택 중단점에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricConditionalBP|로 설정 조건부 중단점의 설정에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricDataBP|설정 데이터의 변경에 대 한 중단점 설정에 대 한 지원을 나타내는 데 0이 아닌.|  
|metricDisassembly|에 디스어셈블리 목록 프로덕션에 대 한 지원을 나타내는 데 0이 아닌 설정 합니다.|  
|metricDumpWriting|로 설정 (의 덤프를 출력 장치에 대 한 메모리)를 작성 하는 덤프에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricENC|편집 하며 계속 하기 지원을 나타내는 데 0이 아닌 값으로 설정 합니다. **참고:** 사용자 지정 디버그 엔진이 설정 해서는 안됩니다 또는 0을 항상 설정 해야 합니다.|  
|metricExceptions|로 설정 예외에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricFunctionBP|로 설정 (특정 함수 이름의 호출 될 때 중단 하는 중단점) 명명 된 중단점에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricHitCountBP|로 설정 "지점 hit" 중단점 (특정 횟수 만큼 적중 된 후에 시작 되는 중단점)의 설정에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricJITDebug|Just-in-time 디버깅 (디버거를 시작할 실행 중인 프로세스에서 예외가 발생 하는 경우)에 대 한 지원을 나타냅니다에 0이 아닌 값을 설정 합니다.|  
|metricMemory|사용 되지 않음|  
|metricPortSupplier|구현 된 경우이 포트 공급자 CLSID로 설정 합니다.|  
|metricRegisters|사용 되지 않음|  
|metricSetNextStatement|로 설정 (중간 문 실행을 건너뜁니다)는 다음 문을 설정에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricSuspendThread|로 설정 스레드 실행을 일시 중단 하기 위한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricWarnIfNoSymbols|로 설정 기호가 없는 경우 사용자를 알릴 나타내려면 0이 아닌 합니다.|  
|metricProgramProvider|이 프로그램 공급자 CLSID로 설정 합니다.|  
|metricAlwaysLoadProgramProviderLocal|이를 해야 함을 나타내려면 프로그램 공급자 항상 로드 로컬로 0이 아닌 설정 합니다.|  
|metricEngineCanWatchProcess|이 설정 프로그램 공급자 대신 프로세스 이벤트에 대 한 디버그 엔진에서 감시 나타내려면 0이 아닌 합니다.|  
|metricRemoteDebugging|이 설정 원격 디버깅에 대 한 지원을 나타내는 데 0이 아닌 합니다.|  
|metricEncUseNativeBuilder|편집 하며 계속 하기에 대 한 빌드에 편집 하며 계속 관리자 디버그 엔진 encbuild.dll 사용 해야 함을 나타내려면 0이 아닌 값으로 설정 합니다. **참고:** 사용자 지정 디버그 엔진이 설정 해서는 안됩니다 또는 0을 항상 설정 해야 합니다.|  
|metricLoadUnderWOW64|64 비트 프로세스를 디버깅할 때 wow 디버기 프로세스에 디버그 엔진을 로드 해야는 나타내려면 0이 아닌 값으로 설정 그렇지 않으면 디버그 엔진 (w o w 64에서 실행 되 고)는 Visual Studio 프로세스에서 로드 됩니다.|  
|metricLoadProgramProviderUnderWOW64|이 속성을 설정 해야 함을 나타내려면 프로그램 공급자는 디버거 프로세스에서 로드 된 wow; 64 비트 프로세스를 디버깅 하는 경우에 0이 아닌 그렇지 않으면 Visual Studio 프로세스에서 로드 됩니다.|  
|metricStopOnExceptionCrossingManagedBoundary|이 설정 프로세스에서 관리 되 는/관리 코드 경계를 넘어 처리 되지 않은 예외가 throw 되 면 중지 해야 함을 나타내기 위해 0이 아닌 합니다.|  
|metricAutoSelectPriority|디버그 엔진 (높은 값은 더 높은 우선 순위)의 자동 선택에 대 한 우선 순위를 설정 합니다.|  
|metricAutoSelectIncompatibleList|레지스트리 키를 자동으로 선택에서 무시 되어야 디버그 엔진에 대 한 Guid를 지정 하는 항목이 포함 되도록 합니다. 이러한 항목은 숫자 (0, 1, 2, 및 등)를 문자열로 표현 된 GUID를 사용 합니다.|  
|metricIncompatibleList|이 디버그 엔진과 호환 되지 않는 디버그 엔진에 대 한 Guid를 지정 하는 항목을 포함 하는 레지스트리 키입니다.|  
|metricDisableJITOptimization|이 설정 (관리 코드용) 최적화 적시에 디버깅 하는 동안 않도록 나타내려면 0이 아닌 합니다.|  
  
|식 계산기 속성|설명|  
|-------------------------------------|-----------------|  
|metricEngine|디버그 엔진을 지 원하는 지정 된 식 계산기의 수를 보유 합니다.|  
|metricPreloadModules|이 설정는 모듈을 미리 설치 해야 식 계산기는 프로그램에 대해 시작 될 때 나타내려면 0이 아닌 합니다.|  
|metricThisObjectName|"This" 개체 이름으로 설정 합니다.|  
  
|식 계산기 확장 속성|설명|  
|-----------------------------------------------|-----------------|  
|metricExtensionDll|이 확장명을 지 원하는 dll의 이름입니다.|  
|metricExtensionRegistersSupported|지원 되는 레지스터의 목록입니다.|  
|metricExtensionRegistersEntryPoint|레지스터에 액세스 하기 위한 진입점입니다.|  
|metricExtensionTypesSupported|지원 되는 유형 목록입니다.|  
|metricExtensionTypesEntryPoint|형식에 액세스 하기 위한 진입점입니다.|  
  
|포트 공급자 속성|설명|  
|------------------------------|-----------------|  
|metricPortPickerCLSID|포트 선택 (포트를 선택 하 고 디버깅을 위해 사용할 포트를 추가 하는 대화 상자가 사용자 사용할 수 있음)의 CLSID입니다.|  
|metricDisallowUserEnteredPorts|사용자가 입력 한 포트는 포트 공급자에 추가할 수 없습니다 하면 0이 아니고 (이렇게 하면 포트 선택 대화 상자는 기본적으로 읽기 전용).|  
|metricPidBase|프로세스 Id를 할당할 때 포트 공급자에서 사용 하는 기본 프로세스 ID입니다.|  
  
|미리 정의 된 SP 저장소 유형|설명|  
|-------------------------------|-----------------|  
|storetypeFile|기호는 별도 파일에 저장 됩니다.|  
|storetypeMetadata|기호는 어셈블리에서 메타 데이터로 저장 됩니다.|  
  
|기타 속성|설명|  
|------------------------------|-----------------|  
|metricShowNonUserCode|이 설정 nonuser 코드를 표시 하려면 0이 아닌 합니다.|  
|metricJustMyCodeStepping|이 설정 단계별 실행 사용자 코드에만 발생할 수 있다는 것을 나타내려면 0이 아닌 합니다.|  
|metricCLSID|특정 메트릭 형식의 개체에 대 한 CLSID입니다.|  
|metricName|특정 메트릭 형식의 개체에 대 한 알기 쉬운 이름.|  
|metricLanguage|언어 이름입니다.|  
  
## <a name="registry-locations"></a>레지스트리 위치  
 메트릭을 읽고 특히의 레지스트리에 기록 된 `VisualStudio` 하위 키입니다.  
  
> [!NOTE]
>  대부분의 경우 HKEY_LOCAL_MACHINE 키에 메트릭이 기록 됩니다. 그러나 때로는 HKEY_CURRENT_USER 됩니다 대상 키입니다. Dbgmetric.lib 두 키를 처리합니다. HKEY_CURRENT_USER 검색 메트릭의 가져올 때 가장 먼저 다음 HKEY_LOCAL_MACHINE입니다. 메트릭, 설정 되는 경우 매개 변수는 최상위 사용할 키를 지정 합니다.  
  
 *[레지스트리 키]*\  
  
 `Software`\  
  
 `Microsoft`\  
  
 `VisualStudio`\  
  
 *[버전 루트]*\  
  
 *[메트릭 루트]*\  
  
 *[메트릭 유형]*\  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
|자리 표시자|설명|  
|-----------------|-----------------|  
|*[레지스트리 키]*|`HKEY_CURRENT_USER` 또는 `HKEY_LOCAL_MACHINE`|  
|*[버전 루트]*|Visual Studio 버전 (예를 들어 `7.0`, `7.1`, 또는 `8.0`). 그러나이 루트 수정할 수도 있습니다를 사용 하는 **/rootsuffix** 전환할 **devenv.exe**합니다. VSIP,이 한정자는 일반적으로 **Exp**버전 루트 것, 예를 들어 8.0Exp 때문입니다.|  
|*[메트릭 루트]*|이 역할은 `AD7Metrics` 또는 `AD7Metrics(Debug)`dbgmetric.lib의 디버그 버전 사용 여부에 따라 합니다. **참고:** 디버그 및 릴리스 차이점 있는 경우이 명명 규칙을 따라야 dbgmetric.lib을 사용 하는 여부 레지스트리에 반영 해야 하는 버전입니다.|  
|*[메트릭 유형]*|메트릭 기록할 유형의: `Engine`, `ExpressionEvaluator`, `SymbolProvider`등입니다. 이러한 작업은 모든 정의로 dbgmetric.h 에서처럼 `metricTypeXXXX`여기서 `XXXX` 특정 형식 이름입니다.|  
|*[메트릭을]*|에 대 한 메트릭을 설정 하려면 값을 지정 하는 항목의 이름입니다. 메트릭의 실제 회사 메트릭 형식에 따라 달라 집니다.|  
|*[메트릭 값]*|에 대 한 메트릭을에 할당 된 값입니다. 값 (문자열, 숫자, 등) 있어야 합니다. 형식에 대 한 메트릭을에 따라 달라 집니다.|  
  
> [!NOTE]
>  모든 Guid의 형식으로 저장 되며 `{GUID}`합니다. 예를 들어, `{123D150B-FA18-461C-B218-45B3E4589F9B}`을 입력합니다.  
  
### <a name="debug-engines"></a>디버그 엔진  
 다음은 레지스트리에서 디버그 엔진 메트릭의 구성 합니다. `Engine`디버그 엔진에 대 한 메트릭 유형 이름이 며 해당 *[메트릭 유형]* 위의 레지스트리 하위 트리에 있는 합니다.  
  
 `Engine`\  
  
 *[엔진 guid]*\  
  
 `CLSID` = *[클래스 guid]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 `PortSupplier`\  
  
 `0` = *[포트 공급자 guid]*  
  
 `1` = *[포트 공급자 guid]*  
  
|자리 표시자|설명|  
|-----------------|-----------------|  
|*[엔진 guid]*|디버그 엔진의 GUID입니다.|  
|*[클래스 guid]*|이 디버그 엔진 구현 하는 클래스의 GUID입니다.|  
|*[포트 공급자 guid]*|있는 경우 포트 공급자의 GUID입니다. 많은 디버그 엔진 기본 포트 공급자를 사용 하 여 및 자신의 공급 업체를 지정 하지 마십시오. 이 경우, 하위 키 `PortSupplier` 없습니다.|  
  
### <a name="port-suppliers"></a>포트 공급자  
 다음은 레지스트리에서 포트 공급 업체 메트릭의 구성 합니다. `PortSupplier`포트 공급자에 대 한 메트릭 형식 이름 및 해당 *[메트릭 유형]*합니다.  
  
 `PortSupplier`\  
  
 *[포트 공급자 guid]*\  
  
 `CLSID` = *[클래스 guid]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
|자리 표시자|설명|  
|-----------------|-----------------|  
|*[포트 공급자 guid]*|포트 공급자의 GUID|  
|*[클래스 guid]*|이 포트 공급자를 구현 하는 클래스의 GUID|  
  
### <a name="symbol-providers"></a>기호 공급자  
 다음은 레지스트리에서 기호 공급 업체 메트릭의 구성 합니다. `SymbolProvider`기호 공급자에 대 한 메트릭 유형 이름이 며 해당 *[메트릭 유형]*합니다.  
  
 `SymbolProvider`\  
  
 *[기호 공급자 guid]*\  
  
 `file`\  
  
 `CLSID` = *[클래스 guid]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 `metadata`\  
  
 `CLSID` = *[클래스 guid]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
|자리 표시자|설명|  
|-----------------|-----------------|  
|*[기호 공급자 guid]*|기호 공급자의 GUID|  
|*[클래스 guid]*|이 기호 공급자를 구현 하는 클래스의 GUID|  
  
### <a name="expression-evaluators"></a>식 계산기  
 다음은 레지스트리에서 식 계산기 메트릭의 구성 합니다. `ExpressionEvaluator`식 계산기에 대 한 메트릭 유형 이름이 며 해당 *[메트릭 유형]*합니다.  
  
> [!NOTE]
>  에 대 한 메트릭 유형을 `ExpressionEvaluator` 식 계산기에 대 한 모든 메트릭 변경 내용을 적절 한 식 계산기 메트릭 함수를 통해 진행 될를 가정 하는 대로 dbgmetric.h에 정의 되지 않았습니다 (의 레이아웃은 `ExpressionEvaluator` 다소 하위 키를 복잡 하 고 dbgmetric.lib 내 세부 정보가 숨겨져 있으므로).  
  
 `ExpressionEvaluator`\  
  
 *[언어 guid]*\  
  
 *[공급 업체 guid]*\  
  
 `CLSID` = *[클래스 guid]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 `Engine`\  
  
 `0` = *[디버그 엔진 guid]*  
  
 `1` = *[디버그 엔진 guid]*  
  
|자리 표시자|설명|  
|-----------------|-----------------|  
|*[언어 guid]*|언어의 GUID|  
|*[공급 업체 guid]*|공급 업체의 GUID|  
|*[클래스 guid]*|이 식 계산기를 구현 하는 클래스의 GUID|  
|*[디버그 엔진 guid]*|이 식 계산기를 사용 하는 디버그 엔진의 GUID|  
  
### <a name="expression-evaluator-extensions"></a>식 계산기 확장  
 다음은 식 계산기 확장 메트릭 레지스트리에 구성 합니다. `EEExtensions`이 식에 대 한 메트릭 형식 이름이 계산기 확장 하 고 해당 *[메트릭 유형]*합니다.  
  
 `EEExtensions`\  
  
 *[확장 guid]*\  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
|자리 표시자|설명|  
|-----------------|-----------------|  
|*[확장 guid]*|식 계산기 확장의 GUID|  
  
### <a name="exceptions"></a>예외  
 다음은 레지스트리에서 예외 메트릭 구성 합니다. `Exception`예외에 대 한 메트릭 유형 이름이 며 해당 *[메트릭 유형]*합니다.  
  
 `Exception`\  
  
 *[디버그 엔진 guid]*\  
  
 *[예외 유형]*\  
  
 *[예외]*\  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[예외]*\  
  
 *[메트릭을] = [메트릭 값]*  
  
 *[메트릭을] = [메트릭 값]*  
  
|자리 표시자|설명|  
|-----------------|-----------------|  
|*[디버그 엔진 guid]*|지 원하는 예외 디버그 엔진의 GUID입니다.|  
|*[예외 유형]*|예외 처리 될 수 있는 클래스를 식별 하는 하위 키에 대 한 일반 제목입니다. 일반적인 이름은 **c + + 예외**, **Win32 예외**, **공용 언어 런타임 예외**, 및 **네이티브 런타임 검사**합니다. 이러한 이름은 특정 클래스의 사용자에 게 예외를 식별 하도 사용 됩니다.|  
|*[예외]*|예외에 대 한 이름을: 예를 들어 **_com_error** 또는 **Control-break**합니다. 이러한 이름은 사용자에 게 특정 예외를 식별 하도 사용 됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 이러한 파일은 %programfiles%\microsoft는 [!INCLUDE[vs_dev10_ext](../../../extensibility/debugger/reference/includes/vs_dev10_ext_md.md)] SDK 설치 디렉터리 (기본적으로 *[드라이브]*files\microsoft Visual Studio 2010 SDK\\).  
  
 헤더: includes\dbgmetric.h  
  
 라이브러리: libs\ad2de.lib, libs\dbgmetric.lib  
  
## <a name="see-also"></a>참고 항목  
 [API 참조](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)
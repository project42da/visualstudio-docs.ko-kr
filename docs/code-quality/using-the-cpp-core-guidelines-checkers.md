---
title: C + + 코어 지침 검사기를 사용 하 여
ms.date: 11/04/2016
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
dev_langs:
- CPP
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.openlocfilehash: f8b031fc1251ad06fdba154c086696337e552445
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747406"
---
# <a name="using-the-c-core-guidelines-checkers"></a>C + + 코어 지침 검사기를 사용 하 여
C + + 코어 지침은 휴대용 집합이 지침, 규칙 및 c + +의 c + + 전문가 디자이너에서 만든 코딩 하는 방법에 대 한 모범 사례입니다. 현재 visual Studio c + +에 대 한 코드 분석 도구는의 일부로 이러한 규칙의 하위 집합을 지원합니다. 코어 지침 검사기는 Visual Studio 2017에 기본적으로 설치 및는 [Visual Studio 2015 용 NuGet 패키지로 사용할 수 있는](#vs2015_corecheck)합니다.

## <a name="the-c-core-guidelines-project"></a>C + + 코어 지침 프로젝트
 Bjarne stroustrup이 작성 하 고 다른 사용자에 의해 만들어진 c + + 코어 지침 안전 하 고 효과적으로 최신 c + +를 사용 하는 데는 합니다. 지침 정적 형식 안전성 및 리소스 보안을 강조합니다. 이들은 제거 하거나 언어에서의 오류 발생률 가장 부분을 최소화 하는 방법을 식별 하며 신뢰할 수 있는 방식으로 코드를 더 간단 하 게 하는 방법과 뛰어날 것이 좋습니다. 이러한 지침은 표준 c + + Foundation에서 유지 관리 됩니다. 자세한 내용은 설명서를 참조 [c + + 코어 지침](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines), c + + 코어 지침 문서 프로젝트 파일에 액세스 하 고 [GitHub](https://github.com/isocpp/CppCoreGuidelines)합니다.

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>코드 분석에서 c + + 코어 확인 지침을 사용 하도록 설정
 선택 하 여 프로젝트에서 코드 분석을 사용할 수 있습니다는 **빌드에 코드 분석 사용** 확인란을 선택은 **코드 분석** 의 섹션은 **속성 페이지** 대화 상자 프로젝트입니다.

 ![코드 분석 일반 설정에 대 한 속성 페이지](../code-quality/media/cppcorecheck_codeanalysis_general.png)

 C + + 코어 확인 규칙은 코드 분석을 사용 하는 실행 하는 기본 규칙 집합에 대 한 확장입니다. C + + 코어 확인 규칙은 개발 중인 이기 때문에 몇 가지 규칙은 잘 구성 및 일부 모든 코드에서 사용할 준비가 되지 않을 수 있지만 여전히 되지 않는 정보를 제공 합니다. 규칙은 두 개의 그룹으로 나뉩니다: 해제 한 후 실험적. 프로젝트에 대 한 속성에서 해제 또는 실험적 규칙을 실행할 것인지를 선택할 수 있습니다.

 ![코드 분석 확장 설정에 대 한 속성 페이지](../code-quality/media/cppcorecheck_codeanalysis_extensions.png)

 C + + 코어 확인 규칙 집합을 사용 하지 않도록 설정 하거나, 엽니다는 **속성 페이지** 프로젝트에 대 한 대화 상자. 아래 **구성 속성**를 확장 하 고 **코드 분석**, **확장**합니다. 옆에 드롭다운 제어 **(릴리스됨)를 확인 c + + 코어를 사용 하도록 설정** 또는 **사용 c + + 코어 확인 (합니다 실험적)**, 선택 **예** 또는 **아니요**합니다. 선택 **확인** 또는 **적용** 변경 내용을 저장 합니다.

## <a name="examples"></a>예제
 C + + 코어 확인 규칙을 찾을 수 있는 문제 중 일부의 예는 다음과 같습니다.

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

 이 예제는 c + + 코어 확인 규칙을 찾을 수 있는 경고 중 몇 가지 보여 줍니다.

-   규칙 Type.5 C26494: 항상 개체를 초기화 합니다.

-   규칙 Bounds.3 C26485: 배열 포인터 decay 없습니다.

-   규칙 Bounds.1 C26481: 포인터 산술 연산을 사용 하지 마십시오. 대신 `span`를 사용하세요.

 C + + 코어 확인 코드 분석 규칙 설치 되 고이 코드를 컴파일할 때 사용 하도록 설정, 처음 두 가지 경고 출력을 있더라도 세 번째 표시 되지 않습니다. 예제 코드에서 빌드 출력은 다음과 같습니다.

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C + + 코어 지침 향상 하 고 안전한 코드를 작성할 수 있도록 하는 것입니다. 그러나 규칙 또는 프로필 안를 적용할 수 없는 인스턴스를 설정한 경우 쉽습니다를 표시 하지 않는 코드에서 직접 합니다. 사용할 수는 `gsl::suppress` 특성을 검색 하 고 다음 코드 블록에서 규칙 위반을 보고에서 c + + 코어 확인을 유지 합니다. 특정 규칙을 억제 개별 문을 표시할 수 있습니다. 작성 하 여 전체 범위 프로 파일을 억제도 `[[gsl::suppress(bounds)]]` 특정 규칙 번호를 포함 하지 않고 있습니다.

## <a name="supported-rule-sets"></a>지원 되는 규칙 집합
C + + 코어 지침 검사기에 새 규칙 추가 되 면 기존 코드에 대 한 생성 되는 경고 수가 증가할 수 있습니다. 사용 하도록 설정 하는 규칙의 종류를 필터링 하려면 미리 정의 된 규칙 집합을 사용할 수 있습니다.
대부분의 규칙에 대 한 참조 항목은 [Visual Studio c + + 코어 확인 참조](code-analysis-for-cpp-corecheck.md)합니다.

Visual Studio 2017 15.3 버전을 기준으로 지원 되는 규칙 집합은 됩니다.
  - **소유자 포인터 규칙** 적용 [리소스 관리 소유자에 게 관련 확인<T> c + + 코어 지침에서](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)합니다.

  - **Const 규칙** 적용 [c + + 코어 지침에서 const 관련 검사](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)합니다.

  - **원시 포인터 규칙** 적용 [리소스 관리는 c + + 코어 지침에서 원시 관련이 포인터 검사](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)합니다.

  - **고유 포인터 규칙** 적용 [리소스 관리는 c + + 코어 지침에서 형식과 고유한 포인터 의미 체계와 관련 된 검사](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)합니다.

  - **규칙 범위** 적용는 [c + + 코어 지침의 프로필 제한](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)합니다.

  - **형식 규칙** 적용는 [c + + 코어 지침의 프로필 입력](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)합니다.

  **Visual Studio 2017 버전 15.5**:
  - **규칙 클래스** 특별 한 메서드 및 가상 사양의 적절 한 사용에 초점을 맞춘 몇 가지 규칙이 있습니다. 이 검사에 대 한 권장의 하위 집합 [클래스 및 클래스 계층 구조](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)합니다.
  - **동시성 규칙** 가드 잘못 선언 된 개체를 catch 하는 단일 규칙입니다. 자세한 내용은 참조 [동시 성과 관련 지침](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency)합니다.
  - **선언 규칙** 몇 가지 규칙에서는 [지침 인터페이스](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces) 중점을 어떻게 전역 변수는 선언 됩니다.
  - **규칙 함수** 단기간에 사용 되는 두 가지 검사는 `noexcept` 지정자입니다. 이 대 한 지침의 일부인 [함수 디자인 및 구현 지우기](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)합니다.
  - **공유 포인터 규칙** 의 일부로 [리소스 관리](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource) 몇 가지 규칙 어떻게 공유 포인터에 대 한 특정 함수에 전달 된 또는 로컬로 사용 되는 추가 지침이 적용 합니다.
  - **스타일 규칙** 하나의 간단 하지만 중요 한 검사를 사용 하 여 금지 [goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)합니다. 이 코딩 스타일과 식과 c + +에서 문을 사용 하 여의 개선을 첫 번째 단계입니다.

  **Visual Studio 2017 버전 15.6**:
  - **산술 규칙** 산술을 검색 하는 규칙 [오버플로](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow), [작업 서명 unsigned](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned) 및 [조작 비트](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)합니다.


 하나 또는 몇 가지 그룹으로 경고를 제한할 수 있습니다. **네이티브 최소** 및 **네이티브 권장** 규칙 집합 다른 PREfast 확인 뿐 아니라 c + + 코어 확인 규칙을 포함 합니다. 사용 가능한 프로젝트 속성 대화 상자를 열고, 규칙 집합을 보려면 선택 **코드 Analysis\General**, 열에 있는 드롭다운에서 **규칙 집합** 콤보 상자 및 선택 **여러 규칙 집합 선택** . Visual Studio에서 규칙 집합을 사용 하는 방법에 대 한 자세한 내용은 참조 [코드 분석 규칙 그룹화를 사용 하 여 규칙 집합](using-rule-sets-to-group-code-analysis-rules.md)합니다.

## <a name="macros"></a>매크로
 C + + 코어 지침 검사기를 코드에서 경고의 전체 범주를 표시 하지 않는 쉽게 해 주는 매크로 정의 하는 헤더 파일에 포함 되어 있습니다.

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

이러한 매크로 규칙 집합에 해당 하 고 경고 번호를 공백으로 구분 된 목록으로 확장 합니다. 적절 한 pragma 구문을 사용 하 여 코드 섹션 또는 프로젝트에 대 한 흥미로운 유효한 규칙 집합을 구성할 수 있습니다. 다음 예제에서는 상수 한정자 누락에 대 한 코드 분석 경고 합니다.

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>특성
 Microsoft Visual c + + 컴파일러는 특성을 표시 하지 않는 GSL에 대 한 제한 된 지원 합니다. 식 및 블록 문에서 함수 내부에서 경고를 표시 하지 않는 데 사용할 수 있습니다.

```cpp
// Supress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Supress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppressing-analysis-by-using-command-line-options"></a>명령줄 옵션을 사용 하 여 분석을 억제 합니다.
 #Pragmas, 대신를 프로젝트 또는 단일 파일에 대 한 경고를 표시 하지 않는 파일의 속성 페이지의 명령줄 옵션을 사용할 수 있습니다. 예를 들어, 경고를 사용 하지 않도록 설정 하는 파일에 대 한 26400:

 1) 파일을 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**

 2) 선택 **속성 | C / C + + | 명령줄**

 3) 에 **추가 옵션** 창 추가 `/wd26400`합니다.

 명령줄 옵션을 사용 하 여 일시적으로 파일에 대 한 모든 코드 분석을 사용 하지 않도록 지정 하 여 `/analyze-`합니다. 경고가 생성 *D9025 재정의 '/analyze'와 ' /analyze-'* 는 다시 나중에 코드 분석을 사용 하도록 사용자에 게 알립니다.

 ## <a name="corecheck_per_file"></a> 특정 프로젝트 파일에 대해 c + + 코어 지침 검사기를 사용 하도록 설정
경우에 따라 수행 초점을 맞춘 코드 분석 하 고 여전히 Visual Studio IDE를 사용 하 여에 유용할 수 있습니다. 빌드 시간을 저장 하 고 필터 결과를 보다 쉽게 대규모 프로젝트의 다음 샘플 시나리오를 사용할 수 있습니다.

1.  명령 셸에서 설정는 `esp.extension` 및 `esp.annotationbuildlevel` 환경 변수입니다.
2.  이러한 변수를 상속 하도록 명령 셸에서 Visual Studio를 시작 합니다.
3.  프로젝트를 로드 하 고 해당 속성을 엽니다.
4.  코드 분석을 활성화 하 고 적절 한 규칙 집합 선택 하지만 코드 분석 확장을 사용 하지 마십시오.
5.  C + + 코어 지침 검사기와 함께 분석 하 고 해당 속성을 엽니다 하려는 파일이 있는 위치로 이동 합니다.
6.  선택 **C / C + + \Command 선 옵션** 추가 `/analyze:plugin EspXEngine.dll`
7.  미리 컴파일된 헤더 사용 안 함 (**C / C + + 헤더 \Precompiled**). 미리 컴파일된 헤더 (PCH;)에서 해당 내부 정보를 읽는 확장 엔진 시도할 수 있으므로이 방법은 필요 PCH 기본 프로젝트 옵션으로 컴파일된, 호환 되지 않습니다.
8.  프로젝트를 다시 빌드합니다. 모든 파일에는 일반적인 PREFast 검사를 실행 해야 합니다. 기본적으로 c + + 코어 지침 검사기를 사용할 수 없으므로 사용 하도록 구성 하는 파일에만 실행 해야 합니다.

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>Visual Studio 외부에서 c + + 코어 지침 검사기를 사용 하는 방법
자동화 된 빌드에서 c + + 코어 지침 검사를 사용할 수 있습니다.

### <a name="msbuild"></a>MSBuild
 네이티브 코드 분석 검사기 (PREfast)를 사용 하는 사용자 지정 대상 파일에서 MSBuild 환경에 통합 됩니다. 프로젝트 속성을 사용 하 여 사용 하도록 설정 하 고 c + + 코어 지침 검사기 (따르므로 PREfast)를 추가할 수 있습니다.:

 ```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>¬¬
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```
Microsoft.Cpp.targets 파일을 가져오기 전에 이러한 속성을 추가 하 고 있는지 확인 합니다. 특정 규칙 집합 선택 또는 하거나 다른 PREfast 검사를 포함 하는 기본 규칙 집합을 사용 하 여 사용자 지정 규칙 집합을 만들 수 있습니다.

와 동일한 방식으로 사용 하 여 지정 된 파일에 대해서만 c + + 코어 검사기를 실행할 수 있습니다 [앞에서 설명한](#corecheck_per_file), 하지만 MSBuild 파일을 사용 합니다. 환경 변수를 사용 하 여 설정할 수 있습니다는 `BuildMacro` 항목:

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>CppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

프로젝트 파일을 수정 하려는 하지 않는 경우 명령줄에서 속성을 전달할 수 있습니다.

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>비 MSBuild 프로젝트
MSBuild에 의존 하지 않고 빌드 시스템을 사용 하는 경우, 검사를 계속 실행할 수 있습니다 하지만 코드 분석 엔진 구성의 일부 내부에 친숙 해지기 필요 합니다. 나중에 지원 되는 데 이러한 내부 보장 되지 않습니다.

몇 가지 환경 변수를 설정 하 고 컴파일러에 대 한 적절 한 명령줄 옵션을 사용 해야 합니다. 컴파일러에 대 한 특정 경로 대 한 검색, 디렉터리 등을 포함 하지 않아도 되도록 "네이티브 도구 명령 프롬프트" 환경에서 작동 하는 것이 좋습니다.

1.  **환경 변수**
  - `set esp.extensions=cppcorecheck.dll` C + + 코어 지침 모듈을 로드 하려면 엔진을 인지를 나타냅니다.
  - `set esp.annotationbuildlevel=ignore` SAL 주석 처리 하는 논리를 해제 합니다. 주석은 c + + 코어 지침 검사에서 코드 분석에 영향을 주지 아직 처리 시간이 (경우에 따라 자세한 시간). 이 설정은 선택 사항 이지만 권장 사항임입니다.
  - `set caexcludepath=%include%` 표준 헤더에 대해 발생 하는 경고를 해제 하는 것이 좋습니다. 경로 예를 들어 프로젝트에서 일반적인 헤더를 여기에 경로 더 추가할 수 있습니다.
2.  **명령줄 옵션**
  - `/analyze`  코드 분석을 활성화 (/analyze 함께 사용 하는 것이 좋습니다:만 및 /analyze: quiet).
  - `/analyze:plugin EspXEngine.dll` 이 옵션은 PREfast에 코드 분석 확장 엔진을 로드합니다. 이 엔진을 c + + 코어 지침 검사기 로드 합니다.



## <a name="use-the-guideline-support-library"></a>안내선 지원 라이브러리를 사용 하 여
 안내선 지원 라이브러리는 코어 지침을 따라 수 있도록 설계 되었습니다. GSL 구문 오류가 발생 하기 쉬운 더 안전한 대체 방법을를 교체할 수는 정의 포함 합니다. 예를 들어 바꿀 수 있습니다는 `T*, length` 쌍의 매개 변수는 `span<T>` 유형입니다. 제공 되는 GSL [ http://www.nuget.org/packages/Microsoft.Gsl ](http://www.nuget.org/packages/Microsoft.Gsl)합니다. 라이브러리는 오픈 소스는 원본을 보려면, 메모 추가 하거나 기여할 수 있습니다. 프로젝트를 찾을 수 있습니다 [ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)합니다.

 ## <a name="vs2015_corecheck"></a> Visual Studio 2015 프로젝트에서 c + + 코어 확인 지침을 사용 하 여
  Visual Studio 2015를 사용 하는 경우 c + + 코어 확인 코드 분석 규칙 집합 기본적으로 설치 되지 않습니다. Visual Studio 2015에서 c + + 코어 확인 코드 분석 도구를 사용 하려면 먼저 몇 가지 추가 단계를 수행 해야 합니다. Microsoft는 Nuget 패키지를 사용 하 여 Visual Studio 2015 프로젝트에 대 한 지원을 제공 합니다. 패키지의 이름은 Microsoft.CppCoreCheck, 및에서 구할 수 [ http://www.nuget.org/packages/Microsoft.CppCoreCheck ](http://www.nuget.org/packages/Microsoft.CppCoreCheck)합니다. 이 패키지 있으면 이상 Visual Studio 2015 업데이트 1과 함께 설치 됩니다.

 또한 패키지는 머리글만 지침 지원 라이브러리 (GSL)를 종속성으로 다른 패키지를 설치합니다. GSL github에 있습니다. [ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)합니다.

 코드 분석 규칙은 로드 하는 방식 때문에 Visual Studio 2015 내에서 확인 하려는 각 c + + 프로젝트에 Microsoft.CppCoreCheck NuGet 패키지를 설치 해야 합니다.

#### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>Microsoft.CppCoreCheck 패키지 Visual Studio 2015에서 프로젝트를 추가 하려면

1.  **솔루션 탐색기**에 패키지를 추가 하려는 솔루션에서 프로젝트의 상황에 맞는 메뉴를 열고를 마우스 오른쪽 단추로 클릭 합니다. 선택 **NuGet 패키지 관리** 열려는 **NuGet 패키지 관리자**합니다.

2.  에 **NuGet 패키지 관리자** 창, Microsoft.CppCoreCheck 검색 합니다.

     ![Nuget 패키지 관리자 창 CppCoreCheck 패키지를 보여 줍니다.](../code-quality/media/cppcorecheck_nuget_window.png)

3.  Microsoft.CppCoreCheck 패키지를 선택한 다음 선택에서 **설치** 프로젝트에 규칙을 추가 하려면 단추입니다.

 추가 MSBuild를 추가 하는 NuGet 패키지 *.targets* 파일을 프로젝트에 대해 코드 분석을 사용 하도록 설정 하면 호출 되는 프로젝트입니다. 이 *.targets* 파일 Visual Studio 코드 분석 도구에 대 한 추가 확장으로 c + + 코어 확인 규칙에 추가 합니다. 패키지가 설치 될 때 해제 한 후 실험적 규칙을 사용 하지 않도록 설정 하거나 설정 하려면 속성 페이지 대화 상자를 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목
[Visual Studio c + + 코어 검사 참조](code-analysis-for-cpp-corecheck.md)합니다.


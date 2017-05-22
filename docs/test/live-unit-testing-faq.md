---
title: Live Unit Testing FAQ | Microsoft Docs
ms.date: 2017-03-13
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing FAQ
ms.assetid: 61baf3bb-646f-4c5a-b7c0-a6bdff68f21c
author: rpetrusha
ms.author: ronpet
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: c9df048a49580f3526b48e29041ef3758722ed27
ms.openlocfilehash: 08677472bc13d58d9ab0b42b856955f8434089e4
ms.contentlocale: ko-kr
ms.lasthandoff: 05/03/2017

---
# <a name="live-unit-testing-frequently-asked-questions"></a>Live Unit Testing 질문과 대답

## <a name="does-live-unit-testing-work-with-net-core"></a>Live Unit Testing은 .NET Core와 호환되나요?  

**대답:**

현재 Live Unit Testing은 .NET Core와 호환되지 않습니다. 나중에 이 지원을 추가하려고 합니다. 

## <a name="why-doesnt-live-unit-testing-work-when-i-turn-it-on"></a>Live Unit Testing을 설정해도 작동하지 않는 이유는 무엇인가요? 

**대답:** 

**출력 창**(Live Unit Testing 드롭다운을 선택한 경우)은 Live Unit Testing이 작동하지 않는 이유를 설명합니다. 다음과 같은 이유로 Live Unit Testing이 작동하지 않을 수 있습니다. 

- 솔루션의 프로젝트에서 참조하는 NuGet 패키지가 복원되지 않은 경우 Live Unit Testing은 작동하지 않습니다. Live Unit Testing을 설정하기 전에 솔루션을 명시적으로 빌드하거나 솔루션의 NuGet 패키지를 복원하면 이 문제가 해결되어야 합니다. 

- 프로젝트에서 MSTest 기반 테스트를 사용하는 경우 `Microsoft.VisualStudio.QualityTools.UnitTestFramework`에 대한 참조를 제거하고 최신 MSTest NuGet 패키지, `MSTest.TestAdapter`(1.1.4-미리 보기의 최소 버전 필요) 및 `MSTest.TestFramework`(1.0.5-미리 보기의 최소 버전 필요)에 대한 참조를 추가해야 합니다. 자세한 내용은 [Visual Studio 2017 Enterprise Edition에서 Live Unit Testing 사용](live-unit-testing.md#supported-test-frameworks) 항목의 "지원되는 테스트 프레임워크" 섹션을 참조하세요.
 
- 솔루션에 있는 하나 이상의 프로젝트에는 NuGet 참조 또는 xUnit, NUnit 또는 MSTest 테스트 프레임워크에 대한 직접 참조가 있어야 합니다. 이 프로젝트도 해당하는 Visual Studio 테스트 어댑터 NuGet 패키지를 참조해야 합니다. Visual Studio 테스트 어댑터는 `.runsettings` 파일을 통해 참조될 수도 있습니다. `.runsettings` 파일에는 다음과 같은 항목이 있어야 합니다. 

   ```xml
    <RunSettings> 
       <RunConfiguration>
          <TestAdaptersPaths>path-to-your-test-adapter</TestAdaptersPaths>
       </RunConfiguration> 
    </RunSettings> 
   ``` 

## <a name="why-does-live-unit-testing-show-incorrect-coverage-after-you-upgrade-the-test-adapter-referenced-in-your-visual-studio-projects-to-the-supported-version"></a>Visual Studio 프로젝트에서 참조되는 테스트 어댑터를 지원되는 버전으로 업그레이드한 후 Live Unit Testing에 잘못된 범위가 표시되는 이유는 무엇인가요?

**대답:**

- 솔루션의 여러 프로젝트에서 NuGet 테스트 어댑터 패키지를 참조하는 경우 각 프로젝트를 지원되는 버전으로 업그레이드해야 합니다.

- 또한 테스트 어댑터 패키지에서 가져온 MSBuild .props 파일이 올바르게 업데이트되었는지 확인합니다. 다음과 같이 일반적으로 프로젝트 파일의 위쪽에 있는 가져오기의 NuGet 패키지 버전/경로를 확인합니다.

   ```xml
    <Import Project="..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props" Condition="Exists('..\packages\xunit.runner.visualstudio.2.2.0\build\net20\xunit.runner.visualstudio.props')" />
   ```

## <a name="can-i-customize-my-live-unit-testing-builds"></a>내 Live Unit Testing 빌드를 사용자 지정할 수 있나요? 

**대답:**

"일반적인" 계측되지 않은 빌드에 필요하지 않은 계측(Live Unit Testing)을 위해 빌드하는 사용자 지정 단계가 솔루션에 필요한 경우 프로젝트 또는 대상 파일에 코드를 추가하여 `BuildingForLiveUnitTesting` 속성에 대해 확인하고 사용자 지정 사전/사후 빌드 단계를 수행할 수 있습니다. 또한 특정 빌드 단계(예: 패키지 게시 또는 생성)을 제거하거나 빌드 단계(예: 필수 구성 요소 복사)를 이 프로젝트 속성을 기반으로 하는 Live Unit Testing 빌드에 추가할 수 있습니다. 이렇게 하더라도 일반적인 빌드를 변경하지 않으며 Live Unit Testing 빌드에만 영향을 줍니다. 

예를 들어 일반적인 빌드 중에 NuGet 패키지를 생성하는 대상이 있을 수 있습니다. 아마도 편집을 모두 완료한 후에 NuGet 패키지를 생성하려고 하지는 않을 것입니다. 따라서 다음과 같은 작업을 실행하여 Live Unit Testing 빌드에서 해당 대상을 해제할 수 있습니다.   

```xml
<Target Name="GenerateNuGetPackages" BeforeTargets="AfterBuild" Condition="'$(BuildingForLiveUnitTesting)' != 'true'"> 
    <Exec Command='"$(MSBuildThisFileDirectory)..\tools\GenPac" '/> 
</Target> 
```

## <a name="error-messages-with-ltoutputpathgt-or-ltoutdirgt"></a>&lt;OutputPath&gt; 또는 &lt;OutDir&gt;을 포함한 오류 메시지

**Live Unit Testing이 내 솔루션을 빌드하려고 하는 경우 다음 오류가 표시되는 이유는 무엇인가요? “무조건 `<OutputPath>` 또는 `<OutDir>`으로 설정된 것으로 보입니다. Live Unit Testing은 출력 어셈블리에서 테스트를 실행하지 않습니다.”**

**대답:**

솔루션에 대한 빌드 프로세스가 무조건 `<OutputPath>` 또는 `<OutDir>`를 재정의하는 경우에 발생할 수 있습니다. 따라서 `<BaseOutputPath>`의 하위 디렉터리가 아닙니다. 이러한 경우에 빌드 아티팩트가 `<BaseOutputPath>` 아래의 폴더에 배치되도록 이러한 항목을 재정의하기 때문에 Live Unit Testing은 작동하지 않습니다. 빌드 아티팩트를 일반적인 빌드에 배치하는 위치를 재정의해야 하는 경우 `<BaseOutputPath>`에 따라 조건부로 `<OutputPath>`를 재정의합니다. 

예를 들어 다음과 같이 빌드가 `<OutputPath>`를 재정의하는 경우: 

```xml 
<Project> 
  <PropertyGroup> 
    <OutputPath>$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)</OutputPath> 
  </PropertyGroup> 
</Project> 
```

그러면 다음 항목으로 바꿀 수 있습니다. 

```xml 
<Project> 
  <PropertyGroup> 
    <BaseOutputPath Condition="'$(BaseOutputPath)' == ''">$(SolutionDir)Artifacts\$(Configuration)\bin\$(MSBuildProjectName)\</BaseOutputPath> 
    <OutputPath Condition="'$(OutputPath)' == ''">$(BaseOutputPath)</OutputPath> 
  </PropertyGroup> 
</Project> 
```
 
그렇게 하면 `<OutputPath>`은 `<BaseOutputPath>` 폴더 내에 위치합니다. 
 
`<OutDir>`를 빌드 프로세스에서 직접 재정의하지 않습니다. 특정 위치에 빌드 아티팩트를 배치하는 대신 `<OutputPath>`를 재정의합니다.
  
## <a name="setting-the-location-of-live-unit-testing-build-artifacts"></a>Live Unit Testing 빌드 아티팩트의 위치 설정

**Live Unit Testing 빌드 아티팩트를 원하는 `.vs` 폴더의 기본 위치 대신 특정 위치로 이동하려고 합니다. 어떻게 변경할 수 있나요?**
 
**대답:**

`LiveUnitTesting_BuildRoot` 사용자 수준 환경 변수를 Live Unit Testing 빌드 아티팩트를 배치하려는 경로로 설정합니다.  

## <a name="how-is-running-tests-from-test-explorer-window-different-from-running-tests-in-live-unit-testing"></a>Test Explorer 창에서 테스트를 실행하는 것과 Live Unit Testing에서 테스트를 실행하는 것은 어떻게 다른가요? 

**대답:**

다음과 같은 몇 가지 차이점이 있습니다. 

- Test Explorer 창에서 테스트를 실행 또는 디버깅하면 일반 이진 파일을 실행합니다. 반면 Live Unit Testing은 계측된 이진 파일을 실행합니다. 계측된 이진 파일을 디버그하려는 경우 테스트 메서드에서 [Debugger.Launch](xref:System.Diagnostics.Debugger.Launch) 메서드 호출을 추가하면 해당 메서드가 실행될 때(Live Unit Testing에서 실행하는 경우 포함)마다 디버거가 시작되고 계측된 이진 파일을 연결하고 디버그할 수 있습니다. 그러나 계측이 대부분의 사용자 시나리오에 대해 투명하고 계측된 이진 파일을 디버그할 필요가 없는 것이 좋습니다. 

- Live Unit Testing은 테스트를 실행하기 위해 새 응용 프로그램 도메인을 만들지 않지만 Test Explorer 창에서 실행되는 테스트는 새 응용 프로그램 도메인을 만듭니다. 

- Live Unit Testing은 각 테스트 어셈블리에서 순차적으로 테스트를 실행하는 반면 Test Explorer 창에서 여러 테스트를 실행하고 **동시에 테스트 실행** 단추를 선택한 경우 테스트가 동시에 실행됩니다. 

- Live Unit Testing에서 테스트를 검색 및 실행하면 `TestPlatform`의 버전 2를 사용하는 반면 Test Explorer 창은 버전 1을 사용합니다. 그러나 대부분의 경우에는 차이를 알 수 없습니다.  

- 현재 Test Explorer는 기본적으로 STA(단일 스레드 아파트)에서 실행되는 반면 Live Unit Testing은 MTA(다중 스레드 아파트)에서 테스트를 실행합니다. Live Unit Testing의 STA에서 MSTest 테스트를 실행하려면 `MSTest.STAExtensions 1.0.3-beta`에서 찾을 수 있는 `<STATestMethod>` 또는 `<STATestClass>` 특성을 사용하여 NuGet 패키지 테스트 메서드 또는 포함한 클래스를 데코레이트합니다. NUnit의 경우 테스트 메서드를 `<RequiresThread(ApartmentState.STA)>` 특성을 사용하여 데코레이트하고 xUnit의 경우 `<STAFact>` 특성을 사용하여 데코레이트합니다.
 
## <a name="how-do-i-exclude-tests-from-participating-in-live-unit-testing"></a>Live Unit Testing에 참여하지 않도록 테스트를 제외하려면 어떻게 하나요?

**대답:**

사용자 지정 설정은 [Visual Studio 2017 Enterprise Edition에서 Live Unit Testing 사용](live-unit-testing.md#including-and-excluding-test-projects-and-test-methods) 항목의 "테스트 프로젝트 및 테스트 메서드 포함 및 제외" 섹션을 참조하세요. 이러한 기능은 특정 편집 세션에 특정 집합의 테스트를 실행하거나 고유한 개인 기본 설정을 유지하려는 경우에 매우 유용합니다.
  
솔루션 지정 설정은 Live Unit Testing에서 계측한 메서드, 속성, 클래스 또는 구조를 제외하여 프로그래밍 방식으로 <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute?displayProperty=fullName> 특성을 적용할 수 있습니다. 또한 프로젝트 파일에서 `<ExcludeFromCodeCoverage>` 속성을 `true`로 설정하여 전체 프로젝트를 계측하지 않도록 제외할 수도 있습니다. Live Unit Testing은 계측되지 않는 테스트를 실행하지만 해당 검사를 시각화할 수는 없습니다.

`Microsoft.CodeAnalysis.LiveUnitTesting.Runtime`이 현재 응용 프로그램 도메인에 로드되고 그에 따라 테스트를 사용하지 않도록 설정하는지 여부를 확인할 수도 있습니다. 예를 들어 xUnit을 사용하여 다음과 같은 작업이 가능합니다.

```cs
[ExcludeFromCodeCoverage]
public class SkipLiveFactAttribute : FactAttribute
{
   private static bool s_lutRuntimeLoaded = AppDomain.CurrentDomain.GetAssemblies().Any(a => a.GetName().Name == 
                                            "Microsoft.CodeAnalysis.LiveUnitTesting.Runtime");
   public override string Skip => s_lutRuntimeLoaded ? "Test excluded from Live Unit Testing" : "";
}

public class Class1
{
   [SkipLiveFact]
   public void F()
   {
      Assert.True(true);
   }
}
```

## <a name="why-are-win32-pe-headers-different-in-instrumented-assemblies-built-by-live-unit-testing"></a>Win32 PE 헤더가 Live Unit testing에서 빌드한 계측된 어셈블리와 다른 이유는 무엇인가요? 

**대답:**

알려진 버그로 인해 Live Unit testing 빌드가 다음 Win32 PE 헤더 데이터를 포함하는 데 실패할 수 있습니다. 

- 파일 버전(코드에서 @System.Reflection.AssemblyFileVersionAttribute로 지정됨) 

- Win32 아이콘(명령줄에서 `/win32icon:`로 지정됨) 

- Win32 매니페스트(명령줄에서 `/win32manifest:`로 지정됨) 

이러한 값을 사용하는 테스트를 Live Unit testing에서 실행하는 경우 실패할 수 있습니다.

## <a name="why-does-live-unit-testing-keep-building-my-solution-all-the-time-even-if-i-am-not-making-any-edits"></a>Live Unit testing이 편집하지 않은 경우에도 항상 내 솔루션을 빌드하는 이유는 무엇인가요? 

**대답:**

솔루션의 빌드 프로세스가 솔루션 자체의 일부인 소스 코드를 생성하고 빌드 대상 파일에 적절한 입력 및 출력이 지정되지 않은 경우에 발생할 수 있습니다. 대상에는 입력 및 출력의 목록이 지정되었으므로 MSBuild는 적절한 최신 검사를 수행하고 새 빌드가 필요한지 여부를 확인할 수 있습니다. 

Live Unit Testing은 원본 파일이 변경되었음을 감지할 때마다 빌드하기 시작합니다. 솔루션의 빌드가 원본 파일을 생성하기 때문에 Live Unit Testing은 빌드 무한 루프로 진행됩니다. 그러나 (이전 빌드에서 새로 생성된 원본 파일을 감지한 후에) Live Unit Testing에서 두 번째 빌드를 시작하는 시기를 대상의 입력 및 출력이 확인하면 입력 및 출력 검사는 모든 항목이 최신 상태라고 표시하기 때문에 루프를 중단시킵니다.   

## <a name="how-does-live-unit-testing-work-with-the-lightweight-solution-load-feature"></a>Live Unit testing은 Lightweight 솔루션 로드 기능과 어떻게 호환되나요? 

**대답:**

솔루션에서 모든 프로젝트가 아직 로드되지 않은 경우 Live Unit testing은 현재 Lightweight 솔루션 로드 기능과 호환되지 않습니다. 이러한 시나리오에서는 잘못된 검사 정보를 얻을 수 있습니다.
 
## <a name="why-does-live-unit-testing-does-not-capture-coverage-from-a-new-process-created-by-a-test"></a>Live Unit Testing이 테스트에서 만든 새 프로세스의 검사를 캡처하지 않는 이유는 무엇인가요?
 
**대답:**

Visual Studio 2017 릴리스에서 수정하지 못한 알려진 문제입니다. Visual Studio 2017의 후속 업데이트에서 수정해야 합니다. 

## <a name="why-does-nothing-happen-after-i-include-or-exclude-tests-from-the-live-test-set"></a>라이브 테스트 집합에서 테스트를 포함하거나 제외한 후에 아무 것도 발생하지 않은 이유는 무엇인가요? 

**대답:**

이것은 알려진 문제입니다. 이를 해결하기 위해 테스트를 포함하거나 제외한 후에 모든 파일을 편집해야 합니다.  

## <a name="live-unit-testing-and-editor-icons"></a>Live Unit Testing 및 편집기 아이콘 

**Live Unit Testing이 출력 창의 메시지를 기반으로 한 테스트를 실행하는 것처럼 보이는데 편집기에서 아이콘을 확인할 수 없는 이유는 무엇인가요?** 

**대답:**

Live Unit Testing이 작동하는 어셈블리가 어떤 이유로든 계측되지 않는 경우에 발생합니다. 예를 들어 Live Unit Testing은 `<UseHostCompilerIfAvailable>false</UseHostCompilerIfAvailable>`로 설정된 프로젝트와 호환되지 않습니다. 이 경우에 Live Unit Testing이 작동하기 위해 이 설정을 제거하거나 `true`로 변경하도록 빌드 프로세스를 업데이트해야 합니다.  

## <a name="how-do-i-collect-more-detailed-logs-to-file-bug-reports"></a>파일 버그 보고서에 대한 자세한 로그를 수집하려면 어떻게 해야 하나요? 

**대답:**

자세한 로그를 수집하려면 몇 가지 작업을 수행할 수 있습니다. 

- **도구**, **옵션**, **Live Unit Testing**으로 이동하여 로깅 옵션을 **자세한 정보**로 변경합니다. 이렇게 하면 출력 창에 자세한 로그가 표시됩니다. 

- `LiveUnitTesting_BuildLog` 사용자 환경 변수를 MSBuild 로그를 캡처하는 데 사용하려는 파일의 이름으로 설정합니다. Live Unit Testing 빌드의 자세한 MSBuild 로그 메시지를 해당 파일에서 검색할 수 있습니다.

- `LiveUnitTesting_TestPlatformLog` 사용자 환경 변수를 `1`로 설정하여 테스트 플랫폼 로그를 캡처합니다. Live Unit Testing의 자세한 테스트 플랫폼 로그 메시지를 `[Solution Root]\.vs\[Solution Name]\log\[VisualStudio Process ID]`에서 검색할 수 있습니다.

- `VS_UTE_DIAGNOSTICS`이라는 사용자 수준 환경 변수를 만들고 1(또는 다른 값)로 설정한 다음 Visual Studio를 다시 시작합니다. 이제 Visual Studio의 **출력 - 테스트** 탭에서 여러 로깅이 표시됩니다. 
 
## <a name="see-also"></a>참고 항목

[유닛 테스트](live-unit-testing.md)
 

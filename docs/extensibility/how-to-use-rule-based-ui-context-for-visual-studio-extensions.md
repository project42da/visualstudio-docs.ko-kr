---
title: "방법: Visual Studio 확장에 대 한 규칙 기반 UI 컨텍스트를 사용 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8dd2cd1d-d8ba-49b9-870a-45acf3a3259d
caps.latest.revision: 7
caps.handback.revision: 6
ms.author: "gregvanl"
---
# 방법: Visual Studio 확장에 대 한 규칙 기반 UI 컨텍스트를 사용 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio에서는 VSPackages 경우 특정 로드 잘 알려진 <xref:Microsoft.VisualStudio.Shell.UIContext>s 활성화 됩니다. 이러한 UI 컨텍스트는 하지 매우 세밀 하 게 세분화 되어 있는지, 선택 되지 확장 작성자를 유지 하지만 지점 앞을 활성화 하는 사용 가능한 UI 컨텍스트를 선택 하기 원한다 VSPackage를 로드 합니다. 잘 알려진 UI 컨텍스트의 목록이 참조 <xref:Microsoft.VisualStudio.Shell.KnownUIContexts>합니다.  
  
 패키지를 로드 하면 성능이 저하 될 수 아니며 필요할 보다 더 빨리 로드 하기는 것이 좋습니다. Visual Studio 2015 규칙 기반 UI 컨텍스트, 확장 프로그램 작성자가 UI 컨텍스트의 활성화 하 고 관련된 Vspackage가 로드 되는 정확한 조건을 정의할 수 있게 하는 메커니즘의 개념이 도입 되었습니다.  
  
## 규칙 기반 UI 컨텍스트  
 새 UI 컨텍스트 \(GUID\) "규칙" 구성 되며 하나 이상의 "단어"를 참조 하는 부울 식을 결합 하 여 논리 "및", "또는", "not"을 작업 합니다. "조건" 런타임에 동적으로 계산 됩니다 및 용어 변경 내용을 때마다 식이 다시 계산 합니다. 식이 true 이면 연결 된 UI 컨텍스트 활성화 됩니다. 그렇지 않으면 UI 컨텍스트는 de\-activated입니다.  
  
 규칙 기반 UI 상황에 맞는 여러 가지 방법으로 사용할 수 있습니다.  
  
1.  명령 및 도구 창에 대 한 표시 유형 제약 조건을 지정 합니다. UI 컨텍스트의 규칙이 충족 될 때까지 명령을\/도구 창을 숨길 수 있습니다.  
  
2.  자동으로 로드 제약 조건: 규칙이 충족 될 때만 자동 로드할 패키지  
  
3.  지연 된 작업: 지정한 간격이 경과 하 고는 규칙이 여전히 충족 될 때까지 로드를 지연 합니다.  
  
 메커니즘은 모든 Visual Studio 확장 프로그램에서 사용할 수 있습니다.  
  
## 규칙 기반 UI 컨텍스트 만들기  
 ".config" 확장명을 가진 파일에만 적용 되는 메뉴 명령을 제공 하는 TestPackage 라는 확장 있다고 가정 합니다. V s 2015를 하기 전에 가장 적합 한 옵션 TestPackage 로드 했습니다 때 <xref:Microsoft.VisualStudio.Shell.KnownUIContexts.SolutionExistsAndFullyLoadedContext%2A> UI 컨텍스트의 활성화 되었습니다. 이 비효율적 이며 이후 로드 된 솔루션.config 파일에 하지도 포함 될 수 있습니다. 주십시오 참조 규칙 기반 UI 컨텍스트를 사용 하 여 UI 컨텍스트의 경우.config 확장명을 가진 파일에만 활성화 수 있습니다 선택 되어 방법과 해당 UI 컨텍스트의 활성화 될 때 TestPackage를 로드 합니다.  
  
1.  새 UIContext GUID를 정의 하 고 VSPackage 클래스에 추가 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 및 <xref:Microsoft.VisualStudio.Shell.ProvideUIContextRuleAttribute>합니다.  
  
     예를 들어 새 UIContext 가정 "UIContextGuid"는 추가할 수 있습니다. 만든 GUID \(도구를 클릭 하 여 GUID를 만들 수 있습니다\-\> guid 만들기\) "8B40D5E2\-5626\-42AE\-99EF\-3DD1EFF46E7B" 됩니다. 그런 다음 다음 추가 클래스 내에서 패키지:  
  
    ```c#  
    public const string UIContextGuid = "8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B";  
    ```  
  
     특성에 대해 다음을 추가 합니다. \(이러한 특성의 세부 정보 대해서는 나중에\)  
  
    ```c#  
    [ProvideAutoLoad(TestPackage.UIContextGuid)]      
    [ProvideUIContextRule(TestPackage.UIContextGuid,  
        name: "Test auto load",   
        expression: "DotConfig",  
        termNames: new[] { "DotConfig" },  
        termValues: new[] { "HierSingleSelectionName:.config$" })]  
    ```  
  
     이러한 메타 데이터는 새 UIContext GUID \(8B40D5E2\-5626\-42AE\-99EF\-3DD1EFF46E7B\)와 하나의 조건 "DotConfig"를 참조 하는 식을 정의 합니다. 현재 계층 구조에서 현재 선택한 "\\.config$" \(".config"로 끝나는\) 정규식 패턴과 일치 하는 이름을 가진 때마다 "DotConfig" 라는 용어를 true로 평가 합니다. \(기본값\) 값에는 디버깅에 유용 하지만 규칙에 대 한 선택적 이름을 정의합니다.  
  
     특성의 값은 나중에 빌드 시간 중에 생성 된 pkgdef에 추가 됩니다.  
  
2.  TestPackage의 명령에 대 한 VSCT 파일에서 "DynamicVisibility" 플래그를 적절 한 명령에 추가 합니다.  
  
    ```xml  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    ```  
  
3.  VSCT의 표시 유형 섹션에 새 UIContext \# 1에 정의 된 GUID 적절 한 명령을 연결 합니다.  
  
    ```xml  
    <VisibilityConstraints>   
        <VisibilityItem guid="guidTestPackageCmdSet" id="TestId"  context="guidTestUIContext"/>   
    </VisibilityConstraints>  
    ```  
  
4.  Symbols 섹션에는 UIContext 정의 추가 합니다.  
  
    ```xml  
    <GuidSymbol name="guidTestUIContext" value="{8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B}" />  
    ```  
  
     이제 솔루션 탐색기에서 선택한 항목은 ".config" 파일 및 이러한 명령 중 하나를 선택 하기 전에 패키지를 로드할 수는 경우에 \*.config 파일에 대 한 상황에 맞는 메뉴 명령을 표시 됩니다.  
  
 다음으로, 패키지에만 때 기대할에 로드 되는지 확인 하는 디버거를 사용해 보겠습니다. 디버깅 하려면 TestPackage:  
  
1.  중단점을 설정 된 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드.  
  
2.  TestPackage 빌드하고 디버깅을 시작 합니다.  
  
3.  프로젝트를 만들거나 하나를 엽니다.  
  
4.  이외의.config 확장명을 가진 모든 파일을 선택 합니다. 중단점이 적중 되지 해야 합니다.  
  
5.  App.Config 파일을 선택 합니다.  
  
 TestPackage 로드 하 고 중단점에서 중지 합니다.  
  
## UI 컨텍스트에 대 한 더 많은 규칙을 추가합니다.  
 UI 컨텍스트 규칙 부울 식에 있으므로 UI 컨텍스트에 대 한 더 제한적인된 규칙을 추가할 수 있습니다. 예를 들어 위의 UI 컨텍스트에서 규칙이 프로젝트와 솔루션 로드 될 때에 적용 되도록 지정할 수 있습니다. 이러한 방식으로 명령을 독립 실행형 파일로, 프로젝트의 일부가 아니라 ".config" 파일을 열 경우 설명 하지 않습니다.  
  
```c#  
[ProvideAutoLoad(TestPackage.UIContextGuid)]      
[ProvideUIContextRule(TestPackage.UIContextGuid,    
    name: "Test auto load",  
    expression: "(SingleProject | MultipleProjects) & DotConfig",    
    termNames: new[] { "SingleProject", "MultipleProjects","DotConfig" },     
    termValues: new[] { VSConstants.UICONTEXT_SolutionHasSingleProject_string , VSConstants.UICONTEXT_SolutionHasMultipleProjects_string , "HierSingleSelectionName:.config$" })]  
```  
  
 이제 식에는 세 가지 조건 참조합니다. 처음 두 용어 "SingleProject" 및 "MultipleProjects" \(Guid\) 하 여 잘 알려진 다른 UI 컨텍스트를 가리킵니다. 세 번째 용어 "DotConfig" 앞서 정의한 규칙 기반 UI 컨텍스트로 사용 됩니다.  
  
## 지연 된 활성화  
 규칙에는 선택적인 "지연" 있을 수 있습니다. 지연 시간 \(밀리초\)에 지정 됩니다. 있는 경우 지연 시간을 사용 하면 정품 인증 또는 해당 시간 간격으로 지연 되는 규칙의 UI 컨텍스트의 비활성화 됩니다. 규칙 변경 내용에서 지연 간격 전에 백업 하는 경우 아무 변화가 없습니다. "분산" 초기화 단계\-타이머에 의존 하거나 유휴 상태 알림을 등록 하지 않고 일회 초기화 특히이 메커니즘을 사용할 수 있습니다.  
  
 예를 들어 100 밀리초의 지연 하 여 테스트 부하 규칙을 지정할 수 있습니다.  
  
```c#  
[ProvideAutoLoad(TestPackage.UIContextGuid)]  
[ProvideUIContextRule(TestPackage.UIContextGuid,   
    name: "Test auto load",  
    expression: "DotConfig",   
    termNames: new[] { "DotConfig" },  
    termValues: new[] { "HierSingleSelectionName:.config$" },   
    delay: 100)]  
```  
  
## 용어 유형  
 다양 한 유형의 용어 지원 되는 다음과 같습니다.  
  
|||  
|-|-|  
|{nnnnnnnn nnnn\-nnnn\-nnnn\-형식으로 되어}|GUID는 UI 컨텍스트를 가리킵니다. 그렇지 않으면 UI 컨텍스트는 활성 및 false 때마다 용어 true 됩니다.|  
|HierSingleSelectionName: \< 패턴 \>|현재 계층 구조에서 선택한 항목은 단일 항목을 선택된 된 항목의 이름을 "패턴"에서 제공 된.Net 정규식과 일치 때마다 용어 true 됩니다.|  
|UserSettingsStoreQuery: \< 쿼리 \>|"쿼리" 0이 아닌 값으로 계산 되어야 하는 사용자 설정 저장소에 전체 경로 나타냅니다. 쿼리는 마지막 슬래시에서 "propertyName" 및 "컬렉션"으로 나누어집니다.|  
|ConfigSettingsStoreQuery: \< 쿼리 \>|"쿼리" 0이 아닌 값으로 계산 되어야 하는 구성 설정 저장소에 전체 경로 나타냅니다. 쿼리는 마지막 슬래시에서 "propertyName" 및 "컬렉션"으로 나누어집니다.|  
|ActiveProjectFlavor: \< projectTypeGuid \>|현재 선택한 프로젝트는 사용 될 때마다 용어 발생할 수 있습니다 \(집계 됨\)에 지정 된 프로젝트 형식 GUID와 일치 하는 버전.|  
|ActiveEditorContentType: \< contentType \>|지정 된 콘텐츠 형식으로 텍스트 편집기에서 선택한 문서 용어 true 됩니다.|  
|ActiveProjectCapability: \< 식 \>|용어 활성 프로젝트 기능에 제공 된 식과 일치 하는 경우에 유용 합니다. 식을 VB 같이 수 &#124; CSharp|  
|SolutionHasProjectCapability: \< 식 \>|위의 유사 하지만 용어는 솔루션에 모든 로드 된 프로젝트 식에 일치 하는 경우 true입니다.|  
  
## 버전 간 확장와의 호환성  
 규칙을 기반으로 UI 컨텍스트는 Visual Studio 2015의 새로운 기능 및 이전 버전으로 이식 해야 합니다. 이렇게 해야 Visual Studio 2013의 자동 로드 하 고 이전 버전을 하지만 자동\-에 로드 중인 Visual Studio 2015를 방지 하기 위해 규칙 기반 UI 컨텍스트에서 이익을 얻을 수 있는 Visual Studio의 여러 버전을 대상으로 하는 확장\/패키지에 문제가 됩니다.  
  
 이러한 패키지를 지원 하려면 레지스트리의 AutoLoadPackages 항목 이제 이상 Visual Studio 2015에서 항목을 생략 해야 함을 나타내려면 값 필드에 플래그를 제공할 수 있습니다. 플래그 옵션을 추가 하 여 이렇게 <xref:Microsoft.VisualStudio.Shell.PackageAutoLoadFlags>합니다. Vspackage 추가할 수 **SkipWhenUIContextRulesActive** 옵션을 자신의 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 를 Visual Studio 2015 이상 항목을 무시할지를 나타내는 특성입니다.  
  
## 확장 가능한 UI 컨텍스트 규칙  
 경우에 따라 패키지 정적 UI 상황에 맞는 규칙을 사용할 수 없습니다. 예를 들어 패키지는 명령 상태는 가져온된 MEF 공급자에서 지원 되는 편집기 형식에 기반 확장성을 지원 합니다. 이 명령은 현재 편집 형식을 지 원하는 확장 하는 경우 활성화 됩니다. 이러한 경우 패키지 자체 용어 확장을 사용할 수 있는 MEF에 따라 변경 되므로 정적 UI 컨텍스트 규칙을 사용할 수 없습니다.  
  
 이러한 패키지를 지원 하기 위해 규칙 기반 UI 컨텍스트는 하드 코드 된 식 지원 "\*" 모든 아래 조건으로 추가 될 것을 나타내는 또는 합니다. 명령 상태를이 컨텍스트에 연결 및 마스터 패키지 정의 알려진된 규칙 UI 컨텍스트의 만들 수 있습니다. 나중에 마스터 패키지에 대 한 대상으로 하는 모든 MEF 확장 편집기 마스터 식이나 다른 용어를 영향을 주지 않고 지원에 대 한 해당 용어를 추가할 수 있습니다.  
  
 생성자는 <xref:Microsoft.VisualStudio.Shell.ProvideExtensibleUIContextRuleAttribute.%23ctor%2A> 설명서에는 확장 가능한 UI 컨텍스트 규칙에 대 한 구문을 보여 줍니다.
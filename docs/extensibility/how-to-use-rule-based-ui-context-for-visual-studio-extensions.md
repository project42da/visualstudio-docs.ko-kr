---
title: '방법: Visual Studio 확장에 대 한 규칙 기반 UI 컨텍스트를 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 8dd2cd1d-d8ba-49b9-870a-45acf3a3259d
author: gregvanl
ms.author: gregvanl
ms.workload:
- vssdk
ms.openlocfilehash: 8597c413c899b54e61e848649c3c524cbdb20724
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-rule-based-ui-context-for-visual-studio-extensions"></a>방법: Visual Studio 확장에 대 한 규칙 기반 UI 컨텍스트를 사용 합니다.
Visual Studio에서는 특정 때 Vspackage의 로드 잘 알려진 <xref:Microsoft.VisualStudio.Shell.UIContext>s 활성화 됩니다. 이러한 UI 컨텍스트가 하지 매우가 덜 세분화 된 옵션이 없음 확장 작성자를 종료 하지만 않으며 지점 앞를 활성화 하는 사용 가능한 UI 컨텍스트를 선택할 수 있습니다 않았는지 확인 하 고 VSPackage를 로드 합니다. 잘 알려진 UI 컨텍스트 목록이 참조 <xref:Microsoft.VisualStudio.Shell.KnownUIContexts>합니다.  
  
 성능 영향을 줄 수 패키지를 로드 하 고 필요할 보다 더 빨리 로드 하기 모범 사례는 아닙니다. Visual Studio 2015에는 규칙 기반 UI 컨텍스트, 확장 프로그램 작성자는 UI 컨텍스트가 활성화 되 고 연결 된 Vspackage를 로드 하는 정확한 조건을 정의 하는 메커니즘의 개념을 도입 되었습니다.  
  
## <a name="rule-based-ui-context"></a>규칙 기반 UI 컨텍스트  
 새 UI 컨텍스트 (GUID) "규칙" 구성 되며 하나 이상의 "조건"을 참조 하는 부울 식을 결합 논리 "및", "또는", "not" 작업 합니다. "조건" 런타임에 동적으로 평가 됩니다 및 때마다 조건 변경 내용의 식을 다시 평가 됩니다. 식이 true 이면 연결 된 UI 컨텍스트 활성화 됩니다. 이렇게 하지 않으면 UI 컨텍스트가 비활성화 되었습니다.  
  
 규칙 기반 UI 컨텍스트는 여러 가지 방법으로 사용할 수 있습니다.  
  
1.  명령과 도구 창에 대 한 표시 유형 제약 조건을 지정 합니다. UI 컨텍스트 규칙이 충족 될 때까지 명령/도구 창을 숨길 수 있습니다.  
  
2.  자동으로 로드 제약 조건: 자동 부하는 규칙이 충족 될 경우에 패키지  
  
3.  지연 된 작업: 지정 된 기간이 경과 하 고는 규칙이 여전히 충족 될 때까지 로드 지연 합니다.  
  
 메커니즘은 모든 Visual Studio 확장에서 사용할 수 있습니다.  
  
## <a name="create-a-rule-based-ui-context"></a>규칙 기반 UI 컨텍스트 만들기  
 TestPackage ".config" 확장명을 가진 파일에만 적용 되는 메뉴 명령을 제공 하 라는 확장 있다고 가정 합니다. VS2015, 이전 가장 적합 한 옵션 TestPackage 로드 하지 했습니다 때 <xref:Microsoft.VisualStudio.Shell.KnownUIContexts.SolutionExistsAndFullyLoadedContext%2A> UI 컨텍스트가 활성화 되었습니다. 이 하지 않으므로 효율적으로 로드 된 솔루션이.config 파일에도 없을 수 있습니다. 주세요 참조 규칙 기반 UI 상황에 맞는 경우.config 확장명을 가진 파일에만 UI 컨텍스트를 활성화 데 사용할 수을 선택 및 해당 UI 컨텍스트가 활성화 되 면 TestPackage를 로드 합니다.  
  
1.  새 UIContext GUID를 정의 하 고 VSPackage 클래스에 추가 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 및 <xref:Microsoft.VisualStudio.Shell.ProvideUIContextRuleAttribute>합니다.  
  
     예를 들어 새 UIContext 가정 "UIContextGuid" 추가 하는 것입니다. 만든 GUID (도구를 클릭 하 여 GUID를 만들 수 있습니다-> guid 만들기) "8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B" 됩니다. 그런 다음 다음 추가 패키지 클래스 내부:  
  
    ```csharp  
    public const string UIContextGuid = "8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B";  
    ```  
  
     특성에 대해 다음을 추가 합니다: (이러한 특성의 세부 정보 나중에 설명 됩니다)  
  
    ```csharp  
    [ProvideAutoLoad(TestPackage.UIContextGuid)]      
    [ProvideUIContextRule(TestPackage.UIContextGuid,  
        name: "Test auto load",   
        expression: "DotConfig",  
        termNames: new[] { "DotConfig" },  
        termValues: new[] { "HierSingleSelectionName:.config$" })]  
    ```  
  
     이러한 메타 데이터는 새 UIContext GUID (8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B) 및 단일 용어, "DotConfig"를 참조 하는 식을 정의 합니다. 활성 계층 구조에서 현재 선택한 이름이 지정 된 정규식 패턴과 일치 될 때마다 true로 평가 되는 "DotConfig" 라는 용어 "\\.config$" (".config"로 끝나는). (기본값) 값에는 디버깅에 유용한 규칙에 대 한 선택적 이름을 정의합니다.  
  
     특성의 값은 나중에 빌드 시간 동안 생성 된 pkgdef에 추가 됩니다.  
  
2.  TestPackage의 명령에 대 한 VSCT 파일에서 적절 한 명령에 "DynamicVisibility" 플래그를 추가 합니다.  
  
    ```xml  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    ```  
  
3.  VSCT의 표시 유형 섹션에 새 UIContext # 1에 정의 된 GUID 적절 한 명령을 연결:  
  
    ```xml  
    <VisibilityConstraints>   
        <VisibilityItem guid="guidTestPackageCmdSet" id="TestId"  context="guidTestUIContext"/>   
    </VisibilityConstraints>  
    ```  
  
4.  기호 섹션에는 UIContext의 정의 추가 합니다.  
  
    ```xml  
    <GuidSymbol name="guidTestUIContext" value="{8B40D5E2-5626-42AE-99EF-3DD1EFF46E7B}" />  
    ```  
  
     이제 솔루션 탐색기에서 선택한 항목은 ".config" 파일 및 이러한 명령 중 하나를 선택 하기 전에 패키지를 로드할 수는 경우에 *.config 파일에 대 한 상황에 맞는 메뉴 명령을 표시 됩니다.  
  
 다음으로, 보겠습니다 디버거를 사용 하 여 패키지에만 경우 라고 생각 되 게 로드 되도록 확인 합니다. 디버깅 하려면 TestPackage:  
  
1.  중단점을 설정의 <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> 메서드.  
  
2.  TestPackage 빌드하고 디버깅을 시작 합니다.  
  
3.  프로젝트를 만들거나 엽니다.  
  
4.  이외의.config 확장명을 가진 모든 파일을 선택 합니다. 중단점이 적중 되지 해야 합니다.  
  
5.  App.Config 파일을 선택 합니다.  
  
 TestPackage 로드 하 고 중단점에서 중지 합니다.  
  
## <a name="adding-more-rules-for-ui-context"></a>UI 컨텍스트에 대 한 더 많은 규칙을 추가합니다.  
 UI 컨텍스트 규칙은 부울 식, UI 컨텍스트에 대 한 좀 더 제한 된 규칙을 추가할 수 있습니다. 예를 들어 위의 UI 컨텍스트에서 규칙이 프로젝트와 솔루션 로드 될 때에 적용 되도록 지정할 수 있습니다. 이러한 방식으로 명령을 열면 ".config" 파일을 프로젝트의 일부가 아닌 독립 실행형 파일으로 표시 되지 않습니다.  
  
```csharp  
[ProvideAutoLoad(TestPackage.UIContextGuid)]      
[ProvideUIContextRule(TestPackage.UIContextGuid,    
    name: "Test auto load",  
    expression: "(SingleProject | MultipleProjects) & DotConfig",    
    termNames: new[] { "SingleProject", "MultipleProjects","DotConfig" },     
    termValues: new[] { VSConstants.UICONTEXT_SolutionHasSingleProject_string , VSConstants.UICONTEXT_SolutionHasMultipleProjects_string , "HierSingleSelectionName:.config$" })]  
```  
  
 이제 식 다음 세 가지 용어를 참조합니다. 처음 두 용어 "SingleProject" 및 "MultipleProjects" (Guid) 하 여 잘 알려진 다른 UI 컨텍스트를 참조 하십시오. 세 번째 용어 "DotConfig"는 앞에서 정의한 규칙 기반 UI 컨텍스트입니다.  
  
## <a name="delayed-activation"></a>지연 된 활성화  
 규칙에는 선택 사항 "지연" 있을 수 있습니다. 지연 시간 (밀리초)에 지정 됩니다. 있는 경우 지연으로 인해 활성화 또는 해당 시간 간격으로 지연 될 규칙의 UI 컨텍스트를 비활성화 합니다. 지연 간격은 하기 전에 규칙 변경 내용을 다시, 경우 아무 변화가 없습니다. 이 메커니즘 "분산" 초기화 단계-타이머 또는 유휴 상태 알림을 등록 하지 않고 한 번만 초기화 특히 데 사용할 수 있습니다.  
  
 예를 들어 100 밀리초의 지연이 위해 테스트 부하 규칙을 지정할 수 있습니다.  
  
```csharp  
[ProvideAutoLoad(TestPackage.UIContextGuid)]  
[ProvideUIContextRule(TestPackage.UIContextGuid,   
    name: "Test auto load",  
    expression: "DotConfig",   
    termNames: new[] { "DotConfig" },  
    termValues: new[] { "HierSingleSelectionName:.config$" },   
    delay: 100)]  
```  
  
## <a name="term-types"></a>용어 유형  
 지원 되는 다양 한 용어 유형에 다음과 같습니다.  
  
|||  
|-|-|  
|{nnnnnnnn-nnnn-nnnn-nnnn-nnnnnnnnnnnn}|GUID는 UI 컨텍스트를 가리킵니다. 그렇지 않으면 UI 컨텍스트는 활성 상태이 고 false 때마다 용어 true 됩니다.|  
|HierSingleSelectionName:\<패턴 >|라는 용어는 활성 계층 구조에서 선택한 항목은 단일 항목 및 선택된 항목의 이름을 "패턴"에 의해 제공 된.Net 정규식과 일치 될 때마다 true 됩니다.|  
|UserSettingsStoreQuery:\<쿼리 >|"쿼리" 0이 아닌 값으로 계산 되어야 하는 사용자 설정 저장소로의 전체 경로 나타냅니다. 쿼리는 "collection"과 마지막 슬래시에서 "propertyName"으로 나누어집니다.|  
|ConfigSettingsStoreQuery:\<쿼리 >|"쿼리" 0이 아닌 값으로 계산 되어야 하는 구성 설정 저장소에 전체 경로 나타냅니다. 쿼리는 "collection"과 마지막 슬래시에서 "propertyName"으로 나누어집니다.|  
|ActiveProjectFlavor:\<projectTypeGuid >|현재 선택한 프로젝트 버전이 지정 된 때마다 용어 true 됩니다 (집계 됨) 및 지정된 된 프로젝트 형식의 GUID와 일치 하는 버전입니다.|  
|ActiveEditorContentType:\<contentType >|선택한 문서는 지정한 콘텐츠 형식의 텍스트 편집기 용어 true 됩니다.|  
|ActiveProjectCapability:\<식 >|현재 프로젝트 기능에는 제공 된 식과 일치 하는 경우 용어 마찬가지입니다. 식을 VB 같이 수 &#124; CSharp|  
|SolutionHasProjectCapability:\<식 >|솔루션에 로드 된 프로젝트 식에 일치 하는 경우 위의 유사 하지만 용어 마찬가지입니다.|  
|SolutionHasProjectFlavor:\<projectTypeGuid >|솔루션 (집계 됨)은 버전이 지정 된 프로젝트에 있고 지정된 된 프로젝트 형식의 GUID와 일치 하는 버전 때마다 용어 true 됩니다.|


  
## <a name="compatibility-with-cross-version-extension"></a>버전 간 확장와의 호환성  
 규칙 기반된 UI 컨텍스트는 Visual Studio 2015의 새로운 기능 및 이전 버전에 이식 될 것입니다. 이렇게 하면 여러 버전의 Visual Studio 2013에서 자동으로 로드 되 고 이전 버전 있어야 하지만 자동-에 로드 중인 Visual Studio 2015를 방지 하기 위해 규칙 기반 UI 컨텍스트에서 얻을 수 있는 Visual Studio를 대상으로 하는 확장/패키지에 문제가 만들어집니다.  
  
 이러한 패키지를 지원 하려면 레지스트리의 AutoLoadPackages 항목 이제 이상 Visual Studio 2015 버전에서 항목을 건너뛰어야 함을 나타내려면 값 필드에 플래그를 제공할 수 있습니다. 플래그 옵션을 추가 하 여이 작업을 수행할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.PackageAutoLoadFlags>합니다. Vspackage 이제 추가할 수 **SkipWhenUIContextRulesActive** 옵션을 해당 <xref:Microsoft.VisualStudio.Shell.ProvideAutoLoadAttribute> 이상 Visual Studio 2015 버전에서 항목을 무시할지를 나타내는 특성입니다.  
  
## <a name="extensible-ui-context-rules"></a>확장 가능한 UI 컨텍스트 규칙  
 경우에 따라 패키지는 정적 UI 컨텍스트 규칙을 사용할 수 없습니다. 예를 들어 패키지는 명령 상태 유형을 기반으로 편집기 가져온된 MEF 공급자에서 지원 되는 확장성을 지원 합니다. 이 명령은 현재 편집 형식을 지 원하는 확장 하는 경우에 활성화 됩니다. 이 경우 패키지 자체 조건 확장은 사용할 수 있는 MEF에 따라 변경 하는 이후 정적 UI 컨텍스트 규칙을 사용할 수 없습니다.  
  
 이러한 패키지를 지원 하기 위해 규칙 기반 UI 컨텍스트는 하드 코드 된 식 지원 "*" 모든 아래 조건으로 참여할 수를 나타내는 또는 합니다. 이 통해 정의 하는 마스터 패키지에 대 한 알려진된 규칙 기반 UI 컨텍스트가 해당 명령 상태가이 컨텍스트에 연결. 나중에 마스터 패키지에 대 한 대상으로 하는 모든 MEF 확장 마스터 식이나 다른 용어 영향을 주지 않고 원하는 편집기에 대 한 해당 용어를 추가할 수 있습니다.  
  
 생성자 <xref:Microsoft.VisualStudio.Shell.ProvideExtensibleUIContextRuleAttribute.%23ctor%2A> 설명서에는 확장 가능한 UI 컨텍스트 규칙에 대 한 구문을 보여 줍니다.
---
title: "텍스트 템플릿에서 Visual Studio ModelBus를 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0184e3b543e509d0e523504c0ea07f6fcc36775f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="using-visual-studio-modelbus-in-a-text-template"></a>텍스트 템플릿에서 Visual Studio ModelBus 사용
포함 하는 모델을 읽을 하는 텍스트 템플릿을 작성 하는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus 참조, 액세스 대상 모델에 대 한 참조를 확인 하는 것이 좋습니다. 이 경우 텍스트 템플릿 및 참조 도메인 특정 언어 (Dsl)를 적용 해야 할 수도 있습니다.  
  
-   참조의 대상이 되는 모든 DSL에는 텍스트 서식 파일에서 액세스를 위해 구성 된 ModelBus 어댑터를 설치 해야 합니다. 또한 다른 코드에서 DSL을 액세스 하는 경우에 다시 구성 된 어댑터는 표준 ModelBus 어댑터 외에도 필요 합니다.  
  
     상속 해야 합니다. 어댑터 관리자 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager> 특성이 있어야 하 고 `[HostSpecific(HostName)]`합니다.  
  
-   서식 파일에서 상속 해야 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>합니다.  
  
> [!NOTE]
>  DSL 모델 ModelBus 참조를 포함 하지 않는 읽을 하려는 경우 DSL 프로젝트에서 생성 되는 지시문 프로세서를 사용할 수 있습니다. 자세한 내용은 참조 [텍스트 템플릿에서 모델에 액세스](../modeling/accessing-models-from-text-templates.md)합니다.  
  
 텍스트 템플릿에 대 한 자세한 내용은 참조 [T4 텍스트 템플릿을 사용 하 여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)합니다.  
  
## <a name="creating-a-model-bus-adapter-for-access-from-text-templates"></a>텍스트 템플릿에서 액세스에 대 한 모델 버스 어댑터 만들기  
 텍스트 템플릿에서 ModelBus 참조를 확인 하려면 대상 DSL 호환 가능한 어댑터가 있어야 합니다. 별도 AppDomain에서 텍스트 템플릿을 실행는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기를 문서화 하 고 따라서 어댑터에 있는 DTE를 통해 액세스 하는 대신 모델을 로드 합니다.  
  
#### <a name="to-create-a-modelbus-adapter-that-is-compatible-with-text-templates"></a>텍스트 템플릿 호환 되는 ModelBus 어댑터를 만들려면  
  
1.  대상 DSL 솔루션에 없는 경우는 **ModelBusAdapter** 프로젝트에서 Modelbus 확장 마법사를 사용 하 여 만듭니다.  
  
    1.  다운로드 및 설치는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus 확장을 아직 수행 하지 않은 경우. 자세한 내용은 참조 [Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=185579)합니다.  
  
    2.  DSL 정의 파일을 엽니다. 디자인 화면을 마우스 오른쪽 단추로 누른 **사용 Modelbus**합니다.  
  
    3.  대화 상자에서 선택 **이 DSL는 ModelBus에 노출 하려는**합니다. 이 DSL 해당 모델을 노출 하 고 다른 Dsl에 대 한 참조를 사용 하려는 경우 두 옵션을 선택할 수 있습니다.  
  
    4.  **확인**을 클릭합니다. "ModelBusAdapter"라는 새 프로젝트가 DSL 솔루션에 추가됩니다.  
  
    5.  클릭 **모든 템플릿 변환**합니다.  
  
    6.  솔루션을 다시 빌드합니다.  
  
2.  텍스트 템플릿에서 명령 등의 다른 코드에서 DSL에 액세스 하려는 경우 복제는 **ModelBusAdapter** 프로젝트:  
  
    1.  Windows 탐색기에서 복사 하 고 포함 된 폴더에 붙여 넣을 **ModelBusAdapter.csproj**합니다.  
  
    2.  프로젝트 파일의 이름을 바꿉니다 (예를 들어 **T4ModelBusAdapter.csproj**).  
  
    3.  **솔루션 탐색기**솔루션 노드를 마우스 오른쪽 단추로 가리킨 **추가**, 클릭 하 고 **기존 프로젝트**합니다. 새 어댑터 프로젝트를 찾을 **T4ModelBusAdapter.csproj**합니다.  
  
    4.  각 `*.tt` 파일 새 프로젝트의 네임 스페이스를 변경 합니다.  
  
    5.  솔루션 탐색기에서 새 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 Properties를 클릭 합니다. 속성 편집기에서 생성된 된 어셈블리 및 기본 네임 스페이스의 이름을 변경 합니다.  
  
    6.  두 어댑터 모두에 대 한 참조 된 갖도록 DslPackage 프로젝트에서 새 어댑터 프로젝트에 대 한 참조를 추가 합니다.  
  
    7.  DslPackage\source.extension.tt에서 새 어댑터 프로젝트를 참조 하는 행을 추가 합니다.  
  
        ```  
        <MefComponent>|T4ModelBusAdapter|</MefComponent>  
        ```  
  
    8.  **모든 템플릿 변환** 는 솔루션을 다시 빌드합니다. 빌드 오류가 발생 해야 합니다.  
  
3.  새 어댑터 프로젝트에서 다음 어셈블리에 대 한 참조를 추가 합니다.  
  
    -   Microsoft.VisualStudio.TextTemplating.11.0  
  
         Microsoft.VisualStudio.TextTemplating.Modeling.11.0  
  
4.  AdapterManager.tt:  
  
    -   상속 되도록 AdapterManagerBase의 선언을 변경 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>합니다.  
  
         `public partial class <#= dslName =>AdapterManagerBase :`  
  
         `Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager { ...`  
  
    -   파일의 끝에서 AdapterManager 클래스 전에 HostSpecific 특성을 대체 합니다. 다음 줄을 제거 합니다.  
  
         `[DslIntegration::HostSpecific(DslIntegrationShell::VsModelingAdapterManager.HostName)]`  
  
         다음 줄을 삽입 합니다.  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
         이 특성 modelbus 소비자는 어댑터를 검색할 때 사용할 수 있는 어댑터의 집합을 필터링 합니다.  
  
5.  **모든 템플릿 변환** 는 솔루션을 다시 빌드합니다. 빌드 오류가 발생 해야 합니다.  
  
## <a name="writing-a-text-template-that-can-resolve-modelbus-references"></a>ModelBus 참조를 확인할 수 있는 텍스트 템플릿 작성  
 일반적으로 읽고 "원본" DSL에서에서 파일을 생성 하는 템플릿을 사용 하 여 시작 합니다. 이 서식 파일에 설명 된 방식으로 소스 모델 파일을 읽는 소스 DSL 프로젝트에서 생성 되는 지시문을 사용 하 여 [텍스트 템플릿에서 모델에 액세스](../modeling/accessing-models-from-text-templates.md)합니다. 그러나 소스 DSL ModelBus DSL "대상"에 대 한 참조를 포함합니다. 따라서 참조를 확인 하 고 대상 DSL 액세스할 템플릿 코드를 설정 하려고 합니다. 따라서 이러한 단계에 따라 템플릿을 적용 해야 합니다.  
  
-   서식 파일의 기본 형식을 변경 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>합니다.  
  
-   포함 `hostspecific="true"` 템플릿 지시문에 있습니다.  
  
-   DSL 대상 및 해당 어댑터를 하 고 ModelBus 있도록 어셈블리 참조를 추가 합니다.  
  
-   대상 DSL의 일부로 생성 되는 지시문이 필요가 없습니다.  
  
```  
<#@ template debug="true" hostspecific="true" language="C#"  
inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>   
<#@ SourceDsl processor="SourceDslDirectiveProcessor" requires="fileName='Sample.source'" #>  
<#@ output extension=".txt" #>  
<#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>  
<#@ assembly name = "Company.TargetDsl.Dsl.dll" #>  
<#@ assembly name = "Company.TargetDsl.T4ModelBusAdapter.dll" #>  
<#@ assembly name = "System.Core" #>  
<#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>  
<#@ import namespace="Company.TargetDsl" #>  
<#@ import namespace="Company.TargetDsl.T4ModelBusAdapters" #>  
<#@ import namespace="System.Linq" #>  
<#  
  SourceModelRoot source = this.ModelRoot; // Usual access to source model.  
  // In the source DSL Definition, the root element has a model reference:  
  using (TargetAdapter adapter = this.ModelBus.CreateAdapter(source.ModelReference) as TargetAdapter)   
  {if (adapter != null)  
   {  
      // Get the root of the target model:  
      TargetRoot target = adapter.ModelRoot;  
    // The source DSL Definition has a class "SourceElement" embedded under the root.  
    // (Let's assume they're all in the same model file):  
    foreach (SourceElement sourceElement in source.Elements)  
    {  
      // In the source DSL Definition, each SourceElement has a MBR property:  
      ModelBusReference elementReference = sourceElement.ReferenceToTarget;  
      // Resolve the target model element:   
      TargetElement element = adapter.ResolveElementReference<TargetElement>(elementReference);   
#>  
     The source <#= sourceElement.Name #> is linked to: <#= element.Name #> in target model: <#= target.Name #>.  
<#  
    }  
  }}  
  // Other useful code: this.Host.ResolvePath(filename) gets an absolute filename   
  // from a path that is relative to the text template.  
#>  
  
```  
  
 이 텍스트 템플릿을 실행 될 때는 `SourceDsl` 지시문 파일을 로드 `Sample.source`합니다. 서식 파일에서 시작 해당 모델의 요소에 액세스할 수 `this.ModelRoot`합니다. 도메인 클래스 및 해당 DSL의 속성을 코드에서 사용할 수 있습니다.  
  
 또한 서식 파일 ModelBus 참조를 확인할 수 있습니다. 참조 대상 모델을 가리킵니다, 여기서 assembly 지시문 사용 도메인 클래스 및 해당 모델의 DSL의 속성을 사용 하 여 코드를 수 있습니다.  
  
-   DSL 프로젝트에 의해 생성 된 지시문을 사용 하지 않는 경우 다음도 포함 해야 있습니다.  
  
    ```  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.11.0" #>  
    <#@ assembly name = "Microsoft.VisualStudio.TextTemplating.Modeling.11.0" #>  
    ```  
  
-   사용 하 여 `this.ModelBus` 는 ModelBus에 대 한 액세스를 얻으려고 합니다.  
  
## <a name="walkthrough-testing-a-text-template-that-uses-modelbus"></a>연습: ModelBus를 사용 하는 텍스트 템플릿을 테스트  
 이 연습에서는 다음이 단계를 수행 합니다.  
  
1.  두 개의 Dsl을 생성 합니다. 하나의 DSL는 *소비자*에 `ModelBusReference` 다른 DSL를 참조할 수 있는 속성은 *공급자*합니다.  
  
2.  공급자에서 두 개의 ModelBus 어댑터를 만듭니다: 텍스트 템플릿에 대 한 일반 코드에 대 한 다른 액세스에 대 한 합니다.  
  
3.  단일 실험적 프로젝트에는 Dsl의 인스턴스 모델을 만듭니다.  
  
4.  다른 모델을 가리키도록 모델 하나에 도메인 속성을 설정 합니다.  
  
5.  가 가리키는 모델을 두 번 클릭 처리기를 작성 합니다.  
  
6.  첫 번째 모델을 로드할 다른 모델에 대 한 참조를 수행 하 고 다른 모델을 읽을 수 있는 텍스트 템플릿을 작성 합니다.  
  
#### <a name="construct-a-dsl-that-is-accessible-to-modelbus"></a>DSL ModelBus에 액세스할 수 있는 구문  
  
1.  새 DSL 솔루션을 만듭니다. 이 예제에 대 한 작업 흐름 솔루션 템플릿을 선택 합니다. 언어 이름으로 설정 `MBProvider` 및 파일 이름 확장명 ".provide"입니다.  
  
2.  DSL 정의 다이어그램에서 위쪽에 없는 다이어그램의 빈 부분을 마우스 오른쪽 단추로 클릭 하 고 클릭 **사용 Modelbus**합니다.  
  
    -   표시 되지 않으면 **사용 Modelbus**를 다운로드 하 고 VMSDK ModelBus 확장을 설치 해야 합니다. VMSDK 사이트 찾기: [Visualization and Modeling SDK](http://go.microsoft.com/fwlink/?LinkID=185579)합니다.  
  
3.  에 **Modelbus 사용** 대화 상자에서 **이 DSL는 ModelBus에 노출**, 클릭 하 고 **확인**합니다.  
  
     새 프로젝트를 `ModelBusAdapter`, 솔루션에 추가 합니다.  
  
 텍스트 템플릿에서 ModelBus 통해 액세스할 수 있는 DSL 생깁니다. 명령, 이벤트 처리기 또는 모델 파일 편집기의 AppDomain에서 작동 중 일부는 규칙의 코드에서 참조를 해결할 수 있습니다. 그러나 텍스트 템플릿 별도 AppDomain에서 실행 되며 편집 중일 때 모델에 액세스할 수 없습니다. 텍스트 템플릿에서이 dsl ModelBus 참조에 액세스 하려는 경우에 별도 ModelBusAdapter 있어야 합니다.  
  
#### <a name="to-create-a-modelbus-adapter-that-is-configured-for-text-templates"></a>텍스트 템플릿 용으로 구성 된 ModelBus 어댑터를 만들려면  
  
1.  Windows 탐색기에서 복사한 ModelBusAdapter.csproj 포함 된 폴더를 붙여 넣습니다.  
  
     T4ModelBusAdapter 폴더를 이름을 지정 합니다.  
  
     T4ModelBusAdapter.csproj 프로젝트 파일을 이름을 바꿉니다.  
  
2.  솔루션 탐색기에서 T4ModelBusAdapter MBProvider 솔루션에 추가 합니다. 솔루션 노드를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**, 클릭 하 고 **기존 프로젝트**합니다.  
  
3.  T4ModelBusAdapter 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 Properties를 클릭 합니다. 프로젝트 속성 창에서 변경 된 **어셈블리 이름** 및 **Default Namespace** 를 `Company.MBProvider.T4ModelBusAdapters`합니다.  
  
4.  T4ModelBusAdapter 각 *.tt 파일에는 줄은 다음과 유사 하에 네임 스페이스의 마지막 부분에 "T4"을 삽입 합니다.  
  
     `namespace <#= CodeGenerationUtilities.GetPackageNamespace(this.Dsl) #>.T4ModelBusAdapters`  
  
5.  에 `DslPackage` 프로젝트를 프로젝트 참조를 추가 `T4ModelBusAdapter`합니다.  
  
6.  DslPackage\source.extension.tt, 아래에 다음 줄 추가 `<Content>`합니다.  
  
     `<MefComponent>|T4ModelBusAdapter|</MefComponent>`  
  
7.  에 `T4ModelBusAdapter` 프로젝트에 대 한 참조를 추가 합니다: **Microsoft.VisualStudio.TextTemplating.Modeling.11.0**  
  
8.  Open T4ModelBusAdapter\AdapterManager.tt:  
  
    1.  AdapterManagerBase의 기본 클래스를 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>로 변경합니다. 파일의이 부분 다음과 유사 합니다.  
  
        ```  
        namespace <#= CodeGenerationUtilities.GetPackageNamespace(this.Dsl) #>.T4ModelBusAdapters  
        {  
            /// <summary>  
            /// Adapter manager base class (double derived pattern) for the <#= dslName #> Designer  
            /// </summary>  
            public partial class <#= dslName #>AdapterManagerBase   
            : Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager  
            {  
  
        ```  
  
    2.  파일의 끝에서 AdapterManager 클래스 앞에 다음 추가 특성을 삽입 합니다.  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
         결과 다음과 같습니다.  
  
        ```  
        /// <summary>  
        /// ModelBus modeling adapter manager for a <#= dslName #>Adapter model adapter  
        /// </summary>  
        [Mef::Export(typeof(DslIntegration::ModelBusAdapterManager))]  
        [Mef::ExportMetadata(DslIntegration::CompositionAttributes.AdapterIdKey,<#= dslName #>Adapter.AdapterId)]  
        [DslIntegration::HostSpecific(DslIntegrationShell::VsModelingAdapterManager.HostName)]  
        [Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]  
        public partial class <#= dslName #>AdapterManager : <#= dslName #>AdapterManagerBase  
        {  
        }  
  
        ```  
  
9. 클릭 **모든 템플릿 변형** 에서 제목 표시줄의 솔루션 탐색기.  
  
10. 솔루션을 다시 빌드합니다. F5 키를 클릭 합니다.  
  
11. F5 키를 눌러 DSL 작동 하는지 확인 합니다. 실험적 프로젝트를 열고 `Sample.provider`합니다. 실험적 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 인스턴스를 닫습니다.  
  
 텍스트 템플릿 및 일반 코드로이 dsl ModelBus 참조 이제 해결할 수 있습니다.  
  
#### <a name="construct-a-dsl-with-a-modelbus-reference-domain-property"></a>DSL ModelBus 참조 도메인 속성을 갖는 구문  
  
1.  최소한의 언어 솔루션 템플릿을 사용 하 여 새 DSL를 만듭니다. MBConsumer 언어 이름을 지정 하 고 파일 이름 확장명 ".consume"을 설정 합니다.  
  
2.  DSL 프로젝트에서 DSL MBProvider 어셈블리에 대 한 참조를 추가 합니다. 마우스 오른쪽 단추로 클릭 `MBConsumer\Dsl\References` 클릭 하 고 **참조 추가**합니다. 에 **찾아보기** 탭, 찾기`MBProvider\Dsl\bin\Debug\Company.MBProvider.Dsl.dll`  
  
     그러면 다른 DSL을 사용 하는 코드를 만들 수 있습니다. 여러 Dsl에 대 한 참조를 만들려는 경우에 추가 합니다.  
  
3.  DSL 정의 다이어그램에서 다이어그램을 마우스 오른쪽 단추로 클릭 하 고 클릭 **사용 ModelBus**합니다. 대화 상자에서 선택 **는 ModelBus를 사용 하도록이 DSL을 사용 하도록 설정**합니다.  
  
4.  클래스에 `ExampleElement`, 새 도메인 속성을 추가할 `MBR`, 속성 창에서 해당 형식으로 설정 하 고 `ModelBusReference`합니다.  
  
5.  다이어그램에서 도메인 속성을 마우스 오른쪽 단추로 누른 **편집 ModelBusReference 특정 속성**합니다. 대화 상자에서 선택 **모델 요소**합니다.  
  
     다음에 파일 대화 상자 필터를 설정 합니다.  
  
     `Provider File|*.provide`  
  
     뒤의 부분 문자열 "&#124;" 파일 선택 대화 상자에 대 한 필터입니다. 사용 하 여 모든 파일을 허용 하도록 설정할 수 있습니다 * 합니다.\*  
  
     에 **모델 요소 형식** 목록 DSL (예를 들어 Company.MBProvider.Task) 공급자에 하나의 자세한 자세한 도메인 클래스의 이름을 입력 합니다. 추상 클래스 될 수 있습니다. 목록을 비워 두면 사용자는 모든 요소에 대 한 참조를 설정할 수 있습니다.  
  
6.  대화 상자를 닫고 및 **모든 템플릿 변형**합니다.  
  
 다른 DSL의 요소에 대 한 참조를 포함할 수 있는 하는 DSL을 만들었습니다.  
  
#### <a name="create-a-modelbus-reference-to-another-file-in-the-solution"></a>솔루션의 다른 파일에 대 한 ModelBus 만들기  
  
1.  MBConsumer 솔루션에서 CTRL + f 5를 누릅니다. 실험적 인스턴스가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 열립니다는 **MBConsumer\Debugging** 프로젝트.  
  
2.  에 Sample.provide의 복사본 추가 **MBConsumer\Debugging** 프로젝트. 동일한 솔루션에 파일을 참조 해야 ModelBus 참조 되므로이 작업이 필요 합니다.  
  
    1.  디버깅 프로젝트를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**, 클릭 하 고 **기존 항목**합니다.  
  
    2.  에 **항목 추가** 대화 상자에서 필터를 설정 **모든 파일 (\*.\*)** .  
  
    3.  로 이동 `MBProvider\Debugging\Sample.provide` 클릭 하 고 **추가**합니다.  
  
3.  `Sample.consume`를 엽니다.  
  
4.  예제 모양을 클릭 하 고 속성 창에서 클릭 **[...]**  MBR 속성에 있습니다. 대화 상자에서 클릭 **찾아보기** 선택 `Sample.provide`합니다. 요소 창에서 작업 형식을 확장 하 고 요소 중 하나를 선택 합니다.  
  
5.  파일을 저장합니다.  
  
     (아직의 실험적 인스턴스를 닫지 마십시오 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].)  
  
 다른 모델의 요소에 대 한 ModelBus를 포함 하는 모델을 작성 했습니다.  
  
#### <a name="resolve-a-modelbus-reference-in-a-text-template"></a>텍스트 템플릿에서 ModelBus 참조 확인  
  
1.  실험적 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 샘플 텍스트 템플릿 파일을 엽니다. 해당 콘텐츠를 다음과 같이 설정 합니다.  
  
    ```  
    <#@ template debug="true" hostspecific="true" language="C#"  
    inherits="Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation" #>   
    <#@ MBConsumer processor="MBConsumerDirectiveProcessor" requires="fileName='Sample.consume'" #>  
    <#@ output extension=".txt" #>  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.Integration.11.0" #>  
    <#@ assembly name = "Company.MBProvider.Dsl.dll" #>  
    <#@ import namespace="Microsoft.VisualStudio.Modeling.Integration" #>  
    <#@ import namespace="Company.MBProvider" #>  
    <#  
      // Property provided by the Consumer directive processor:  
      ExampleModel consumerModel = this.ExampleModel;   
      // Iterate through Consumer model, listing the elements:  
      foreach (ExampleElement element in consumerModel.Elements)  
      {  
    #>  
       <#= element.Name #>   
    <#  
        if (element.MBR != null)  
      using (ModelBusAdapter adapter = this.ModelBus.CreateAdapter(element.MBR))  
      {   
              // If we allowed multiple types or DSLs in the MBR, discover type here.  
        Task task = adapter.ResolveElementReference<Task>(element.MBR);  
    #>  
            <#= element.Name #> is linked to Task: <#= task==null ? "(null)" : task.Name #>  
    <#  
          }  
      }  
    #>  
  
    ```  
  
     다음 사항을 확인합니다.  
  
    1.  `hostSpecific` 및 `inherits` 의 특성은 `template` 지시문을 설정 해야 합니다.  
  
    2.  소비자 모델 해당 DSL에서 생성 된 지시문 프로세서를 통해 일반적인 방식으로 액세스 합니다.  
  
    3.  어셈블리 및 import 지시문 ModelBus 및 DSL 공급자의 형식에 액세스할 수 있어야 합니다.  
  
    4.  많은 마샬링된 같은 모델에 연결 되어 있음을 알고 있는 경우 한 번만 CreateAdapter를 호출 하는 것이 좋습니다.  
  
2.  템플릿을 저장하는 경우 결과 텍스트 파일에 다음과 유사한 지 확인 합니다.  
  
    ```  
  
    ExampleElement1   
    ExampleElement2   
         ExampleElement2 is linked to Task: Task2  
  
    ```  
  
#### <a name="resolve-a-modelbus-reference-in-a-gesture-handler"></a>제스처 처리기에서 ModelBus 참조 확인  
  
1.  실험적 인스턴스를 닫은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]실행 되는 경우, 합니다.  
  
2.  MBConsumer\Dsl\Custom.cs 라는 이며 해당 콘텐츠를 다음 설정 된 파일을 추가 합니다.  
  
    ```  
  
    namespace Company.MB2Consume  
    {  
      using Microsoft.VisualStudio.Modeling.Integration;  
      using Company.MB3Provider;  
  
      public partial class ExampleShape  
      {  
        public override void OnDoubleClick(Microsoft.VisualStudio.Modeling.Diagrams.DiagramPointEventArgs e)  
        {  
          base.OnDoubleClick(e);  
          ExampleElement element = this.ModelElement as ExampleElement;  
          if (element.MBR != null)  
          {  
            IModelBus modelbus = this.Store.GetService(typeof(SModelBus)) as IModelBus;  
            using (ModelBusAdapter adapter = modelbus.CreateAdapter(element.MBR))  
            {  
              Task task = adapter.ResolveElementReference<Task>(element.MBR);  
              // Open a window on this model:  
              ModelBusView view = adapter.GetDefaultView();  
              view.Show();  
              view.SetSelection(element.MBR);  
            }  
          }  
        }  
      }  
    }  
  
    ```  
  
3.  Ctrl+F5를 누릅니다.  
  
4.  실험적 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]개방형 `Debugging\Sample.consume`합니다.  
  
5.  모양을 두 번 클릭 합니다.  
  
     해당 요소에는 MBR을 설정한 경우 참조 되는 모델 열리고 참조 된 요소를 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio Modelbus를 사용 하 여 모델을 통합](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

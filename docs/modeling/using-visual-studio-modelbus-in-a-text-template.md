---
title: "텍스트 템플릿에서 Visual Studio ModelBus 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5ed3e5c2-f60f-43c7-8ef4-754f511339c5
caps.latest.revision: 13
caps.handback.revision: 13
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 텍스트 템플릿에서 Visual Studio ModelBus 사용
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

포함 된 모델을 읽을 텍스트 서식 파일을 기록 하는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Modelbus를 참조 하는 대상 모델에 액세스 하려면 참조를 확인 할 수 있습니다.  이 경우 텍스트 서식 파일 및 참조 된 도메인 관련 언어 \(Dsl\)을 적용할 수 있습니다.  
  
-   참조 대상인 DSL에서 텍스트 서식 파일 액세스를 위해 구성 된 ModelBus 어댑터가 있어야 합니다.  또한 DSL를 다른 코드에서 액세스 하는 경우 다시 구성된 어댑터 외에 표준 ModelBus 어댑터입니다.  
  
     어댑터 관리자에서 상속 해야 합니다 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager> 특성이 있어야 하 고 `[HostSpecific(HostName)]`.  
  
-   서식 파일에서 상속 해야 합니다 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>.  
  
> [!NOTE]
>  ModelBus 대 한 참조를 포함 하지 않는 DSL 모델을 읽고 싶은 경우 DSL 프로젝트에서 생성 된 지시문 프로세서를 사용할 수 있습니다.  자세한 내용은 [텍스트 템플릿에서 모델에 액세스](../modeling/accessing-models-from-text-templates.md)를 참조하십시오.  
  
 텍스트 템플릿에 대한 자세한 내용은 [T4 텍스트 템플릿을 사용하여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)을 참조하십시오.  
  
## 모델 버스 어댑터에 대 한 액세스를 텍스트 서식 파일 만들기  
 텍스트 서식에 대 한 ModelBus 참조를 해결 하려면 대상 DSL 호환 가능한 어댑터가 있어야 합니다.  텍스트 템플릿 실행에서 별도 Appdomain에는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 편집기를 문서화 하 고 따라서 DTE를 통해 액세스 하는 대신 모델을 로드 하는 어댑터를 포함 합니다.  
  
#### 텍스트 서식으로 호환 되는 ModelBus 어댑터를 만들려면  
  
1.  DSL 솔루션 대상에 게는 **ModelBusAdapter** 프로젝트에서 Modelbus 확장 마법사를 사용 하 여 만듭니다.  
  
    1.  다운로드 및 설치는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus 이미 이렇게 하지 않았다면 확장 합니다.  자세한 내용은 [시각화 및 모델링 SDK](란?LinkID%20=%20185579).  
  
    2.  DSL 정의 파일을 엽니다.  디자인 화면을 마우스 오른쪽 단추로 클릭 하 고 다음을 클릭  **사용 Modelbus**.  
  
    3.  선택 대화 상자에서  **에 노출 하는 Modelbus이이 DSL**.  이 DSL의 모델을 제공 하 고 다른 Dsl에 대 한 참조를 사용할 경우 두 가지 옵션을 선택할 수 있습니다.  
  
    4.  **확인**을 클릭합니다.  새 프로젝트 "ModelBusAdapter" DSL 솔루션에 추가 됩니다.  
  
    5.  클릭  **서식 파일을 모두 변환**.  
  
    6.  솔루션을 다시 빌드합니다.  
  
2.  텍스트 서식에서 및 기타 코드, 명령 등에서 DSL 액세스 하는 경우 복제는 **ModelBusAdapter** 프로젝트:  
  
    1.  Windows 탐색기에서 복사 하 고 있는 폴더에 붙여 넣습니다 **ModelBusAdapter.csproj**.  
  
    2.  프로젝트 파일 이름 바꾸기 \(예를 들어, **T4ModelBusAdapter.csproj**\).  
  
    3.  **솔루션 탐색기**, 솔루션 노드를 마우스 오른쪽 단추로 클릭 하 고 가리킨  **추가**에서 다음을 클릭 하 고  **기존 프로젝트**.  어댑터에서 새 프로젝트를 찾을 **T4ModelBusAdapter.csproj**.  
  
    4.  각 `*.tt` 파일은 새 프로젝트의 네임 스페이스를 변경 합니다.  
  
    5.  솔루션 탐색기에서 새 프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 속성을 클릭 합니다.  속성 편집기에서 생성 된 어셈블리 및 기본 네임 스페이스의 이름을 변경 합니다.  
  
    6.  두 어댑터 모두에 대 한 참조를 가질 수 있도록 DslPackage 프로젝트에 새 어댑터가 프로젝트에 참조를 추가 합니다.  
  
    7.  Dslpackage\\source.extension.tt에서 새 어댑터 프로젝트가 참조 하는 줄을 추가 합니다.  
  
        ```  
        <MefComponent>|T4ModelBusAdapter|</MefComponent>  
        ```  
  
    8.  **모든 템플릿 변환** 하 고 솔루션을 다시 빌드합니다.  빌드 오류가 발생 합니다.  
  
3.  새 어댑터 프로젝트에서 다음 어셈블리에 대 한 참조를 추가 합니다.  
  
    -   Microsoft.VisualStudio.TextTemplating.11.0  
  
         Microsoft.VisualStudio.TextTemplating.Modeling.11.0  
  
4.  에 AdapterManager.tt:  
  
    -   상속 되는 Adaptermanagerbase의 선언을 변경 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>.  
  
         `public partial class <#= dslName =>AdapterManagerBase :`  
  
         `Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager { ...`  
  
    -   파일의 끝에 가까이 전에 AdapterManager 클래스의 HostSpecific 특성을 대체 합니다.  다음 줄을 제거 합니다.  
  
         `[DslIntegration::HostSpecific(DslIntegrationShell::VsModelingAdapterManager.HostName)]`  
  
         다음 줄을 삽입 합니다.  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
         이 특성에 modelbus 소비자에 대 한 어댑터를 검색할 때 사용할 수 있는 어댑터 집합이 필터링 합니다.  
  
5.  **모든 템플릿 변환** 하 고 솔루션을 다시 빌드합니다.  빌드 오류가 발생 합니다.  
  
## ModelBus 참조를 확인할 수 있습니다 텍스트 서식 파일 작성  
 일반적으로 읽고 파일 "원본" DSL 생성 하는 템플릿과 함께 시작 합니다.  원본 모델에서 설명 하는 방식으로 읽을 수 DSL 원본 프로젝트에서 생성 되는 지시문이 서식이 파일을 사용 하 여 [텍스트 템플릿에서 모델에 액세스](../modeling/accessing-models-from-text-templates.md).  그러나 원본 DSL ModelBus 참조 하는 "대상" DSL 포함합니다.  템플릿 코드에 대 한 참조를 확인 하 고 DSL 대상에 액세스를 사용 하도록 합니다.  따라서 다음과이 같이 템플릿을 적응 해야 합니다.  
  
-   서식 파일의 기본 클래스를 변경 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.ModelBusEnabledTextTransformation>.  
  
-   포함 `hostspecific="true"` 템플릿 지시문에서입니다.  
  
-   대상 DSL 및 해당 어댑터 및 Modelbus를 사용 하려면 어셈블리 참조를 추가 합니다.  
  
-   DSL 대상의 일부로 생성 된 지시문이 필요 하지 않습니다.  
  
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
    // (Let’s assume they’re all in the same model file):  
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
  
 이 텍스트 템플릿을 실행 하면 해당 `SourceDsl` 지시문 파일 로드 `Sample.source`.  서식 파일에서 시작 하는 해당 모델의 요소에 액세스할 수 있습니다 `this.ModelRoot`.  코드는 도메인 클래스와 해당 DSL의 속성을 사용할 수 있습니다.  
  
 또한 서식 파일 ModelBus 참조를 확인할 수 있습니다.  어셈블리 지시문 참조 대상 모델을 가리킨 곳 도메인 클래스와 해당 모델의 DSL의 속성을 사용 하 여 코드를 수 있습니다.  
  
-   DSL 프로젝트에 의해 생성 되는 지시어를 사용 하지 않는 경우에 포함 되어야 합니다.  
  
    ```  
    <#@ assembly name = "Microsoft.VisualStudio.Modeling.Sdk.11.0" #>  
    <#@ assembly name = "Microsoft.VisualStudio.TextTemplating.Modeling.11.0" #>  
    ```  
  
-   사용 `this.ModelBus` 에서 Modelbus에 액세스할 수 있습니다.  
  
## 연습: Modelbus를 사용 하 여 텍스트 서식 파일 테스트  
 이 연습에서는 다음이 단계를 수행 하십시오.  
  
1.  두 개의 Dsl을 생성 합니다.  한 DSL는  *소비자*,이 `ModelBusReference` 다른 DSL를 참조할 수 있는 속성의  *공급자*.  
  
2.  공급자의 ModelBus 어댑터를 두 개 만듭니다:에 대 한 텍스트 서식 파일에서 다른 일반 코드에 대해.  
  
3.  한 실험적인 프로젝트에 Dsl 모델 인스턴스를 만듭니다.  
  
4.  한 모델에 다른 모델을 가리키도록 도메인 속성을 설정 합니다.  
  
5.  가리키는 하 여 모델을 엽니다 두 번 클릭 처리기를 작성 합니다.  
  
6.  첫 번째 모델 로드 하 고 다른 모델에 대 한 참조에 따라 고 다른 모델을 읽을 수 있는 텍스트 서식 파일을 작성 합니다.  
  
#### Modelbus에 액세스할 수 있는 DSL 작성  
  
1.  새 DSL 솔루션을 만듭니다.  이 예제에 대 한 작업 흐름 솔루션 템플릿을 선택 합니다.  언어 이름을 설정  `MBProvider` 및 파일 이름 확장명을 ".provide"입니다.  
  
2.  DSL 정의 다이어그램의 위쪽에 있는 다이어그램의 빈 부분을 마우스 오른쪽 단추로 클릭 하 고 다음을 클릭  **사용 Modelbus**.  
  
    -   보이지 않는 경우  **사용 Modelbus**를 다운로드 하 고 VMSDK ModelBus 확장을 설치 해야 합니다.  VMSDK 사이트에서 찾기: [시각화 및 모델링 SDK](란?LinkID%20=%20185579).  
  
3.  에  **사용 Modelbus** 선택 대화 상자  **노출 하는 Modelbus이이 DSL**를 클릭 하 고 다음을 클릭  **확인**.  
  
     새 프로젝트를 `ModelBusAdapter`를 솔루션에 추가 됩니다.  
  
 이제 DSL 텍스트 템플릿 ModelBus 통해 액세스할 수 있습니다.  명령, 이벤트 처리기 또는 모델 파일 편집기의 Appdomain에 모두를 작동 하는 규칙을 코드에 대 한 참조를 확인할 수 있습니다.  그러나 텍스트 템플릿을 별도 Appdomain에서 실행 및 편집 될 때 모델에 액세스할 수 없습니다.  이 DSL ModelBus 참조 텍스트 서식 파일에서에 액세스 하려는 경우 별도 ModelBusAdapter 있어야 합니다.  
  
#### 텍스트 서식 파일을 구성 하는 ModelBus 어댑터를 만들려면  
  
1.  Windows 탐색기에서 복사 하 고 Modelbusadapter.csproj를 포함 하는 폴더에 붙여 넣습니다.  
  
     T4ModelBusAdapter 폴더를 이름을 지정 합니다.  
  
     T4ModelBusAdapter.csproj 프로젝트 파일을 이름을 바꿉니다.  
  
2.  솔루션 탐색기에서 t4modelbusadapter를 MBProvider 솔루션에 추가 합니다.  솔루션 노드를 마우스 오른쪽 단추로 클릭 하 고  **추가**에서 다음을 클릭 하 고  **기존 프로젝트**.  
  
3.  T4ModelBusAdapter 프로젝트 노드를 마우스 오른쪽 단추로 클릭 한 다음 속성을 클릭 합니다.  프로젝트 속성 창에서 변경의  **어셈블리 이름** 및  **기본 네임 스페이스** 에 `Company.MBProvider.T4ModelBusAdapters`.  
  
4.  줄은 다음과 비슷하게 T4ModelBusAdapter 각 \*.tt 파일에 있는 네임 스페이스의 마지막 부분에 "T4"를 삽입 합니다.  
  
     `namespace <#= CodeGenerationUtilities.GetPackageNamespace(this.Dsl) #>.T4ModelBusAdapters`  
  
5.  에 있는 `DslPackage` 프로젝트, 프로젝트 참조를 추가 `T4ModelBusAdapter`.  
  
6.  아래에서 다음 줄을 추가 하는 Dslpackage\\source.extension.tt에서 `<Content>`.  
  
     `<MefComponent>|T4ModelBusAdapter|</MefComponent>`  
  
7.  에 있는 `T4ModelBusAdapter` 프로젝트, 참조를 추가 합니다.**Microsoft.VisualStudio.TextTemplating.Modeling.11.0**  
  
8.  T4modelbusadapter\\adaptermanager.tt를 엽니다.  
  
    1.  기본 클래스의 AdapterManagerBase 변경 <xref:Microsoft.VisualStudio.TextTemplating.Modeling.VsTextTemplatingModelingAdapterManager>.  이제 파일의이 부분을 다음과 같은.  
  
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
  
    2.  파일의 끝에 근처에 다음 추가 특성 클래스 AdapterManager 앞에 삽입 합니다.  
  
         `[Microsoft.VisualStudio.Modeling.Integration.HostSpecific(HostName)]`  
  
         결과 다음과 유사합니다.  
  
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
  
9. 클릭  **모든 템플릿 변환** 에 있는 제목 표시줄의 솔루션 탐색기입니다.  
  
10. 솔루션을 다시 빌드합니다.  F5 키를 누릅니다.  
  
11. DSL F5 키를 눌러 작동 하는지 확인 합니다.  실험적인 프로젝트에 `Sample.provider`.  실험 모드의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 인스턴스를 닫습니다.  
  
 이제 텍스트 템플릿 및 또한 일반 코드가이 DSL에 대 한 ModelBus 참조를 해결할 수 있습니다.  
  
#### DSL ModelBus 참조 도메인 속성을 구성 합니다.  
  
1.  최소한의 언어 솔루션 템플릿을 사용 하 여 새 DSL을 만듭니다.  MBConsumer 언어 이름과 파일 이름 확장명이 ".consume"를 설정 하십시오.  
  
2.  DSL 프로젝트에서 DSL MBProvider 어셈블리에 참조를 추가 합니다.  마우스 오른쪽 단추로 `MBConsumer\Dsl\References` 하 고 다음을 클릭  **참조 추가**.  에 있는  **찾아보기** 탭에서 찾습니다`MBProvider\Dsl\bin\Debug\Company.MBProvider.Dsl.dll`  
  
     다른 DSL을 사용 하 여 코드를 만들 수 있습니다.  여러 Dsl에 대 한 참조를 만들려면도 추가 합니다.  
  
3.  DSL 정의 다이어그램에서 다이어그램을 마우스 오른쪽 단추로 클릭 하 고 다음을 클릭  **사용 ModelBus**.  선택 대화 상자에서  **사용이 DSL는 Modelbus를 사용할 수**.  
  
4.  클래스에 `ExampleElement`, 새 도메인 속성 추가  `MBR`, 고 속성 창에서 해당 형식을 설정 합니다. `ModelBusReference`.  
  
5.  도메인 속성에서 다이어그램을 마우스 오른쪽 단추로 클릭 하 고 다음을 클릭  **특정 속성 편집 ModelBusReference**.  선택 대화 상자에서  **모델 요소**.  
  
     파일 대화 상자 필터를 다음과 같이 설정 합니다.  
  
     `Provider File|*.provide`  
  
     뒤의 부분 문자열 "&#124;" 파일 선택 대화 상자에 대 한 필터입니다.  사용 하 여 모든 파일을 허용 하도록 설정할 수 \* 있습니다. \*  
  
     에 있는  **모델 요소 형식** 목록에서 \(예를 들어, Company.MBProvider.Task\) DSL 공급자에 하나의 광물 클래스를 더 많은 도메인 이름을 입력 합니다.  이러한 추상 클래스가 될 수 있습니다.  목록이 비어 있으면 사용자가 모든 요소에 대 한 참조를 설정할 수 있습니다.  
  
6.  대화 상자를 닫습니다 및  **모든 템플릿 변환**.  
  
 다른 DSL의 요소에 대 한 참조를 포함할 수 있는 DSL을 만들었습니다.  
  
#### 솔루션에서 다른 파일에 대 한 ModelBus 참조 만들기  
  
1.  MBConsumer 솔루션에서 CTRL \+ f 5를 누릅니다.  실험적인 인스턴스를 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에 여는 **MBConsumer\\Debugging** 프로젝트입니다.  
  
2.  추가 복사본을 sample.provide에는 **MBConsumer\\Debugging** 프로젝트입니다.  이것은 ModelBus 참조를 동일한 솔루션에 있는 파일을 참조 하기 때문입니다.  
  
    1.  디버깅 프로젝트를 마우스 오른쪽 단추로 클릭 하 고  **추가**에서 다음을 클릭 하 고  **기존 항목**.  
  
    2.  에  **항목 추가** 대화 상자에서 필터를 설정  **모든 파일 \(\*. \*\)**.  
  
    3.  이동 `MBProvider\Debugging\Sample.provide` 하 고 다음을 클릭  **추가**.  
  
3.  `Sample.consume`를 엽니다.  
  
4.  하나의 예제에서는 도형을 클릭 하 고 속성 창에서 클릭  **\[...\]** 의 MBR 속성입니다.  대화 상자에서 누릅니다  **찾아보기** 를 선택 하 고 `Sample.provide`.  요소 창 작업 유형을 확장 한 요소 중 하나를 선택 합니다.  
  
5.  파일을 저장합니다.  
  
     \(아직 실험적인 인스턴스를 닫지 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]입니다.\)  
  
 ModelBus 참조 다른 모델의 요소를 포함 하는 모델을 만들었습니다.  
  
#### 텍스트 서식에 대 한 ModelBus 참조 확인  
  
1.  실험의 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 샘플 텍스트 서식 파일을 엽니다.  해당 내용을 다음과 같이 설정 합니다.  
  
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
  
     다음 사항에 유의하십시오.  
  
    1.  `hostSpecific` 및 `inherits` 의 특성은 `template` 지시문을 설정 해야 합니다.  
  
    2.  소비자 모델은 일반적인 방법으로 해당 DSL에 생성 된 지시문 프로세서를 통해 액세스할 수 있습니다.  
  
    3.  어셈블리 및 가져오기 지시문 ModelBus 및 종류의 DSL 공급자에 액세스할 수 있어야 합니다.  
  
    4.  많은 마샬링된 동일한 모델에 연결 되어 있음을 알고 있는 경우 Createadapter를 한 번만 호출 하는 것이 좋습니다.  
  
2.  템플릿을 저장하는 경우  결과 텍스트 파일 다음과 유사한 지 확인 하십시오.  
  
    ```  
  
    ExampleElement1   
    ExampleElement2   
         ExampleElement2 is linked to Task: Task2  
  
    ```  
  
#### 제스처 처리기에 대 한 ModelBus 참조 확인  
  
1.  실험적인 인스턴스를 닫고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 실행 중인 경우.  
  
2.  MBConsumer\\Dsl\\Custom.cs 이름이 지정 되 고 해당 콘텐츠를 다음과 같이 설정 파일을 추가 합니다.  
  
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
  
3.  Ctrl\+F5를 누릅니다.  
  
4.  실험의 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 열기 `Debugging\Sample.consume`.  
  
5.  셰이프를 두 번 클릭 합니다.  
  
     MBR 요소에 설정 된 경우 참조 된 모델을 엽니다 및 참조 된 요소를 선택 합니다.  
  
## 참고 항목  
 [Visual Studio Modelbus를 사용 하 여 모델 통합](../modeling/integrating-models-by-using-visual-studio-modelbus.md)   
 [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)
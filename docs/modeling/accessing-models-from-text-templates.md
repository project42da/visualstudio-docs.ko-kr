---
title: "텍스트 템플릿에서 모델에 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, 모델 액세스"
ms.assetid: cf65395a-0ca3-4826-89c7-b1869562685c
caps.latest.revision: 33
caps.handback.revision: 33
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 텍스트 템플릿에서 모델에 액세스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 서식 파일을 사용 하 여 보고서 파일, 소스 코드 파일 및 도메인 관련 언어 모델을 기반으로 하는 다른 텍스트 파일을 만들 수 있습니다.  텍스트 서식에 대 한 기본적인 정보를 참조 하십시오. [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md).  텍스트 템플릿을 DSL을 디버깅 하는 경우 시험 모드에서 작동 하지 및 또한 DSL을 배포한 컴퓨터에서 작동 합니다.  
  
> [!NOTE]
>  DSL 솔루션, 샘플 텍스트 템플릿 만들기 **\*.tt** 파일 디버깅 프로젝트에 생성 됩니다.  도메인 클래스의 이름을 변경 하면 이러한 템플릿이 더 이상 작동 하지.  그럼에도 불구 하 고 필요한 기본 지시문에는 한 DSL을 일치 하도록 업데이트할 수 있습니다 예를 제공 합니다.  
  
 텍스트 서식 파일로 모델에 액세스 하려면:  
  
-   템플릿 지시문의 상속 속성 설정 <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation>.  저장소에 있는 액세스를 제공합니다.  
  
-   지시문 프로세서 DSL에 대 한 액세스를 지정 합니다.  해당 도메인 클래스, 속성, 관계 텍스트 서식 파일의 코드에서 사용할 수 있도록 어셈블리를 DSL 로드 합니다.  또한 지정 하 여 모델 파일을 로드 합니다.  
  
 A `.tt` 파일은 다음 예제와 비슷한 디버깅 프로젝트에서 만든 새 사용자를 만들 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션에서 DSL 최소한의 언어 서식 파일입니다.  
  
```  
<#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
<#@ output extension=".txt" #>  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>  
  
This text will be output directly.  
  
This is the name of the model: <#= this.ModelRoot.Name #>  
  
Here is a list of elements in the model:  
<#  
  // When you change the DSL Definition, some of the code below may not work.  
  foreach (ExampleElement element in this.ExampleModel.Elements)  
  {#>  
<#= element.Name #>  
<#      
  }  
#>  
  
```  
  
 이 서식 파일에 대 한 다음 사항을 확인 합니다.  
  
-   템플릿을 도메인 클래스, 속성, DSL 정의에 정의 된 관계를 사용할 수 있습니다.  
  
-   서식 파일에서 지정한 모델 파일 로드는 `requires` 속성입니다.  
  
-   속성에서 `this` 루트 요소를 포함 합니다.  여기에서 코드를 다른 모델의 요소를 이동할 수 있습니다.  일반적으로 속성 이름을 루트 도메인 클래스를 DSL의 같습니다.  이 예제에서는 것입니다 `this.ExampleModel`.  
  
-   C\#에서 코드 조각을 작성 되는 언어는 것 이지만 모든 종류의 텍스트를 생성할 수 있습니다.  또는 해당 코드를 작성할 수 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 속성을 추가 하 여 `language="VB"` 에 있는 `template` 지시문입니다.  
  
-   추가 서식 파일을 디버깅할 수 `debug="true"` 에 있는 `template` 지시문입니다.  서식 파일의 다른 인스턴스에서 열립니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 예외가 발생 합니다.  디버거는 코드의 특정 지점에 중단 하려면 문을 삽입합니다`System.Diagnostics.Debugger.Break();`  
  
     자세한 내용은 [T4 텍스트 템플릿 디버깅](../modeling/debugging-a-t4-text-template.md)를 참조하십시오.  
  
## DSL 지시문 프로세서에 대 한  
 서식 파일을 DSL 정의에 정의 된 도메인 클래스를 사용할 수 있습니다.  이 일반적으로 템플릿 시작 근처에 표시 하는 지시문으로 가져오는 방법에 대 한.  앞의 예제는 다음입니다.  
  
```  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>  
```  
  
 지시문의 이름 \( `MyLanguage`,이 예제에서는\)를 DSL의 이름에서 파생 됩니다.  이 호출 하는  *지시문 프로세서* 를 DSL의 일부로 생성 됩니다.  해당 소스 코드를 찾을 수 있습니다 **Dsl\\GeneratedCode\\DirectiveProcessor.cs**.  
  
 DSL 지시문 프로세서 두 가지 주요 작업을 수행합니다.  
  
-   효과적으로 어셈블리 및 가져오기 지시문 참조를 DSL 서식 파일에 삽입 합니다.  도메인 클래스 템플릿 코드에서 사용할 수 있습니다.  
  
-   지정한 파일을 로드는 `requires` 매개 변수를 속성을 설정 하 고 `this` 에 로드 된 모델의 루트 요소를 나타냅니다.  
  
## 서식 파일을 실행 하기 전에 모델의 유효성 검사  
 템플릿을 실행 하기 전에 유효성을 검사 하는 모델이 될 수 있습니다.  
  
```  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1';validation='open|load|save|menu'" #>  
  
```  
  
 에 유의 하십시오.  
  
1.  `filename` 및 `validation` 매개 변수 구분 됩니다 ";" 하 고 있어야 다른 구분 기호 또는 공백을.  
  
2.  유효성 검사 범주의 목록을 실행 되는 유효성 검사 메서드를 결정 합니다.  여러 범주를 분리 해야 "&#124;" 하 고 있어야 다른 구분 기호 또는 공백을.  
  
 오류가 있으면 오류 창에 보고 됩니다 및 결과 파일에 오류 메시지가 포함 됩니다.  
  
##  <a name="Multiple"></a> 텍스트 서식 파일에서 여러 모델에 액세스  
  
> [!NOTE]
>  이 메서드는 여러 개의 모델에서 동일한 서식 파일을 읽을 수 있습니다 하지만 ModelBus 참조를 지원 하지 않습니다.  ModelBus 참조에 의해 상호 연결 되는 모델 읽기를 참조 하십시오. [텍스트 템플릿에서 Visual Studio ModelBus 사용](../modeling/using-visual-studio-modelbus-in-a-text-template.md).  
  
 같은 텍스트 서식 파일에서 두 개 이상의 모델에 액세스 하는 경우 각 모델에 대해 한 번 생성 된 지시문 프로세서를 호출 해야 합니다.  각 모델에는 파일 이름을 지정 해야 해당 `requires` 매개 변수.  루트 도메인 클래스에 대해 사용할 이름을 지정 합니다는 `provides` 매개 변수.  서로 다른 값을 지정 해야 합니다는 `provides` 각 지시문 호출의 매개 변수입니다.  예를 들어, Library.xyz, School.xyz, 및 Work.xyz 라는 세 가지 모델 파일이 있다고 가정 합니다.  같은 텍스트 서식 파일을 액세스 하려면 다음 것과 유사한 지시문 호출 세 가지를 작성 해야 합니다.  
  
```  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Library.xyz'" provides="ExampleModel=LibraryModel" #>  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='School.xyz'" provides="ExampleModel=SchoolModel" #>  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Work.xyz'" provides="ExampleModel=WorkModel" #>  
```  
  
> [!NOTE]
>  이 예제 코드는 최소한의 언어 솔루션 템플릿을 기반으로 하는 언어입니다.  
  
 모델 텍스트 서식 파일에서에 액세스 하려면 지금 다음 예제 코드와 유사한 코드를 작성할 수 있습니다.  
  
```c#  
<#  
foreach (ExampleElement element in this.LibraryModel.Elements)  
...  
foreach (ExampleElement element in this.SchoolModel.Elements)  
...  
foreach (ExampleElement element in this.WorkModel.Elements)  
...  
#>  
```  
  
```vb#  
<#  
For Each element As ExampleElement In Me.LibraryModel.Elements  
...  
For Each element As ExampleElement In Me.SchoolModel.Elements  
...  
For Each element As ExampleElement In Me.WorkModel.Elements  
...  
#>  
```  
  
## 모델을 동적으로 로드  
 런타임 시 로드 하려면 어떤 모델 확인 하려면 하면 모델 파일 동적으로 DSL 특정 지시문을 사용 하는 대신 프로그램 코드를 로드할 수 있습니다.  
  
 그러나 템플릿 코드는 DSL에 정의 된 도메인 클래스를 사용할 수 있도록 DSL 특정 지시문의 기능 중 하나는 DSL 네임 스페이스를 가져오는 것입니다.  이 지시문을 사용 하 고 있기 때문에 추가 해야 합니다 **\<assembly\>** 및 **\<import\>** 로드할 수 있는 모든 모델에 대 한 지시문입니다.  로드 될 수 있습니다 다른 모델로 모든 인스턴스가 같은 DSL의 경우 간단한 작업입니다.  
  
 사용 하 여 파일을 로드 하는 가장 효과적인 방법입니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus.  일반적인 시나리오에서 일반적인 방법으로는 첫 번째 모델을 로드 하는 DSL 특정 지시문 텍스트 서식 파일을 사용 합니다.  해당 모델은 다른 모델에 대 한 ModelBus 참조가 포함 됩니다.  Modelbus를 사용 하 여 참조 된 모델을 열고 특정 요소에 액세스할 수 있습니다.  자세한 내용은 [텍스트 템플릿에서 Visual Studio ModelBus 사용](../modeling/using-visual-studio-modelbus-in-a-text-template.md)를 참조하십시오.  
  
 경우도 있는 파일 이름만 모델 파일을 열려고 하는 덜 일반적인 시나리오에서 현재 수 있습니다 없습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트입니다.  이 경우에 설명 된 기술을 사용 하 여 파일을 열 수 있습니다 [방법: 프로그램 코드로 파일에서 모델 열기](../modeling/how-to-open-a-model-from-file-in-program-code.md).  
  
## 서식 파일에서 여러 파일을 생성합니다.  
 \-여러 파일을 생성 하는 경우 예를 들어, 모델에서 각 요소에 대해 별도 파일을 생성 하는 여러 가지 가능한 방법입니다.  기본적으로 각 서식 파일의 파일 하나만 생성 됩니다.  
  
### 긴 파일 분  
 이 방법에서는 구분 하 여 단일 파일을 생성 하려면 템플릿을 사용 합니다.  다음 파일을 부분으로 분할 합니다.  두 개의 템플릿, 단일 파일 및 다른 분할을 생성 하는 있습니다.  
  
 **LoopTemplate.t4**긴 단일 파일을 생성합니다.  클릭 하면 직접 해당 처리 되지 않아야 하기 때문에 파일 확장명이 ".t4" 되었습니다  **모든 템플릿 변환**.  이 서식 파일 세그먼트 구분 하는 구분 기호 문자열을 지정 하는 매개 변수를 사용 합니다.  
  
```  
<#@ template ninherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>  
<#@ parameter name="delimiter" type="System.String" #>  
<#@ output extension=".txt" #>  
<#@ MyDSL processor="MyDSLDirectiveProcessor" requires="fileName='SampleModel.mydsl1';validation='open|load|save|menu'" #>  
<#  
  // Create a file segment for each element:  
  foreach (ExampleElement element in this.ExampleModel.Elements)   
  {   
    // First item is the delimiter:  
#>  
<#= string.Format(delimiter, element.Id) #>  
  
   Element: <#= element.Name #>  
<#  
   // Here you generate more content derived from the element.  
  }  
#>  
  
```  
  
 `LoopSplitter.tt`호출 `LoopTemplate.t4`, 및 다음 결과 파일을 세그먼트로 분할 합니다.  모델 읽기 하지 않습니다 때문에이 템플릿을 모델링 템플릿을 사용할 수 없는지 확인 합니다.  
  
```  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ import namespace="Microsoft.VisualStudio.TextTemplating" #>  
<#@ import namespace="System.Runtime.Remoting.Messaging" #>  
<#@ import namespace="System.IO" #>  
  
<#  
  // Get the local path:  
  string itemTemplatePath = this.Host.ResolvePath("LoopTemplate.t4");  
  string dir = Path.GetDirectoryName(itemTemplatePath);  
  
  // Get the template for generating each file:  
  string loopTemplate = File.ReadAllText(itemTemplatePath);  
  
  Engine engine = new Engine();  
  
  // Pass parameter to new template:  
  string delimiterGuid = Guid.NewGuid().ToString();  
  string delimiter = "::::" + delimiterGuid + ":::";  
  CallContext.LogicalSetData("delimiter", delimiter + "{0}:::");   
  string joinedFiles = engine.ProcessTemplate(loopTemplate, this.Host);  
  
  string [] separateFiles = joinedFiles.Split(new string [] {delimiter}, StringSplitOptions.None);  
  
  foreach (string nameAndFile in separateFiles)   
  {   
     if (string.IsNullOrWhiteSpace(nameAndFile)) continue;  
     string[] parts = nameAndFile.Split(new string[]{":::"}, 2, StringSplitOptions.None);  
     if (parts.Length < 2) continue;  
#>  
 Generate: [<#= dir #>] [<#= parts[0] #>]  
<#  
     // Generate a file from this item:  
     File.WriteAllText(Path.Combine(dir, parts[0] + ".txt"), parts[1]);    
  }  
#>  
  
```
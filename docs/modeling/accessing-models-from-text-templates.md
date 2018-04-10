---
title: 텍스트 템플릿에서 모델에 액세스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
helpviewer_keywords:
- text templates, accessing models
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 3162350a9afbe7972c4e593049141f533517bdc3
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="accessing-models-from-text-templates"></a>텍스트 템플릿에서 모델에 액세스
텍스트 템플릿을 사용 하 여 보고서 파일, 소스 코드 파일 및 도메인 특정 언어 모델을 기반으로 하는 기타 텍스트 파일을 만들 수 있습니다. 텍스트 템플릿에 대 한 기본 정보에 대 한 참조 [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)합니다. 텍스트 템플릿 DSL를 디버깅할 때 실험적 모드에서 작동 하며 DSL 프로그램이 배포 되는 컴퓨터에도 작동 합니다.  
  
> [!NOTE]
>  DSL 솔루션, 샘플 텍스트 서식 파일을 만들 때  **\*.tt** 파일 디버깅 프로젝트에서 생성 됩니다. 도메인 클래스의 이름을 변경 하면 이러한 템플릿은 더 이상 작동 합니다. 그럼에도 불구 하 고 필요한 기본 지시문을 포함 하며 DSL 일치 하도록 업데이트할 수 있는 예제를 제공 합니다.  
  
 텍스트 템플릿에서 모델에 액세스 합니다 하:  
  
-   템플릿 지시문의 상속 속성을 설정 <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation>합니다. 이 저장소에 대 한 액세스를 제공합니다.  
  
-   액세스 하려는 DSL에 대 한 지시문 프로세서를 지정 합니다. 이렇게 하면 텍스트 서식 파일의 코드에서 해당 도메인 클래스, 속성 및 관계를 사용할 수 있도록 DSL에 대 한 어셈블리 로드 됩니다. 또한 사용자가 지정한 모델 파일을 로드 합니다.  
  
 A `.tt` 을 새로 만들 때 다음 예제와 비슷한 파일 디버깅 프로젝트에서 만들어집니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] DSL 최소 언어 서식 파일을 솔루션입니다.  
  
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
  
 이 서식 파일에 대해 다음 사항을 참고 하세요.  
  
-   도메인 클래스, 속성 및 관계 DSL 정의에 정의 된 템플릿을 צ ְ ײ 합니다.  
  
-   지정 하는 모델 파일을 로드 하는 서식 파일은 `requires` 속성입니다.  
  
-   속성에 `this` 루트 요소를 포함 합니다. 여기에서 코드 모델의 다른 요소를 탐색할 수 있습니다. 일반적으로 속성의 이름은 DSL의 루트 도메인 클래스와 동일 합니다. 이 예제에서는 `this.ExampleModel`입니다.  
  
-   코드 조각을 작성 되는 언어는 C#을 이지만 모든 종류의 텍스트를 생성할 수 있습니다. 는 코드를 작성 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 속성을 추가 하 여 `language="VB"` 에 `template` 지시문입니다.  
  
-   서식 파일을 디버깅 하려면 추가 `debug="true"` 에 `template` 지시문입니다. 서식 파일의 다른 인스턴스에서 열립니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 예외가 발생 합니다. 코드에서 특정 한 시점에 디버거를 중단 하려는 경우 끝에 구문을 삽입합니다 `System.Diagnostics.Debugger.Break();`  
  
     자세한 내용은 참조 [T4 텍스트 템플릿 디버그](../modeling/debugging-a-t4-text-template.md)합니다.  
  
## <a name="about-the-dsl-directive-processor"></a>DSL 지시문 프로세서에 대 한  
 서식 파일 DSL 정의에 정의 된 도메인 클래스를 사용할 수 있습니다. 일반적으로 서식 파일의 시작 부분을 표시 하는 지시문에 대 한 상태가 됩니다. 이전 예에서 값인 경우 다음과 같습니다.  
  
```  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>  
```  
  
 지시문의 이름 ( `MyLanguage`,이 예에서) DSL의 이름에서 파생 됩니다. 호출 된 *지시문 프로세서* DSL의 일부로 생성 된 합니다. 해당 소스 코드를 찾을 수 있습니다 **Dsl\GeneratedCode\DirectiveProcessor.cs**합니다.  
  
 DSL 지시문 프로세서 두 개의 주 작업을 수행합니다.  
  
-   효과적으로 DSL 참조 하는 서식 파일에 어셈블리 및 import 지시문을 삽입 합니다. 이렇게 하면 도메인 클래스 템플릿 코드에서 사용할 수 있습니다.  
  
-   지정 하는 파일을 로드는 `requires` 매개 변수 속성을 설정 하 고 `this` 로드 된 모델의 루트 요소를 참조 하는입니다.  
  
## <a name="validating-the-model-before-running-the-template"></a>서식 파일을 실행 하기 전에 모델 유효성 검사  
 서식 파일을 실행 하기 전에 유효성을 검사 하려면 모델을 발생할 수 있습니다.  
  
```  
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1';validation='open|load|save|menu'" #>  
  
```  
  
 다음 사항을 참고하세요.  
  
1.  `filename` 및 `validation` 매개 변수는으로 구분 되어 있습니다. ";"이 고 다른 구분 기호 또는 공백 이어야 합니다.  
  
2.  유효성 검사 범주 목록이 있는 유효성 검사 메서드가 실행 될 결정 합니다. 여러 범주와 구분 해야 "&#124;"이 고 다른 구분 기호 또는 공백 이어야 합니다.  
  
 오류가 발견 된 오류 창에 보고 됩니다 및 결과 파일에 오류 메시지가 포함 됩니다.  
  
##  <a name="Multiple"></a> 텍스트 템플릿에서 여러 모델에 액세스  
  
> [!NOTE]
>  이 방법을 사용 하면 같은 서식 파일에서 여러 모델을 읽을 수 있지만 ModelBus 참조를 지원 하지 않습니다. ModelBus 참조를 통해 상호 연결 하는 모델, 참조 [텍스트 템플릿에서 Visual Studio ModelBus를 사용 하 여](../modeling/using-visual-studio-modelbus-in-a-text-template.md)합니다.  
  
 동일한 텍스트 템플릿에서 둘 이상의 모델에 액세스 하려는 경우를 호출 해야 생성된 지시문 프로세서는 한 번 각 모델에 대 한. 각 모델의 파일 이름을 지정 해야 합니다는 `requires` 매개 변수입니다. 루트 도메인 클래스에 사용할 이름을 지정 해야 합니다는 `provides` 매개 변수입니다. 에 대 한 다른 값을 지정 해야 합니다는 `provides` 지시문 호출의 각 매개 변수입니다. 예를 들어 Library.xyz, School.xyz, 및 Work.xyz 라는 3 개의 모델 파일 있다고 가정 합니다. 동일한 텍스트 템플릿에서 액세스 하려면 다음과 유사한 세 지시문 호출이 작성 해야 합니다.  
  
```  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Library.xyz'" provides="ExampleModel=LibraryModel" #>  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='School.xyz'" provides="ExampleModel=SchoolModel" #>  
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Work.xyz'" provides="ExampleModel=WorkModel" #>  
```  
  
> [!NOTE]
>  이 예제 코드는 최소한의 언어 솔루션 템플릿을 기반으로 하는 언어에 대 한 합니다.  
  
 텍스트 템플릿에 모델에 액세스 하려면 다음 예에서 이제는 코드와 유사한 코드를 작성할 수 있습니다.  
  
```csharp  
<#  
foreach (ExampleElement element in this.LibraryModel.Elements)  
...  
foreach (ExampleElement element in this.SchoolModel.Elements)  
...  
foreach (ExampleElement element in this.WorkModel.Elements)  
...  
#>  
```  
  
```vb  
<#  
For Each element As ExampleElement In Me.LibraryModel.Elements  
...  
For Each element As ExampleElement In Me.SchoolModel.Elements  
...  
For Each element As ExampleElement In Me.WorkModel.Elements  
...  
#>  
```  
  
## <a name="loading-models-dynamically"></a>모델을 동적으로 로드  
 모델을 로드할 런타임 시 결정 하려는 경우 DSL 별 지시문을 사용 하는 대신, 프로그램 코드에서 모델 파일을 동적으로 로드할 수 있습니다.  
  
 그러나 DSL 관련 지시문의 기능 중 하나는 DSL 네임 스페이스를 가져오는 템플릿 코드는 해당 DSL에 정의 된 도메인 클래스를 사용할 수 있도록 합니다. 지시문을 사용 하지 않는 때문에 추가 해야  **\<어셈블리 >** 및  **\<가져올 >** 로드 될 수 있는 모든 모델에 대 한 지시문입니다. 로드 될 수 있는 서로 다른 모델은 동일한 DSL 함수의 모든 인스턴스의 경우 쉽습니다.  
  
 파일을 로드 하려면 가장 효과적인 메서드를 사용 하 여는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ModelBus 합니다. 일반적인 시나리오에서는 텍스트 템플릿을 일반적으로 첫 번째 모델을 로드할 수 DSL 별 지시문을 사용 합니다. 해당 모델에는 다른 모델로 ModelBus 참조가 포함 됩니다. 참조 되는 모델을 열고 특정 요소에 액세스 하려면 ModelBus를 사용할 수 있습니다. 자세한 내용은 참조 [텍스트 템플릿에서 Visual Studio ModelBus를 사용 하 여](../modeling/using-visual-studio-modelbus-in-a-text-template.md)합니다.  
  
 덜 일반적인 시나리오에서는 파일 이름에만 권한이 있는 모델 파일을 열려고 할 수 있으며 현재에서 수 없을 수도 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트. 이 경우에 설명 된 기술을 사용 하 여 파일을 열 수 있습니다 [하는 방법: 프로그램 코드 파일에서 모델 열기](../modeling/how-to-open-a-model-from-file-in-program-code.md)합니다.  
  
## <a name="generating-multiple-files-from-a-template"></a>서식 파일에서 여러 파일을 생성합니다.  
 여러 파일-을 생성 하려면 예를 들어 모델에서 각 요소에 대해 별도 파일을 생성 하려면 많은 경우 여러 가지 방법 합니다. 기본적으로 각 서식 파일에서 파일을 하나만 생성 됩니다.  
  
### <a name="splitting-a-long-file"></a>긴 파일 분  
 이 방법에서는 구분 기호로 구분 된 단일 파일을 생성 하는 템플릿을 사용 합니다. 다음 파일을 부분으로 분할 합니다. 단일 파일 및 다른 분할 하 여 생성 하는 두 템플릿이 있습니다.  
  
 **LoopTemplate.t4** 긴 단일 파일을 생성 합니다. 클릭할 때 직접에 하지 처리 해야 하기 때문에 파일 확장명이 ".t4" 것을 확인할 **모든 템플릿 변형**합니다. 이 서식 파일 세그먼트를 구분 하는 구분 기호 문자열을 지정 하는 매개 변수를 사용 합니다.  
  
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
  
 `LoopSplitter.tt` 호출 `LoopTemplate.t4`, 한 다음 해당 세그먼트에 결과 파일을 분할 합니다. 이 템플릿에 없습니다을 모델링 템플릿인 모델 읽을 때문에 확인 합니다.  
  
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
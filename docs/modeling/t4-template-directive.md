---
title: "T4 템플릿 지시문 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b0a8e04-6fee-4c6c-b086-e49fc728a3ed
caps.latest.revision: 10
author: alancameronwills
ms.author: awills
manager: douge
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
translationtype: Machine Translation
ms.sourcegitcommit: eb2ab9d49cdeb1ed71da8ef67841f7796862dc30
ms.openlocfilehash: ae369eacf934db165a10783bb59ad8a812f8c542
ms.lasthandoff: 02/22/2017

---
# <a name="t4-template-directive"></a>T4 템플릿 지시문
일반적으로 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] T4 텍스트 템플릿은 템플릿의 처리 방식을 지정하는 `template` 지시문으로 시작합니다. 하나의 텍스트 템플릿 및 템플릿이 포함된 파일에는 템플릿 지시문이 하나만 있어야 합니다.  
  
 텍스트 템플릿 작성의 일반적인 개요를 참조 하십시오. [T4 텍스트 템플릿 작성](../modeling/writing-a-t4-text-template.md)합니다.  
  
## <a name="using-the-template-directive"></a>template 지시문 사용  
  
```  
<#@ template [language="VB"] [compilerOptions="options"] [culture="code"] [debug="true"] [hostspecific="true"] [inherits="templateBaseClass"] [visibility="internal"] [linePragmas="false"] #>  
```  
  
 `template` 지시문에는 변환의 다양한 측면을 지정할 수 있도록 하는 몇 가지 특성이 있습니다. 모든 특성은 선택적입니다.  
  
## <a name="compileroptions-attribute"></a>compilerOptions 특성  
 예제:  
 `compilerOptions="optimize+"`  
  
 유효한 값은  
 유효한 컴파일러 옵션입니다.  
  
 전처리된 런타임 템플릿의 경우 무시됩니다.  
  
 이 옵션은 템플릿이 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vb_current_short](../debugger/includes/vb_current_short_md.md)]으로 변환된 경우 적용되며 결과 코드는 컴파일됩니다.  
  
## <a name="culture-attribute"></a>culture 특성  
 예제:  
 `culture="de-CH"`  
  
 유효한 값은  
 "", 기본값인 고정 문화권입니다.  
  
 xx-XX 형식의 문자열로 표현된 문화권. 예를 들어 en-US, ja-JP, de-CH, de-DE 등입니다. 자세한 내용은 <xref:System.Globalization.CultureInfo?displayProperty=fullName>.</xref:System.Globalization.CultureInfo?displayProperty=fullName> 을 참조 하십시오.  
  
 식 블록이 텍스트로 변환될 때 사용할 문화권을 지정하는 culture 특성입니다.  
  
## <a name="debug-attribute"></a>debug 특성  
 예제:  
 ```  
debug="true"  
```  
  
 유효한 값:  
 `true, false`. 기본값은 False입니다.  
  
 `debug` 특성이 `true`인 경우 중간 코드 파일에 디버거가 중단 또는 예외가 발생한 템플릿의 위치를 정확하게 식별할 수 있도록 하는 정보가 포함됩니다.  
  
 디자인 타임 템플릿의 경우 중간 코드 파일에 기록 됩니다 프로그램 **% TEMP %** 디렉터리입니다.  
  
 디버거에서 디자인 타임 템플릿을 실행 하려면 텍스트 템플릿을 저장 한 다음 솔루션 탐색기에서 텍스트 템플릿의 바로 가기 메뉴를 열고 선택한 **T4 템플릿 디버그**합니다.  
  
## <a name="hostspecific-attribute"></a>hostspecific 특성  
 예제:  
 ```  
hostspecific="true"  
```  
  
 유효한 값:  
 `true, false, trueFromBase`. 기본값은 False입니다.  
  
 이 특성의 값을 `true`로 설정하면 `Host`라는 속성이 텍스트 템플릿에서 생성된 클래스에 추가됩니다. 속성은 변환 엔진의 호스트에 대 한 참조 이며 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>.</xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> 로 선언 됨 사용자 지정 호스트를 정의한 경우에는 해당 호스트를 사용자 지정 호스트 형식으로 캐스팅할 수 있습니다.  
  
 이 속성의 형식이 호스트의 형식에 따라 달라지기 때문에 이 속성은 특정 호스트에서만 작동하는 텍스트 템플릿을 작성하는 경우에만 유용합니다. 에 적용 될 [디자인 타임 템플릿의](../modeling/design-time-code-generation-by-using-t4-text-templates.md), 하지 않고 [타임 템플릿](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.  
  
 `hostspecific`이 `true`이고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용하고 있는 경우 `this.Host`를 IServiceProvider로 캐스팅하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 기능에 액세스할 수 있습니다. `Host.ResolvePath(filename)`를 사용하여 프로젝트에서 파일의 절대 경로를 가져올 수도 있습니다. 예:  
  
```c#  
<#@ template debug="false" hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#@ import namespace="EnvDTE" #>  
<#@ import namespace="System.IO" #>  
<# // Get the Visual Studio API as a service:  
 DTE dte = ((IServiceProvider)this.Host).GetCOMService(typeof(DTE)) as DTE;    
#>  
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>  
  
<#  
 // Find a path within the current project:  
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));  
#>  
Content of myFile is:  
<#= myFile #>  
  
```  
  
 `inherits`와 `hostspecific` 특성을 함께 사용하는 경우, 파생 클래스에 host="trueFromBase"를 지정하고 기본 클래스에는 host="true"를 지정하십시오. 이렇게 하면 생성된 코드에서 `Host` 속성의 이중 정의를 피할 수 있습니다.  
  
## <a name="language-attribute"></a>language 특성  
 예제:  
 `language="VB"`  
  
 유효한 값은  
 `C#`(기본값)  
  
 `VB`  
  
 Language 특성은 언어를 지정 합니다 ([!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]) 문 및 식 블록에서 소스 코드에 사용 하도록 합니다. 출력이 생성되는 중간 코드 파일에서 이 언어가 사용됩니다. 이 언어는 템플릿에서 생성되는 언어와 관련이 없으며 모든 종류의 텍스트일 수 있습니다.  
  
 예:  
  
```vb#  
<#@ template language="VB" #>  
<#@ output extension=".txt" #>  
Squares of numbers:  
<#  
  Dim number As Integer  
  For number = 1 To 4  
#>  
  Square of <#= number #> is <#= number * number #>  
<#  
  Next number  
#>  
  
```  
  
## <a name="inherits-attribute"></a>inherits 특성  
 템플릿의 프로그램 코드가 텍스트 템플릿에서 생성될 수도 있는 다른 클래스에서 상속하도록 지정할 수 있습니다.  
  
### <a name="inheritance-in-a-run-time-preprocessed-text-template"></a>전처리된 런타임 텍스트 템플릿의 상속  
 런타임 텍스트 템플릿 간에 상속을 사용하여 여러 파생 변형이 있는 기본 템플릿을 만들 수 있습니다. 런타임 템플릿은 해당는 **사용자 지정 도구** 속성으로 설정 **TextTemplatingFilePreprocessor**합니다. 런타임 템플릿에서는 응용 프로그램에서 호출하여 템플릿에 정의된 텍스트를 만들 수 있는 코드를 생성합니다. 자세한 내용은 참조 [T4 텍스트 템플릿을 사용 하 여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)합니다.  
  
 `inherits` 특성을 지정하지 않으면 기본 클래스 및 파생 클래스가 텍스트 템플릿에서 생성됩니다. `inherits` 특성을 지정하면 파생 클래스만 생성됩니다. 기본 클래스를 직접 작성할 수 있지만 기본 클래스에서 파생 클래스에 사용되는 메서드를 제공해야 합니다.  
  
 또한 전처리된 다른 템플릿을 기본 클래스로 지정하는 것이 더 일반적입니다. 기본 템플릿에서는 파생 템플릿의 텍스트를 인터리브할 수 있는 공통 텍스트 블록을 제공합니다. 클래스 기능 블록 `<#+ ... #>`을 사용하여 텍스트 조각이 들어 있는 메서드를 정의할 수 있습니다. 예를 들어 출력 텍스트의 프레임워크를 기본 템플릿에 둠으로써 파생 템플릿에 재정의할 수 있는 가상 메서드를 제공할 수 있습니다.  
  
 전처리된 런타임 텍스트 템플릿 BaseTemplate.tt:  
 ```scr  
This is the common header.  
<#   
  SpecificFragment1();   
#>  
A common central text.  
<#   
  SpecificFragment2();   
#>  
This is the common footer.  
<#+   
  // Declare abstract methods  
  protected virtual void SpecificFragment1() { }  
  protected virtual void SpecificFragment2() { }  
#>  
  
```  
  
 전처리된 런타임 텍스트 템플릿 DerivedTemplate1.tt:  
 ```c#  
<#@ template language="C#" inherits="BaseTemplate" #>  
<#   
  // Run the base template:  
  base.TransformText();  
#>  
<#+  
// Provide fragments specific to this derived template:  
protected override void SpecificFragment1()  
{  
#>  
   Fragment 1 for DerivedTemplate1  
<#+  
}  
protected override void SpecificFragment2()  
{  
#>  
   Fragment 2 for DerivedTemplate1  
<#+  
}  
#>  
  
```  
  
 DerivedTemplate1을 호출할 응용 프로그램 코드:  
 ```c#  
Console.WriteLine(new DerivedTemplate().TransformText());  
```  
  
 결과 출력:  
 ```  
This is the common header.  
   Fragment 1 for DerivedTemplate1  
A common central text.  
   Fragment 2 for DerivedTemplate1  
This is the common footer.  
```  
  
 서로 다른 프로젝트에서 기본 클래스와 파생 클래스를 빌드할 수 있습니다. 기본 프로젝트 또는 어셈블리를 파생 프로젝트의 참조에 추가해야 합니다.  
  
 직접 작성한 일반 클래스를 기본 클래스로 사용할 수도 있습니다. 기본 클래스는 파생 클래스에 사용되는 메서드를 제공합니다.  
  
> [!WARNING]
>  `inherits`와 `hostspecific` 특성을 함께 사용하는 경우, 파생 클래스에 hostspecific="trueFromBase"를 지정하고 기본 클래스에는 host="true"를 지정하십시오. 이렇게 하면 생성된 코드에서 `Host` 속성의 이중 정의를 피할 수 있습니다.  
  
### <a name="inheritance-in-a-design-time-text-template"></a>디자인 타임 텍스트 템플릿의 상속  
 디자인 타임 텍스트 서식 파일은 파일의 **사용자 지정 도구** 로 설정 된 **TextTemplatingFileGenerator**합니다. 이 템플릿에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트의 일부를 구성하는 코드 또는 텍스트의 출력 파일을 생성합니다. 출력 파일을 생성하기 위해 먼저 템플릿이 중간 프로그램 코드 파일로 변환되며, 대개 이 파일은 보이지 않습니다. `inherits` 특성은 이 중간 코드를 위한 기본 클래스를 지정합니다.  
  
 디자인 타임 텍스트 템플릿의 경우 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>.</xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName> 에서 파생 된 클래스는 기본 클래스를 지정할 수 있습니다. `<#@assembly#>` 지시문을 사용하여 기본 클래스가 들어 있는 프로젝트나 어셈블리를 로드합니다.  
  
 자세한 내용은 참조 [상속에 텍스트 "템플릿" Gareth Jones 블로그의](http://go.microsoft.com/fwlink/?LinkId=208373)합니다.  
  
## <a name="linepragmas-attribute"></a>LinePragmas 특성  
 예제:  
 `linePragmas="false"`  
  
 유효한 값은  
 `true`(기본값)  
  
 `false`  
  
 이 특성을 false로 설정하면 생성된 코드에서 줄 번호를 식별하는 태그가 제거됩니다. 즉, 컴파일러에서 생성된 코드의 줄 번호를 사용하여 모든 오류를 보고하는 것을 의미합니다. 이렇게 하면 텍스트 템플릿 또는 생성된 코드를 디버깅하도록 선택할 수 있어 더 많은 디버깅 옵션을 사용할 있습니다.  
  
 이 특성은 소스 코드 컨트롤에 따라 프로그램에서 산만한 병합을 유발하는 정확한 파일 이름을 찾는 경우 유용할 수 있습니다.  
  
## <a name="visibility-attribute"></a>표시 유형 특성  
 예제:  
 `visibility="internal"`  
  
 유효한 값은  
 `public`(기본값)  
  
 `internal`  
  
 런타임 텍스트 템플릿에서 생성된 클래스의 표시 유형 특성을 설정합니다. 기본적으로 클래스는 사용자 코드의 공용 API에 속하지만 `visibility="internal"`을 설정하여 사용자의 코드만 텍스트 생성 클래스를 사용할 수 있도록 지정할 수 있습니다.


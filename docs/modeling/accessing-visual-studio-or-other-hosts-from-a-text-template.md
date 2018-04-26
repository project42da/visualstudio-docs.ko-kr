---
title: 텍스트 템플릿에서 Visual Studio 또는 다른 호스트 액세스
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 657abba976e0f0d167651943289296d340981e62
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="access-visual-studio-or-other-hosts-from-a-text-template"></a>텍스트 템플릿에서 Visual Studio 또는 다른 호스트 액세스

텍스트 템플릿에서 서식 파일을 실행 하는 호스트에 의해 노출 되는 메서드 및 속성을 사용할 수 있습니다. Visual Studio는 호스트의 예시입니다.

> [!NOTE]
> 일반 텍스트 템플릿에 있지만에 없는 호스트 메서드 및 속성을 사용할 수 *전처리* 텍스트 템플릿.

## <a name="obtain-access-to-the-host"></a>호스트에 대 한 액세스 권한을 얻기

호스트에 액세스 하려면 설정 `hostspecific="true"` 에 `template` 지시문입니다. 에서는 이제 `this.Host`, 형식이 있는 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>합니다. <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> 형식에는 파일 이름을 확인 하 고 오류를 기록 하는, 예를 들어 사용할 수 있는 멤버가 있습니다.

### <a name="resolve-file-names"></a>파일 이름을 확인합니다

텍스트 템플릿 기준으로 파일의 전체 경로 찾으려면 `this.Host.ResolvePath()`합니다.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>
```

### <a name="display-error-messages"></a>오류 메시지를 표시 합니다.

이 예제에서는 서식 파일을 변환 하는 경우 메시지를 로깅합니다. 오류에 추가 됩니다 호스트에 Visual Studio 경우는 **오류 목록**합니다.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.CodeDom.Compiler" #>
<#
  string message = "test message";
  this.Host.LogErrors(new CompilerErrorCollection()
    { new CompilerError(
       this.Host.TemplateFile, // Identify the source of the error.
       0, 0, "0",   // Line, column, error ID.
       message) }); // Message displayed in error window.
#>
```

## <a name="use-the-visual-studio-api"></a>Visual Studio API를 사용 하 여

Visual Studio에서 텍스트 템플릿을 실행 하는 경우 사용할 수 있습니다 `this.Host` Visual Studio 및 패키지나 로드 되는 확장에서 제공 하는 액세스 서비스에 있습니다.

설정 hostspecific = "true" 및 캐스팅 `this.Host` 를 <xref:System.IServiceProvider>합니다.

이 예제에서는 Visual Studio API 가져옵니다 <xref:EnvDTE.DTE>, 서비스로:

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#
 IServiceProvider serviceProvider = (IServiceProvider)this.Host;
 DTE dte = serviceProvider.GetService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>
```

## <a name="use-hostspecific-with-template-inheritance"></a>HostSpecific 템플릿 상속 사용

지정 `hostspecific="trueFromBase"` 사용 하는 경우는 `inherits` 특성을 지정 하는 서식 파일에서 상속 하는 경우 및 `hostspecific="true"`합니다. 이렇게 하지 않으면 발생할 수 있습니다 하는 경고는 컴파일러 속성 `Host` 가 두 번 선언 되었습니다.
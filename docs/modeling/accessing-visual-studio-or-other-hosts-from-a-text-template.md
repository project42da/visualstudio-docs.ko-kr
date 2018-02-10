---
title: "텍스트 템플릿에서 Visual Studio 또는 다른 호스트 액세스 | Microsoft Docs"
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
ms.openlocfilehash: cd72a2838e9dd7a903e5cf76aac30e2922708872
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>텍스트 템플릿에서 Visual Studio 또는 다른 호스트 액세스
텍스트 템플릿에서 같은 서식 파일을 실행 하는 호스트에 의해 노출 되는 속성과 메서드를 사용할 수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
 이 일반 텍스트 템플릿에 하지 전처리 된 텍스트 템플릿에 적용 됩니다.  
  
## <a name="obtaining-access-to-the-host"></a>호스트에 대 한 액세스를 획득  
 설정 `hostspecific="true"` 에 `template` 지시문입니다. 이렇게 하면 사용 하 여 `this.Host`, 형식이 있는 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>합니다. 이 형식에 사용할 수 있는, 예를 들어 파일 이름을 확인 하 고 오류를 기록 하는 멤버가 있습니다.  
  
### <a name="resolving-file-names"></a>파일 이름 확인  
 텍스트 템플릿 기준으로 파일의 전체 경로 찾으려면이 사용 합니다. Host.ResolvePath() 합니다.  
  
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
  
### <a name="displaying-error-messages"></a>오류 메시지 표시  
 이 예제에서는 서식 파일을 변환 하는 경우 메시지를 로깅합니다. 호스트가 있는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 오류 창에 추가 됩니다.  
  
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
  
## <a name="using-the-visual-studio-api"></a>Visual Studio API를 사용 하 여  
 텍스트 템플릿을 실행 하는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]를 사용할 수 있습니다 `this.Host` 에서 제공 하는 액세스 서비스에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지나 확장 로드 되 고 있습니다.  
  
 설정 hostspecific = "true" 및 캐스팅 `this.Host` 를 <xref:System.IServiceProvider>합니다.  
  
 이 예제는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] API <xref:EnvDTE.DTE>, 서비스로:  
  
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
  
## <a name="using-hostspecific-with-template-inheritance"></a>HostSpecific 템플릿 상속 사용  
 지정 `hostspecific="trueFromBase"` 사용 하는 경우는 `inherits` 특성을 지정 하는 서식 파일에서 상속 하는 경우 및 `hostspecific="true"`합니다. 이 효과에 컴파일러 경고를 방지할 수 있는 속성 `Host` 가 두 번 선언 되었습니다.
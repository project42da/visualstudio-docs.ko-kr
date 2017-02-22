---
title: "텍스트 템플릿에서 Visual Studio 또는 다른 호스트 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a68886da-7416-4785-8145-3796bb382cba
caps.latest.revision: 5
caps.handback.revision: 5
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 텍스트 템플릿에서 Visual Studio 또는 다른 호스트 액세스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

텍스트 템플릿에서는 템플릿을 실행하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]과 같은 호스트에서 노출하는 메서드 및 속성을 사용할 수 있습니다.  
  
 이 내용은 일반 텍스트 템플릿에 적용되며 전처리된 텍스트 템플릿에는 적용되지 않습니다.  
  
## 호스트에 대한 액세스 획득  
 `template` 지시문에서 `hostspecific="true"`를 설정합니다.  이렇게 하면 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost> 형식의 `this.Host`를 사용할 수 있습니다.  이 형식에는 파일 이름을 확인하고 오류를 기록할 때와 같은 경우 사용할 수 있는 멤버가 있습니다.  
  
### 파일 이름 확인  
 텍스트 템플릿에 관련된 파일의 전체 경로를 찾으려면 this.Host.ResolvePath\(\)를 사용합니다.  
  
```c#  
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
  
### 오류 메시지 표시  
 이 예제에서는 템플릿을 변환할 때 메시지를 기록합니다.  호스트가 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]인 경우에는 해당 메시지가 오류 창에 추가됩니다.  
  
```c#  
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
  
## Visual Studio API 사용  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 텍스트 템플릿을 실행하는 경우 `this.Host`를 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 제공하는 서비스와 로드된 패키지나 확장에 액세스할 수 있습니다.  
  
 hostspecific\="true"를 설정하고 `this.Host`를 <xref:System.IServiceProvider>로 캐스팅합니다.  
  
 이 예제에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] API인 <xref:EnvDTE.DTE>를 서비스로 가져옵니다.  
  
```c#  
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
  
## 템플릿을 사용 하 여 상속을 사용 하 여 hostSpecific  
 지정 `hostspecific="trueFromBase"` 도 사용 하는 경우는 `inherits` 특성 및 지정 템플릿에서 상속 `hostspecific="true"`.  이 컴파일러 경고 하는 효과 피할 수 있는 속성이 `Host` 두 번 선언 되었습니다.
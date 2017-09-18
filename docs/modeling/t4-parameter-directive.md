---
title: "T4 매개 변수 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d590387-1d9d-40a5-a72c-65fae7a8bdf3
caps.latest.revision: 3
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 3
---
# T4 매개 변수 지시문
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 텍스트 템플릿에서 `parameter` 지시문은 외부 컨텍스트로부터 전달된 값에서 초기화되는 속성을 템플릿 코드에 선언합니다.  텍스트 변환을 호출하는 코드를 작성하는 경우 이러한 값을 설정할 수 있습니다.  
  
## parameter 지시문 사용  
  
```  
<#@ parameter type="Full.TypeName" name="ParameterName" #>  
```  
  
 `parameter` 지시문은 외부 컨텍스트로부터 전달된 값에서 초기화되는 속성을 템플릿 코드에 선언합니다.  텍스트 변환을 호출하는 코드를 작성하는 경우 이러한 값을 설정할 수 있습니다.  이 값은 `Session` 사전이나 <xref:System.Runtime.Remoting.Messaging.CallContext>에 전달될 수 있습니다.  
  
 원격 가능 형식의 매개 변수를 선언할 수 있습니다.  즉, 매개 변수 형식은 <xref:System.SerializableAttribute>를 사용하여 선언되거나 <xref:System.MarshalByRefObject>에서 파생되어야 합니다.  이를 통해 템플릿이 처리되는 AppDomain으로 매개 변수 값이 전달될 수 있습니다.  
  
 예를 들어 다음 내용이 포함된 텍스트 템플릿을 작성할 수 있습니다.  
  
```  
<#@ template language="C#" #>  
  
<#@ parameter type="System.Int32" name="TimesToRepeat" #>  
  
<# for (int i = 0; i < TimesToRepeat; i++) { #>  
Line <#= i #>  
<# } #>  
  
```  
  
## 템플릿에 매개 변수 값 전달  
 메뉴 명령이나 이벤트 처리기와 같은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Extension을 작성하는 경우 다음과 같이 텍스트 템플릿 서비스를 사용하여 템플릿을 처리할 수 있습니다.  
  
```c#  
// Get a service provider – how you do this depends on the context:  
IServiceProvider serviceProvider = dte; // or dslDiagram.Store, for example   
// Get the text template service:  
ITextTemplating t4 = serviceProvider.GetService(typeof(STextTemplating)) as ITextTemplating;  
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;  
// Create a Session in which to pass parameters:  
host.Session = host.CreateSession();  
// Add parameter values to the Session:  
session["TimesToRepeat"] = 5;  
// Process a text template:  
string result = t4.ProcessTemplate("MyTemplateFile.t4",  
  System.IO.File.ReadAllText("MyTemplateFile.t4"));  
  
```  
  
## 호출 컨텍스트에 값 전달  
 또는 <xref:System.Runtime.Remoting.Messaging.CallContext>에 논리 데이터로 값을 전달할 수 있습니다.  
  
 다음 예제에서는 두 방법을 사용하여 값을 전달합니다.  
  
```c#  
ITextTemplating t4 = this.Store.GetService(typeof(STextTemplating)) as ITextTemplating;  
ITextTemplatingSessionHost host = t4 as ITextTemplatingSessionHost;  
host.Session = host.CreateSession();  
// Pass a value in Session:  
host.Session["p1"] = 32;  
// Pass another value in CallContext:  
System.Runtime.Remoting.Messaging.CallContext.LogicalSetData("p2", "test");  
  
// Process a small template inline:  
string result = t4.ProcessTemplate("",   
   "<#@parameter type=\"System.Int32\" name=\"p1\"#>"  
 + "<#@parameter type=\"System.String\" name=\"p2\"#>"  
 + "Test <#=p1#> <#=p2#>");  
  
// Result value is:  
//     Test 32 test  
  
```  
  
## 전처리된 런타임 텍스트 템플릿에 값 전달  
 일반적으로는 전처리된 런타임 텍스트 템플릿에 `<#@parameter#>` 지시문을 사용할 필요가 없습니다.  대신 생성된 코드에 대한 추가 생성자나 설정 가능한 속성을 정의하여 이를 통해 매개 변수 값을 전달합니다.  자세한 내용은 [T4 텍스트 템플릿을 사용하여 런타임 텍스트 생성](../modeling/run-time-text-generation-with-t4-text-templates.md)을 참조하십시오.  
  
 그러나 런타임 템플릿에 `<#@parameter>`를 사용하려는 경우 세션 사전을 사용하여 값을 템플릿에 전달할 수 있습니다.  예를 들어 `PreTextTemplate1`이라는 전처리된 템플릿으로 파일을 만든 경우  다음 코드를 사용하여 프로그램에서 템플릿을 호출할 수 있습니다.  
  
```c#  
PreTextTemplate1 t = new PreTextTemplate1();  
t.Session = new Microsoft.VisualStudio.TextTemplating.TextTemplatingSession();  
t.Session["TimesToRepeat"] = 5;  
// Add other parameter values to t.Session here.  
t.Initialize(); // Must call this to transfer values.  
string resultText = t.TransformText();  
  
```  
  
## TextTemplate.exe에서 인수 가져오기  
  
> [!IMPORTANT]
>  `parameter` 지시문은 `TextTransform.exe` 유틸리티의 `–a` 매개 변수에 설정된 값을 검색하지 않습니다.  해당 값을 가져오려면 `template` 지시문에 `hostSpecific="true"`를 설정하고 `this.Host.ResolveParameterValue("","","argName")`를 사용합니다.
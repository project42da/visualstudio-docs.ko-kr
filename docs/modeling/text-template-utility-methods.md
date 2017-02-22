---
title: "텍스트 템플릿 유틸리티 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "텍스트 템플릿, 유틸리티 메서드"
ms.assetid: 8c11f9f7-678b-4f0c-b634-dc78fda699d1
caps.latest.revision: 50
caps.handback.revision: 50
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 텍스트 템플릿 유틸리티 메서드
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 텍스트 템플릿에서 코드를 작성할 때 항상 사용할 수 있는 몇 가지 메서드가 있습니다.  이러한 메서드는 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>에서 정의됩니다.  
  
> [!TIP]
>  전처리된 텍스트 템플릿이 아닌 일반 텍스트 템플릿에서 호스트 환경에 의해 제공되는 다른 메서드 및 서비스를 사용할 수도 있습니다.  예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 로드된 패키지에서 제공되는 서비스를 가져오고 파일 경로를 확인하고 오류를 기록할 수 있습니다.  자세한 내용은 [Accessing Visual Studio from a Text Template](http://msdn.microsoft.com/ko-kr/0556f20c-fef4-41a9-9597-53afab4ab9e4)를 참조하십시오.  
  
## 쓰기 메서드  
 식 코드 블록을 사용하는 대신 `Write()` 및 `WriteLine()` 메서드를 사용하여 표준 코드 블록 안에 텍스트를 추가할 수 있습니다.  다음 두 코드 블록은 기능면에서 동일합니다.  
  
##### 식 블록이 포함된 코드 블록  
  
```  
<#  
int i = 10;  
while (i-- > 0)  
    { #>  
        <#= i #>  
    <# }  
#>  
```  
  
##### WriteLine\(\)을 사용하는 코드 블록  
  
```  
<#   
    int i = 10;  
    while (i-- > 0)  
    {   
        WriteLine((i.ToString()));  
    }  
#>  
```  
  
 중첩 제어 구조에서 긴 코드 블록 안에 식 블록 대신 이러한 유틸리티 메서드 중 하나를 사용하는 것이 유용할 수 있습니다.  
  
 `Write()` 및 `WriteLine()` 메서드에는 두 오버로드가 있습니다. 한 오버로드는 단일 문자열 매개 변수를 사용하고 다른 오버로드는 합성 형식 문자열과 이 문자열에 포함할 개체의 배열을 사용합니다\(`Console.WriteLine()` 메서드와 유사함\).  `WriteLine()`을 사용하는 다음 두 경우는 기능면에서 동일합니다.  
  
```  
<#  
    string msg = "Say: {0}, {1}, {2}";  
    string s1 = "hello";  
    string s2 = "goodbye";  
    string s3 = "farewell";  
  
    WriteLine(msg, s1, s2, s3);  
    WriteLine("Say: hello, goodbye, farewell");  
#>   
```  
  
## 들여쓰기 메서드  
 들여쓰기 메서드를 사용하여 텍스트 템플릿의 출력 형식을 지정할 수 있습니다.  <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> 클래스에는 텍스트 템플릿에서 현재 들여쓰기를 보여 주는 `CurrentIndent` 문자열 속성과 추가된 들여쓰기의 목록인 `indentLengths` 필드가 있습니다.  `PushIndent()` 메서드를 사용하여 들여쓰기를 추가하고 `PopIndent()` 메서드를 사용하여 들여쓰기를 뺄 수 있습니다.  모든 들여쓰기를 제거하려면 `ClearIndent()` 메서드를 사용합니다.  다음 코드 블록에서는 이러한 메서드의 사용 방법을 보여 줍니다.  
  
```  
<#  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
    ClearIndent();  
    WriteLine(CurrentIndent + "Hello");  
    PushIndent("    ");  
    WriteLine(CurrentIndent + "Hello");  
#>  
```  
  
 이 코드 블록은 다음과 같이 출력됩니다.  
  
```  
Hello  
        Hello  
                Hello  
Hello  
        Hello  
```  
  
## 오류 및 경고 메서드  
 오류 및 경고 유틸리티 메서드를 사용하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 오류 목록에 메시지를 추가할 수 있습니다.  예를 들어, 다음 코드에서는 오류 메시지를 오류 목록에 추가합니다.  
  
```  
<#  
  try  
  {  
    string str = null;  
    Write(str.Length.ToString());  
  }  
  catch (Exception e)  
  {  
    Error(e.Message);  
  }  
#>    
```  
  
## 호스트 및 서비스 공급자 액세스  
 `this.Host` 속성을 사용하여 템플릿을 실행하는 호스트에서 노출하는 속성에 액세스할 수 있습니다.  `this.Host`를 사용하려면 `<@template#>` 지시문에서 `hostspecific` 특성을 설정해야 합니다.  
  
 `<#@template ...  hostspecific="true" #>`  
  
 `this.Host`의 형식은 템플릿이 실행되는 호스트의 형식에 따라 달라집니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 실행되는 템플릿에서 `this.Host`를 `IServiceProvider`로 캐스팅하여 IDE와 같은 서비스에 액세스할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
```  
  
## 여러 유틸리티 메서드 집합 사용  
 텍스트 생성 프로세스의 일부로, 템플릿 파일이 클래스로 변환됩니다. 이 클래스는 항상 `GeneratedTextTransformation`으로 명명되며 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>에서 상속합니다.  다른 메서드 집합을 대신 사용하려면 사용자 고유의 클래스를 작성하고 템플릿 지시문에서 지정할 수 있습니다.  이 클래스는 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>에서 상속해야 합니다.  
  
```  
<#@ template inherits="MyUtilityClass" #>  
```  
  
 `assembly` 지시문을 사용하여 컴파일된 클래스를 찾을 수 있는 어셈블리를 참조할 수 있습니다.
---
title: 텍스트 템플릿 유틸리티 메서드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, utility methods
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 37e268313aa6662ca250aed36be193864bbf0ed5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="text-template-utility-methods"></a>텍스트 템플릿 유틸리티 메서드

Visual Studio 텍스트 템플릿의 코드를 작성할 때 항상 사용할 수 있는 방법은 여러 가지가 있습니다. 에 정의 된 이러한 메서드가 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>합니다.

> [!TIP]
> 또한 다른 메서드 및 일반 하지 전처리 된 텍스트 템플릿의 호스트 환경에서 제공 하는 서비스를 사용할 수 있습니다. 예를 들어 파일 경로 확인, 오류를 기록할 수 있고 Visual Studio에서 제공 되는 서비스를 가져올 패키지를 로드 합니다. 자세한 내용은 참조 [텍스트 템플릿에서 Visual Studio에 액세스](http://msdn.microsoft.com/0556f20c-fef4-41a9-9597-53afab4ab9e4)합니다.
  
## <a name="write-methods"></a>Write 메서드

사용할 수는 `Write()` 및 `WriteLine()` 식 코드 블록을 사용 하는 대신 표준 코드 블록 내에 텍스트를 추가 하는 메서드. 다음 두 코드 블록은 기능적으로 같습니다.  
  
### <a name="code-block-with-an-expression-block"></a>식 블록으로 코드 블록  
  
```  
<#  
int i = 10;  
while (i-- > 0)  
    { #>  
        <#= i #>  
    <# }  
#>  
```  
  
### <a name="code-block-using-writeline"></a>WriteLine()를 사용 하 여 코드 블록  
  
```  
<#   
    int i = 10;  
    while (i-- > 0)  
    {   
        WriteLine((i.ToString()));  
    }  
#>  
```  
  
 중첩된 제어 구조에서 긴 코드 블록 안에 식 블록 대신 이러한 유틸리티 메서드 중 하나를 사용 하는 것이 유용할 수 있습니다.  
  
 `Write()` 및 `WriteLine()` 메서드는 두 개의 오버 로드를 갖고, 합성 형식 문자열 및 문자열에 포함할 개체의 배열을 사용 하는 단일 문자열 매개 변수 및 1을 사용 하는 하나 (같은 `Console.WriteLine()` 메서드). 다음 두 가지 용도 `WriteLine()` 기능적으로 동일 합니다.  
  
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
  
## <a name="indentation-methods"></a>들여쓰기 메서드

 텍스트 서식 파일의 출력 형식을 들여쓰기 메서드를 사용할 수 있습니다. <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation> 클래스에는 `CurrentIndent` 문자열 텍스트 템플릿에 현재 들여쓰기를 보여 주는 속성 및 `indentLengths` 필드 추가 된 들여쓰기의 목록입니다. 사용 하 여 들여쓰기를 추가할 수는 `PushIndent()` 메서드를 사용 하 여 들여쓰기 뺍니다는 `PopIndent()` 메서드. 모든 들여쓰기를 제거 하려는 경우 사용 하 여는 `ClearIndent()` 메서드. 다음 코드 블록에서는 이러한 메서드의 사용을 보여 줍니다.  
  
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
  
 이 코드 블록은 다음과 같은 출력을 생성합니다.  
  
```  
Hello  
        Hello  
                Hello  
Hello  
        Hello  
```  
  
## <a name="error-and-warning-methods"></a>오류 및 경고 메서드  
 Visual Studio 오류 목록에 메시지를 추가할 오류 및 경고 유틸리티 메서드를 사용할 수 있습니다. 예를 들어 다음 코드는 오류 목록에는 오류 메시지를 추가 합니다.  
  
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
  
## <a name="access-to-host-and-service-provider"></a>호스트와 서비스 공급자에 대 한 액세스  
 속성 `this.Host` 여 템플릿을 실행 하는 호스트에서 노출 하는 속성에 대 한 액세스를 제공할 수 있습니다. 사용 하도록 `this.Host`를 설정 해야 `hostspecific` 특성에 `<@template#>` 지시문:  
  
 `<#@template ... hostspecific="true" #>`  
  
 유형의 `this.Host` 템플릿이 실행 되는 호스트의 형식에 따라 달라 집니다. Visual Studio에서 실행 되는 서식 파일에서 캐스팅할 수 있습니다 `this.Host` 를 `IServiceProvider` IDE와 같은 서비스에 대 한 액세스 권한을 얻으려고 합니다. 예를 들어:  
  
```  
EnvDTE.DTE dte = (EnvDTE.DTE) ((IServiceProvider) this.Host)  
                       .GetService(typeof(EnvDTE.DTE));  
```  
  
## <a name="using-a-different-set-of-utility-methods"></a>다양 한 유틸리티 메서드를 사용 하 여  
 텍스트 생성 프로세스의 일환으로, 서식 파일은 라고 하는 클래스로 변환 `GeneratedTextTransformation`에서 상속 하 고 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>합니다. 다른 사용 하려는 경우 대신 메서드 집합이 작성 클래스를 직접 하 고 있습니다 template 지시문에 지정 합니다. 클래스에서 상속 해야 <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation>합니다.  
  
```  
<#@ template inherits="MyUtilityClass" #>  
```  
  
 사용 하 여는 `assembly` 지시문 컴파일된 클래스를 찾을 수 있는 어셈블리를 참조할 수 있습니다.
---
title: "T4 텍스트 템플릿을 사용하여 런타임 텍스트 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "전처리 텍스트 템플릿 프로젝트 항목"
  - "텍스트 템플릿, 런타임에 파일 생성"
  - "텍스트 템플릿, TransformText() 메서드"
  - "TextTemplatingFilePreprocessor 사용자 지정 도구"
ms.assetid: 79b4b3c6-a9a7-4446-b6fd-e2388fc6b05f
caps.latest.revision: 22
caps.handback.revision: 22
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# T4 텍스트 템플릿을 사용하여 런타임 텍스트 생성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

하면 텍스트 문자열에서 런타임에 응용 프로그램에서 사용 하 여 생성할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 런타임 텍스트 템플릿.  응용 프로그램을 실행하는 컴퓨터에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]가 없어도 됩니다.  컴파일 타임에 템플릿을 런타임에 실행 되는 코드를 생성 하므로 런타임 템플릿 "전처리 텍스트 템플릿" 라고도 합니다.  
  
 각 템플릿에는 생성된 문자열에 나타날 텍스트와 프로그램 코드의 조각이 혼합되어 있습니다.  프로그램 조각은 문자열의 변수 부분에 대한 값을 제공하며 조건적 부분과 반복되는 부분도 제어합니다.  
  
 예를 들어 HTML 보고서를 만드는 응용 프로그램에서 다음 템플릿을 사용할 수 있습니다.  
  
```  
<#@ template language="C#" #>  
<html><body>  
<h1>Sales for Previous Month</h2>  
<table>  
    <# for (int i = 1; i <= 10; i++)  
       { #>  
         <tr><td>Test name <#= i #> </td>  
             <td>Test value <#= i * i #> </td> </tr>  
    <# } #>  
 </table>  
This report is Company Confidential.  
</body></html>  
```  
  
 템플릿은 변수 부분이 프로그램 코드로 대체된 HTML 페이지입니다.  HTML 페이지의 정적 프로토타입을 작성하여 해당 페이지의 디자인을 시작할 수 있습니다.  그런 다음 테이블 및 기타 변수 부분을 각각의 경우마다 달라지는 콘텐츠를 생성하는 프로그램 코드로 바꿀 수 있습니다.  
  
 응용 프로그램에서 템플릿을 사용하면 출력의 최종 형식을 일련의 긴 쓰기 문에서 확인하는 것보다 더 쉽게 확인할 수 있습니다.  더 쉽고 안정적으로 출력 형식을 변경할 수 있습니다.  
  
## 응용 프로그램에서 런타임 텍스트 템플릿 만들기  
  
#### 런타임 텍스트 템플릿을 만들려면  
  
1.  솔루션 탐색기에서 프로젝트의 바로 가기 메뉴에서 선택  **추가**에서  **새 항목**.  
  
2.  에  **새 항목 추가** 선택 대화 상자에서  **런타임 텍스트 서식 파일**.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 **Common Items\\General** 아래에서 확인합니다.  
  
3.  템플릿 파일의 이름을 입력합니다.  
  
    > [!NOTE]
    >  템플릿 파일 이름은 생성된 코드에서 클래스 이름으로 사용되므로  공백이나 문장 부호를 포함해서는 안 됩니다.  
  
4.  선택  **추가**.  
  
     확장명이 **.tt**인 새 파일이 만들어집니다.  이 파일의 **사용자 지정 도구** 속성이 **TextTemplatingFilePreprocessor**로 설정됩니다.  다음 줄이 포함:  
  
    ```  
    <#@ template language="C#" #>  
    <#@ assembly name="System.Core" #>  
    <#@ import namespace="System.Linq" #>  
    <#@ import namespace="System.Text" #>  
    <#@ import namespace="System.Collections.Generic" #>  
    ```  
  
## 기존 파일을 런타임 템플릿으로 변환  
 템플릿을 만드는 좋은 방법은 기존 출력 예제를 변환하는 것입니다.  예를 들어, 응용 프로그램에서 HTML 파일을 생성할 경우 일반 HTML 파일을 만들어 시작할 수 있습니다.  파일이 올바르게 작동하고 파일의 모양이 올바른지 확인한 다음  파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트에 포함하고 템플릿으로 변환합니다.  
  
#### 기존 텍스트 파일을 런타임 템플릿으로 변환하려면  
  
1.  파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트에 포함합니다.  솔루션 탐색기에서 프로젝트의 바로 가기 메뉴에서 선택  **추가**에서  **기존 항목**.  
  
2.  파일의 **사용자 지정 도구** 속성을 **TextTemplatingFilePreprocessor**로 설정합니다.  솔루션 탐색기에서 해당 파일의 바로 가기 메뉴에서 선택  **속성이**.  
  
    > [!NOTE]
    >  이 속성이 이미 설정되어 있는 경우 **TextTemplatingFileGenerator**가 아니라 **TextTemplatingFilePreprocessor**인지 확인합니다.  이 현상은 확장명이 이미 **.tt**인 파일을 포함하는 경우 발생할 수 있습니다.  
  
3.  파일 확장명을 **.tt**로 변경합니다.  이는 선택적 단계이지만 잘못된 편집기에서 파일을 여는 것을 방지하는 데 도움이 됩니다.  
  
4.  파일 이름의 주 부분에서 공백이나 문장 부호를 모두 제거합니다.  예를 들어, "My Web Page.tt"는 잘못되었지만 "MyWebPage.tt"는 올바릅니다.  파일 이름은 생성된 코드에서 클래스 이름으로 사용됩니다.  
  
5.  파일의 시작 부분에 다음 코드를 삽입합니다.  Visual Basic 프로젝트에서 작업하는 경우에는 "C\#"을 "VB"로 바꿉니다.  
  
     `<#@ template language="C#" #>`  
  
## 런타임 템플릿의 콘텐츠  
  
### 템플릿 지시문  
 템플릿의 첫 줄을 다음과 같이 파일을 만들 당시와 동일하게 유지합니다.  
  
 `<#@ template language="C#" #>`  
  
 language 매개 변수는 프로젝트의 언어에 따라 달라집니다.  
  
### 일반 콘텐츠  
 응용 프로그램에서 생성하도록 할 텍스트를 포함하도록 **.tt** 파일을 편집합니다.  예를 들면 다음과 같습니다.  
  
```  
<html><body>  
<h1>Sales for January</h2>  
<!-- table to be inserted here -->  
This report is Company Confidential.  
</body></html>  
```  
  
### 포함된 프로그램 코드  
 `<#`과 `#>` 사이에 프로그램 코드를 삽입할 수 있습니다.  예를 들면 다음과 같습니다.  
  
```c#  
<table>  
    <# for (int i = 1; i <= 10; i++)  
       { #>  
         <tr><td>Test name <#= i #> </td>  
             <td>Test value <#= i * i #> </td> </tr>  
    <# } #>  
 </table>  
```  
  
```vb#  
<table>  
<#  
    For i As Integer = 1 To 10  
#>  
    <tr><td>Test name <#= i #> </td>  
      <td>Test value <#= i*i #> </td></tr>  
<#  
    Next  
#>  
</table>  
  
```  
  
 문은 `<# ... #>` 사이에 삽입되고 식은 `<#= ... #>` 사이에 삽입됩니다.  자세한 내용은 [T4 텍스트 템플릿 쓰기](../modeling/writing-a-t4-text-template.md)을 참조하십시오.  
  
## 템플릿 사용  
  
### 템플릿에서 빌드된 코드  
 **.tt** 파일을 저장할 때마다 보조 **.cs** 또는 **.vb** 파일이 생성됩니다.  솔루션 탐색기에서 이 파일을 보려면 **.tt** 파일 노드를 확장합니다.  Visual Basic 프로젝트에서는 솔루션 탐색기 도구 모음에서 **모든 파일 표시**를 클릭한 후 노드를 확장할 수 있습니다.  
  
 이 보조 파일에는 `TransformText()`라는 메서드가 포함된 partial 클래스가 들어 있습니다.  응용 프로그램에서 이 메서드를 호출할 수 있습니다.  
  
### 런타임에 텍스트 생성  
 응용 프로그램 코드에서 다음과 같은 호출을 사용하여 템플릿의 내용을 생성할 수 있습니다.  
  
```c#  
MyWebPage page = new MyWebPage();  
String pageContent = page.TransformText();  
System.IO.File.WriteAllText("outputPage.html", pageContent);  
  
```  
  
```vb#  
Dim page = New My.Templates.MyWebPage  
Dim pageContent = page.TransformText()  
System.IO.File.WriteAllText("outputPage.html", pageContent)  
  
```  
  
 생성된 클래스를 특정 네임스페이스에 두려면 텍스트 템플릿 파일의 **사용자 지정 도구 네임스페이스** 속성을 설정합니다.  
  
### 런타임 텍스트 템플릿 디버깅  
 디버깅 하 고 런타임 텍스트 서식 파일 같은 방식으로 일반 코드를 테스트 합니다.  
  
 텍스트 서식 파일에는 중단점을 설정할 수 있습니다.  디버깅 모드에서 Visual Studio 응용 프로그램을 시작 하는 경우, 코드를 단계별로 실행 하 고 일반적인 방법으로 조사식 식 평가 수 있습니다.  
  
### 생성자에 매개 변수 전달  
 일반적으로 템플릿에서는 응용 프로그램의 다른 부분에서 데이터를 가져와야 합니다.  이 작업을 쉽게 수행하기 위해 템플릿에서 빌드된 코드는 partial 클래스입니다.  프로젝트의 다른 파일에 동일한 클래스의 또 다른 부분을 만들 수 있습니다.  이 파일에는 템플릿에 포함된 코드와 응용 프로그램의 나머지 부분에서 액세스할 수 있는 매개 변수, 속성 및 함수와 함께 생성자가 포함될 수 있습니다.  
  
 예를 들어, 별도의 파일 **MyWebPageCode.cs**를 만들 수 있습니다.  
  
```c#  
partial class MyWebPage  
{  
    private MyData m_data;  
    public MyWebPage(MyData data) { this.m_data = data; }}  
```  
  
 템플릿 파일 **MyWebPage.tt**에서 다음 코드를 작성할 수 있습니다.  
  
```c#  
<h2>Sales figures</h2>  
<table>  
<# foreach (MyDataItem item in m_data.Items)   
   // m_data is declared in MyWebPageCode.cs  
   { #>  
      <tr><td> <#= item.Name #> </td>  
          <td> <#= item.Value #> </td></tr>  
<# } // end of foreach  
#>  
</table>  
```  
  
 응용 프로그램에서 이 템플릿을 사용하려면  
  
```c#  
MyData data = ...;  
MyWebPage page = new MyWebPage(data);  
String pageContent = page.TransformText();  
System.IO.File.WriteAllText("outputPage.html", pageContent);  
```  
  
#### Visual Basic의 생성자 매개 변수  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 **MyWebPageCode.vb**라는 별도의 파일에 다음 내용이 포함되어 있습니다.  
  
```vb#  
Namespace My.Templates  
  Partial Public Class MyWebPage  
    Private m_data As MyData  
    Public Sub New(ByVal data As MyData)  
      m_data = data  
    End Sub  
  End Class  
End Namespace  
```  
  
 템플릿 파일에는 다음 내용이 포함되어 있습니다.  
  
```vb#  
<#@ template language="VB" #>  
<html><body>  
<h1>Sales for January</h2>  
<table>  
<#  
    For Each item In m_data.Items  
#>  
    <tr><td>Test name <#= item.Name #> </td>  
      <td>Test value <#= item.Value #> </td></tr>  
<#  
    Next  
#>  
</table>  
This report is Company Confidential.  
</body></html>  
  
```  
  
 그리고 다음과 같이 생성자에 매개 변수를 전달하여 템플릿이 호출됩니다.  
  
```vb#  
Dim data = New My.Templates.MyData  
    ' Add data values here ....  
Dim page = New My.Templates.MyWebPage(data)  
Dim pageContent = page.TransformText()  
System.IO.File.WriteAllText("outputPage.html", pageContent)  
  
```  
  
#### 템플릿 속성에 데이터 전달  
 데이터를 템플릿에 전달하는 다른 방법은 공용 속성을 partial 클래스 정의의 템플릿 클래스에 추가하는 것입니다.  응용 프로그램에서 `TransformText()`를 호출하기 전에 속성을 설정할 수 있습니다.  
  
 부분 정의의 템플릿 클래스에 필드를 추가할 수도 있습니다.  이렇게 하면 템플릿을 연속으로 실행하는 사이에 데이터를 전달할 수 있습니다.  
  
### 코드에 partial 클래스 사용  
 대부분의 개발자는 템플릿에서 큰 코드 본문을 작성하지 않는 쪽을 선호합니다.  대신 템플릿 파일과 이름이 동일한 partial 클래스에 메서드를 정의합니다.  템플릿에서 해당 메서드를 호출합니다.  이런 방식으로 템플릿에서 대상 출력 문자열이 어떻게 표시될지 분명하게 보여 줍니다.  결과 모양에 대한 논의를 표시되는 데이터를 만드는 논리와 분리할 수 있습니다.  
  
### 어셈블리 및 참조  
 템플릿 코드에서 .NET 어셈블리나 **System.Xml.dll** 등의 다른 어셈블리를 참조하도록 하려면 프로젝트의 **참조**에 일반적인 방식으로 어셈블리를 추가해야 합니다.  
  
 `using` 문과 동일한 방식으로 네임스페이스를 가져오려면 `import` 지시문을 사용하여 가져올 수 있습니다.  
  
```  
<#@ import namespace="System.Xml" #>  
```  
  
 이러한 지시문은 파일의 시작 부분에서 `<#@template` 지시문 바로 뒤에 배치되어야 합니다.  
  
### 공유 콘텐츠  
 몇몇 템플릿에서 공유되는 텍스트가 있는 경우 이 텍스트를 별도의 파일에 두고 이 텍스트가 나타나야 하는 각 파일에 포함할 수 있습니다.  
  
```  
<#@include file="CommonHeader.txt" #>  
```  
  
 포함된 콘텐츠에는 프로그램 코드와 일반 텍스트가 혼합되어 있을 수 있으며 다른 include 지시문 및 다른 지시문이 포함될 수 있습니다.  
  
 include 지시문은 템플릿 파일이나 포함된 파일의 텍스트 내의 어느 곳에서든 사용할 수 있습니다.  
  
### 런타임 텍스트 템플릿 간 상속  
 기본 클래스 템플릿\(추상 클래스 템플릿일 수 있음\)을 작성하여 런타임 템플릿 간에 콘텐츠를 공유할 수 있습니다.  사용의 `inherits` 매개 변수는 `<@#template#>` 다른 런타임 템플릿 클래스를 참조 하는 지시문입니다.  
  
#### 상속 패턴: 기본 메서드의 조각  
 다음에 나오는 예제에 사용되는 패턴에서 다음과 같은 사항을 확인합니다.  
  
-   기본 클래스 `SharedFragments`는 클래스 기능 블록 `<#+ ... #>` 내에 메서드를 정의합니다.  
  
-   기본 클래스에는 일반 텍스트가 포함되어 있지 않습니다.  대신 기본 클래스의 모든 텍스트 블록이 클래스 기능 메서드 내부에서 사용됩니다.  
  
-   파생 클래스는 `SharedFragments`에 정의된 메서드를 호출합니다.  
  
-   응용 프로그램은 파생 클래스의 `TextTransform()` 메서드를 호출하지만 기본 클래스 `SharedFragments`를 변환하지 않습니다.  
  
-   런타임 텍스트 템플릿을 기본 클래스와 파생 클래스는: 즉,에서  **사용자 지정 도구** 속성을 설정  **TextTemplatingFilePreprocessor**.  
  
 **SharedFragments.tt:**  
  
```c#  
<#@ template language="C#" #>  
<#+  
protected void SharedText(int n)  
{  
#>  
   Shared Text <#= n #>  
<#+  
}  
// Insert more methods here if required.  
#>  
  
```  
  
 **MyTextTemplate1.tt:**  
  
```c#  
<#@ template language="C#" inherits="SharedFragments" #>  
begin 1  
   <# SharedText(2); #>  
end 1  
  
```  
  
 **MyProgram.cs:**  
  
```c#  
...   
MyTextTemplate1 t1  = new MyTextTemplate1();  
string result = t1.TransformText();  
Console.WriteLine(result);  
```  
  
 **결과 출력:**  
  
```  
begin 1  
    Shared Text 2  
end 1  
```  
  
#### 상속 패턴: 기본 본문의 텍스트  
 템플릿 상속을 사용하는 이 다른 방법에서는 대량의 텍스트가 기본 템플릿에 정의됩니다.  파생 템플릿에서는 기본 콘텐츠에 맞는 데이터 및 텍스트 조각을 제공합니다.  
  
 **AbstractBaseTemplate1.tt:**  
  
```c#  
<#@ template language="C#" #>  
  
Here is the description for this derived template:  
  <#= this.Description #>  
  
Here is the fragment specific to this derived template:  
<#   
  this.PushIndent("  ");  
  SpecificFragment(42);   
  this.PopIndent();  
#>  
End of common template.  
<#+   
  // State set by derived class before calling TextTransform:  
  protected string Description = "";  
  // 'abstract' method to be defined in derived classes:  
  protected virtual void SpecificFragment(int n) { }  
#>  
  
```  
  
 **DerivedTemplate1.tt:**  
  
```c#  
<#@ template language="C#" inherits="AbstractBaseTemplate1" #>  
<#   
  // Set the base template properties:  
  base.Description = "Description for this derived class";   
  
  // Run the base template:  
  base.TransformText();  
  
#>  
End material for DerivedTemplate1.  
  
<#+  
// Provide a fragment specific to this derived template:  
  
protected override void SpecificFragment(int n)  
{  
#>  
   Specific to DerivedTemplate1 : <#= n #>  
<#+  
}  
#>  
  
```  
  
 **응용 프로그램 코드:**  
  
```c#  
...   
DerivedTemplate1 t1 = new DerivedTemplate1();  
string result = t1.TransformText();  
Console.WriteLine(result);  
```  
  
 **결과 출력:**  
  
```  
Here is the description for this derived template:  
  Description for this derived class  
  
Here is the fragment specific to this derived template:  
     Specific to DerivedTemplate1 : 42  
End of common template.  
End material for DerivedTemplate1.  
```  
  
## 관련 항목  
 디자인 타임 템플릿: 템플릿을 사용하여 응용 프로그램의 일부가 되는 코드를 생성하려면 [T4 텍스트 템플릿을 사용하여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)을 참조하십시오.  
  
 컴파일 타임에 템플릿과 해당 콘텐츠 위치 결정 됩니다 모든 응용 프로그램에서 런타임 서식 파일을 사용할 수 있습니다.  그러나 런타임에 변경되는 템플릿에서 텍스트를 생성하는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Extension을 작성하려면 [VS 확장에서 텍스트 변환 호출](../modeling/invoking-text-transformation-in-a-vs-extension.md)을 참조하십시오.  
  
## 참고 항목  
 [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)   
 [T4 텍스트 템플릿 쓰기](../modeling/writing-a-t4-text-template.md)   
 [이해 T4: 텍스트 템플릿 Oleg 동기화가 전처리](http://www.olegsych.com/2009/09/t4-preprocessed-text-templates/)
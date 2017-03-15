---
title: "연습: 모델에 액세스 하는 텍스트 템플릿 디버깅 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af46a7fe-6b98-4d3d-b816-0bbf8e81e220
caps.latest.revision: 6
author: alancameronwills
ms.author: awills
manager: douge
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 7bbe2b592dc315bc0885e1f1ca4c890e4e66255d
ms.lasthandoff: 02/22/2017

---
# <a name="walkthrough-debugging-a-text-template-that-accesses-a-model"></a>연습: 모델에 액세스하는 텍스트 템플릿 디버깅
을 수정 하거나 도메인별 언어 솔루션에서 텍스트 템플릿을 추가 하는 경우 엔진은 생성된 된 코드를 컴파일하는 경우 또는 소스 코드에 템플릿이 변환 하는 경우 오류가 발생할 수 있습니다. 다음 연습에서는 텍스트 템플릿을 디버그 하려면 할 수 있는 작업 중 일부를 보여 줍니다.  
  
> [!NOTE]
>  텍스트에 대 한 자세한 내용은 템플릿 일반적으로 참조 [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)합니다. 텍스트 템플릿 디버깅 하는 방법에 대 한 자세한 내용은 참조 [연습: 텍스트 템플릿 디버깅](http://msdn.microsoft.com/Library/5c3fd3b7-c110-4e86-a22f-d5756be6b94f)합니다.  
  
## <a name="creating-a-domain-specific-language-solution"></a>도메인별 언어 솔루션 만들기  
 이 절차에서는 다음과 같은 특징이 있는 도메인별 언어 솔루션을 만듭니다.  
  
-   이름: DebuggingTestLanguage  
  
-   솔루션 템플릿을: 최소 언어  
  
-   파일 확장명:.ddd  
  
-   회사 이름: Fabrikam  
  
 도메인별 언어 솔루션을 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: 도메인별 언어 솔루션 만들기](../modeling/how-to-create-a-domain-specific-language-solution.md)합니다.  
  
## <a name="creating-a-text-template"></a>텍스트 템플릿 만들기  
 텍스트 서식 파일을 솔루션에 추가 합니다.  
  
#### <a name="to-create-a-text-template"></a>텍스트 템플릿을 만들려면  
  
1.  솔루션을 빌드하고 디버거에서 실행을 시작 합니다. (에 **빌드** 메뉴 클릭 **솔루션 다시 빌드**, 선택한 다음는 **디버그** 메뉴 클릭 **디버깅 시작**.) Visual Studio의 새 인스턴스 디버깅 프로젝트를 엽니다.  
  
2.  라는 텍스트 파일을 추가 `DebugTest.tt` 디버깅 프로젝트에 있습니다.  
  
3.  다음 사항을 확인는 **사용자 지정 도구** DebugTest.tt의 속성이 `TextTemplatingFileGenerator`합니다.  
  
## <a name="debugging-directives-that-access-a-model-from-a-text-template"></a>텍스트 템플릿에서 모델에 액세스 하는 디버깅 지시문  
 문 및 텍스트 템플릿의 식에서 모델에 액세스할 수 있습니다, 전에 생성된 된 지시문 프로세서를 먼저 호출 해야 합니다. 생성 된 지시문 프로세서를 호출을 통해 클래스 모델에서 텍스트 템플릿 코드에 사용할 수 있는 속성으로. 자세한 내용은 참조 [텍스트 템플릿에서 모델에 액세스](../modeling/accessing-models-from-text-templates.md)합니다.  
  
 다음 절차에서 잘못 된 지시문 이름과 잘못 된 속성 이름을 디버깅 합니다.  
  
#### <a name="to-debug-an-incorrect-directive-name"></a>잘못 된 지시문 이름을 디버깅 하려면  
  
1.  DebugTest.tt의 코드를 다음 코드로 바꿉니다.  
  
    > [!NOTE]
    >  코드에 오류가 있습니다. 디버깅을 위해 오류를 도입 되었습니다.  
  
    ```c#  
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
  
    Model: <#= this.ExampleModel #>  
    <#  
    foreach (ExampleElement element in this.ExampleModel.Elements)   
    {   
    #>   
        Element: <#= element.Name #>  
    <#   
    }  
    #>  
    ```  
  
    ```vb#  
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
  
    Model: <#= Me.ExampleModel #>  
    <#  
    For Each element as ExampleElement in Me.ExampleModel.Elements  
    #>   
        Element: <#= element.Name #>  
    <#   
    Next  
    #>  
    ```  
  
2.  **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     **오류 목록** 창에서이 오류를 표시 합니다.  
  
     **'DebuggingTestLanguageDirectiveProcessor' 라는 프로세서 'modelRoot' 지시문을 지원 하지 않습니다. 변환을 실행 되지 않습니다.**  
  
     이 경우 지시문 호출에 잘못 된 지시문 이름 포함 되어 있습니다. 사용자가 지정한 `modelRoot` 지시문 이름 이지만 올바른 지시문 이름 그대로 `DebuggingTestLanguage`합니다.  
  
3.  오류를 두 번 클릭은 **오류 목록** 창에서 코드로 이동 합니다.  
  
4.  하도록 지시문 이름을 변경 하는 코드를 수정 하려면 `DebuggingTestLanguage`합니다.  
  
     변경 내용은 강조 표시 됩니다.  
  
    ```c#  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
    ```  
  
    ```vb#  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
    ```  
  
5.  **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     이제 시스템 텍스트 템플릿을 변환 하 고 해당 출력 파일을 생성 합니다. 모든 오류가 표시 되지 것입니다는 **오류 목록** 창입니다.  
  
#### <a name="to-debug-an-incorrect-property-name"></a>잘못 된 속성 이름을 디버깅 하려면  
  
1.  DebugTest.tt의 코드를 다음 코드로 바꿉니다.  
  
    > [!NOTE]
    >  코드에 오류가 있습니다. 디버깅을 위해 오류를 도입 되었습니다.  
  
    ```c#  
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= this.ExampleModel #>  
    <#  
    foreach (ExampleElement element in this.ExampleModel.Elements)   
    {   
    #>   
        Element: <#= element.Name #>  
    <#   
    }  
    #>  
    ```  
  
    ```vb#  
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= Me.ExampleModel #>  
    <#  
    For Each element as ExampleElement in Me.ExampleModel.Elements  
    #>   
        Element: <#= element.Name #>  
    <#   
    Next  
    #>  
    ```  
  
2.  에 **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     **오류 목록** 창이 나타나고 이러한 오류 중 하나가 표시 됩니다.  
  
     (C#)  
  
     **변환을 컴파일하는 중: Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation' 'ExampleModel'에 대 한 정의 포함 하지 않습니다**  
  
     (Visual Basic)  
  
     **변환을 컴파일하는 중: 'ExampleModel'의 구성원이 아닙니다. ' Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation'.**  
  
     이 경우 텍스트 템플릿 코드가 올바르지 않은 속성 이름을 포함합니다. 사용자가 지정한 `ExampleModel` 속성 이름 하지만 올바른 속성 이름이 `LibraryModel`합니다. 올바른 속성 이름을 찾을 수는 다음 코드에 나와 있는 것 처럼 매개 변수를 제공 합니다.  
  
    ```  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
    ```  
  
3.  코드를 이동 하는 오류 목록 창에 오류를 두 번 클릭 합니다.  
  
4.  코드를 수정 하려면 속성 이름으로 변경 `LibraryModel` 텍스트 템플릿 코드에서.  
  
     변경 내용은 강조 표시 됩니다.  
  
    ```c#  
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= this.LibraryModel #>  
    <#  
    foreach (ExampleElement element in this.LibraryModel.Elements)   
    {   
    #>   
        Element: <#= element.Name #>  
    <#   
    }  
    #>  
    ```  
  
    ```vb#  
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= Me.LibraryModel #>  
    <#  
    For Each element as ExampleElement in Me.LibraryModel.Elements  
    #>   
        Element: <#= element.Name #>  
    <#   
    Next  
    #>  
    ```  
  
5.  **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     이제 시스템 텍스트 템플릿을 변환 하 고 해당 출력 파일을 생성 합니다. 모든 오류가 표시 되지 것입니다는 **오류 목록** 창입니다.

---
title: '연습: 생성된 지시문 프로세서에 호스트 연결'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- walkthroughs [text templates], connecting host to processor
- text templates, custom directive hosts
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 994a1b0677930128d36c4a3218f0231879b7a43e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-connecting-a-host-to-a-generated-directive-processor"></a>연습: 생성된 지시문 프로세서에 호스트 연결
텍스트 템플릿을 처리 하는 고유 호스트를 작성할 수 있습니다. 기본 사용자 지정 호스트에 설명 된 [연습: 사용자 지정 텍스트 템플릿 호스트 만들기](../modeling/walkthrough-creating-a-custom-text-template-host.md)합니다. 여러 개의 출력 파일로 생성 하는 등의 함수를 추가 하려면 해당 호스트를 확장할 수 있습니다.

 이 연습에서는 지시문 프로세서를 호출 하는 텍스트 템플릿을 지원 되도록 사용자 지정 호스트를 확장 합니다. 도메인 특정 언어를 정의 하는 경우에 생성 한 *지시문 프로세서* 도메인 모델에 대 한 합니다. 지시문 프로세서를 사용 하면 쉽게 어셈블리를 쓰고 서식 파일의 지시문을 가져올 필요가 없도록 하는 모델에 액세스 하는 템플릿을 작성할 수 있습니다.

> [!WARNING]
>  이 연습은 [연습: 사용자 지정 텍스트 템플릿 호스트 만들기](../modeling/walkthrough-creating-a-custom-text-template-host.md)합니다. 먼저 다음 연습을 수행 합니다.

 이 연습에는 다음 작업이 포함됩니다.

-   사용 하 여 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 를 도메인 모델을 기반으로 하는 지시문 프로세서를 생성 합니다.

-   생성 된 지시문 프로세서에는 사용자 지정 텍스트 템플릿 호스트를 연결 합니다.

-   생성 된 지시문 프로세서를 가진 사용자 지정 호스트를 테스트 합니다.

## <a name="prerequisites"></a>전제 조건
 DSL을 정의하려면 다음 구성 요소를 설치해야 합니다.

|||
|-|-|
|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185579](http://go.microsoft.com/fwlink/?LinkId=185579)|
|[!INCLUDE[vssdk_current_short](../modeling/includes/vssdk_current_short_md.md)]|[http://go.microsoft.com/fwlink/?LinkId=185580](http://go.microsoft.com/fwlink/?LinkId=185580)|
|Visual Studio Visualization and Modeling SDK||

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

 또한 사용자 지정 텍스트 템플릿 변환에서 만든 있어야 [연습: 사용자 지정 텍스트 템플릿 호스트 만들기](../modeling/walkthrough-creating-a-custom-text-template-host.md)합니다.

## <a name="using-domain-specific-language-tools-to-generate-a-directive-processor"></a>도메인 특정 언어 도구를 사용 하 여 지시문 프로세서를 생성 합니다.
 이 연습에서는 DSLMinimalTest 솔루션에 대 한 도메인 특정 언어를 만들려면 도메인 특정 언어 디자이너 마법사를 사용 합니다.

#### <a name="to-use-domain-specific-language-tools-to-generate-a-directive-processor-that-is-based-on-a-domain-model"></a>도메인 특정 언어 도구를 사용 하 여 도메인 모델을 기반으로 하는 지시문 프로세서를 생성 하려면

1.  다음과 같은 특징이 있는 도메인 특정 언어 솔루션을 만듭니다.

    -   이름: DSLMinimalTest

    -   솔루션 템플릿을: 최소 언어

    -   파일 확장명: 분

    -   회사 이름: Fabrikam

     도메인 특정 언어 솔루션을 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: 도메인 특정 언어 솔루션을 만들어](../modeling/how-to-create-a-domain-specific-language-solution.md)합니다.

2.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

    > [!IMPORTANT]
    >  이 단계는 지시문 프로세서를 생성 하 고에 대 한 레지스트리에서 키를 추가 합니다.

3.  **디버그** 메뉴에서 **디버깅 시작**을 클릭합니다.

     두 번째 인스턴스 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 열립니다.

4.  실험적 빌드에 **솔루션 탐색기**, 파일을 두 번 **sample.min**합니다.

     파일이는 디자이너에서 열립니다. 모델에 두 개의 요소, ExampleElement1 및 ExampleElement2, 및 간의 링크를 확인 합니다.

5.  두 번째 인스턴스를 닫은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.

6.  솔루션을 저장 한 다음 도메인 특정 언어 디자이너를 닫습니다.

## <a name="connecting-a-custom-text-template-host-to-a-directive-processor"></a>지시문 프로세서에 사용자 지정 텍스트 템플릿 호스트 연결
 지시문 프로세서를에서 만든 사용자 지정 텍스트 템플릿 호스트를 연결 하는 지시문 프로세서를 생성 한 후 [연습: 사용자 지정 텍스트 템플릿 호스트 만들기](../modeling/walkthrough-creating-a-custom-text-template-host.md)합니다.

#### <a name="to-connect-a-custom-text-template-host-to-the-generated-directive-processor"></a>생성 된 지시문 프로세서에는 사용자 지정 텍스트 템플릿 호스트를 연결 하려면

1.  CustomHost 솔루션을 엽니다.

2.  **프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.

     **참조 추가** 대화 상자가 열립니다는 **.NET** 탭이 표시 됩니다.

3.  다음 참조를 추가 합니다.

    -   Microsoft.VisualStudio.Modeling.Sdk.11.0

    -   Microsoft.VisualStudio.Modeling.Sdk.Diagrams.11.0

    -   Microsoft.VisualStudio.TextTemplating.11.0

    -   Microsoft.VisualStudio.TextTemplating.Interfaces.11.0

    -   Microsoft.VisualStudio.TextTemplating.Modeling.11.0

    -   Microsoft.VisualStudio.TextTemplating.VSHost.11.0

4.  Program.cs 또는 Module1.vb의 위쪽 코드의 다음 줄을 추가 합니다.

    ```csharp
    using Microsoft.Win32;
    ```

    ```vb
    Imports Microsoft.Win32
    ```

5.  속성에 대 한 코드를 찾을 `StandardAssemblyReferences`를 다음 코드로 바꿉니다.

    > [!NOTE]
    >  이 단계에서는 호스트가 지 원하는 생성된 지시문 프로세서에서 필요로 하는 어셈블리에 대 한 참조를 추가 합니다.

    ```csharp
    //the host can provide standard assembly references
    //the engine will use these references when compiling and
    //executing the generated transformation class
    //--------------------------------------------------------------
    public IList<string> StandardAssemblyReferences
    {
        get
        {
            return new string[]
            {
                //if this host searches standard paths and the GAC
                //we can specify the assembly name like this:
                //"System"
                //since this host only resolves assemblies from the
                //fully qualified path and name of the assembly
                //this is a quick way to get the code to give us the
                //fully qualified path and name of the System assembly
                //---------------------------------------------------------
                typeof(System.Uri).Assembly.Location,
                            typeof(System.Uri).Assembly.Location,
                typeof(Microsoft.VisualStudio.Modeling.ModelElement).Assembly.Location,
                typeof(Microsoft.VisualStudio.Modeling.Diagrams.BinaryLinkShape).Assembly.Location,
                typeof(Microsoft.VisualStudio.TextTemplating.VSHost.ITextTemplating).Assembly.Location,
                typeof(Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation).Assembly.Location

            };
        }
    }
    ```

6.  함수에 대 한 코드를 찾을 `ResolveDirectiveProcessor`를 다음 코드로 바꿉니다.

    > [!IMPORTANT]
    >  이 코드에 연결 하려면 생성 된 지시문 프로세서의 이름을 하드 코드 된 참조가 있습니다. 보다 일반적인 쉽게 유지할 수 있습니다, 모든 지시문 프로세서를 찾습니다는 쿼리에서 레지스트리에 나열 하 고 일치 하는 항목을 찾으려고 합니다. 이 경우 호스트는 생성 된 지시문 프로세서와 함께 작동할 것입니다.

    ```csharp
    //the engine calls this method based on the directives the user has
            //specified it in the text template
            //this method can be called 0, 1, or more times
            //---------------------------------------------------------------------
            public Type ResolveDirectiveProcessor(string processorName)
            {
                //check the processor name, and if it is the name of the processor the
                //host wants to support, return the type of the processor
                //---------------------------------------------------------------------
                if (string.Compare(processorName, "DSLMinimalTestDirectiveProcessor", StringComparison.InvariantCultureIgnoreCase) == 0)
                {
                    try
                    {
                        string keyName = @"Software\Microsoft\VisualStudio\10.0Exp_Config\TextTemplating\DirectiveProcessors\DSLMinimalTestDirectiveProcessor";
                        using (RegistryKey specificKey = Registry.CurrentUser.OpenSubKey(keyName))
                        {
                            if (specificKey != null)
                            {
                                List<string> names = new List<String>(specificKey.GetValueNames());
                                string classValue = specificKey.GetValue("Class") as string;
                                if (!string.IsNullOrEmpty(classValue))
                                {
                                    string loadValue = string.Empty;
                                    System.Reflection.Assembly processorAssembly = null;
                                    if (names.Contains("Assembly"))
                                    {
                                        loadValue = specificKey.GetValue("Assembly") as string;
                                        if (!string.IsNullOrEmpty(loadValue))
                                        {
                                            //the assembly must be installed in the GAC
                                            processorAssembly = System.Reflection.Assembly.Load(loadValue);
                                        }
                                    }
                                    else if (names.Contains("CodeBase"))
                                    {
                                        loadValue = specificKey.GetValue("CodeBase") as string;
                                        if (!string.IsNullOrEmpty(loadValue))
                                        {
                                            //loading local assembly
                                            processorAssembly = System.Reflection.Assembly.LoadFrom(loadValue);
                                        }
                                    }
                                    if (processorAssembly == null)
                                    {
                                        throw new Exception("Directive Processor not found");
                                    }
                                    Type processorType = processorAssembly.GetType(classValue);
                                    if (processorType == null)
                                    {
                                        throw new Exception("Directive Processor not found");
                                    }
                                    return processorType;
                                }
                            }
                        }
                    }
                    catch (Exception e)
                    {
                        //if the directive processor can not be found, throw an error
                        throw new Exception("Directive Processor not found");
                    }
                }

                //if the directive processor is not one this host wants to support
                throw new Exception("Directive Processor not supported");
            }
    ```

7.  에 **파일** 메뉴를 클릭 하 여 **모두 저장**합니다.

8.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

## <a name="testing-the-custom-host-with-the-directive-processor"></a>지시문 프로세서와 사용자 지정 호스트 테스트
 먼저 사용자 지정 텍스트 템플릿 호스트를 테스트 하려면 생성 된 지시문 프로세서를 호출 하는 텍스트 템플릿을 작성 해야 합니다. 그런 다음 사용자 지정 호스트, 텍스트 템플릿의 이름을 전달 및 실행할 지시문 올바르게 처리 하 고 있는지 확인 합니다.

#### <a name="to-create-a-text-template-to-test-the-custom-host"></a>텍스트 템플릿을 만들어 사용자 지정 호스트를 테스트하려면

1.  텍스트 파일을 만들고 이름을 `TestTemplateWithDP.tt`합니다. 파일을 만들 메모장과 같은 텍스트 편집기를 사용할 수 있습니다.

2.  텍스트 파일에 다음을 추가합니다.

    > [!NOTE]
    >  텍스트 템플릿의 프로그래밍 언어와 일치 하는 사용자 지정 호스트의 필요는 없습니다.

    ```csharp
    Text Template Host Test

    <#@ template debug="true" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>
    <# //this is the call to the examplemodel directive in the generated directive processor #>
    <#@ DSLMinimalTest processor="DSLMinimalTestDirectiveProcessor" requires="fileName='<Your Path>\Sample.min'" provides="ExampleModel=ExampleModel" #>
    <# //uncomment this line to test that the host allows the engine to set the extension #>
    <# //@ output extension=".htm" #>

    <# //uncomment this line if you want to see the generated transformation class #>
    <# //System.Diagnostics.Debugger.Break(); #>
    <# //this code uses the results of the examplemodel directive #>
    <#
        foreach ( ExampleElement box in this.ExampleModel.Elements )
        {
            WriteLine("Box: {0}", box.Name);

            foreach (ExampleElement linkedTo in box.Targets)
            {
                WriteLine("Linked to: {0}", linkedTo.Name);
            }

            foreach (ExampleElement linkedFrom in box.Sources)
            {
                WriteLine("Linked from: {0}", linkedFrom.Name);
            }

            WriteLine("");
        }
    #>
    ```

    ```vb
    Text Template Host Test

    <#@ template debug="true" language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>

    <# 'this is the call to the examplemodel directive in the generated directive processor #>
    <#@ DSLMinimalTest processor="DSLMinimalTestDirectiveProcessor" requires="fileName='<Your Path>\Sample.min'" provides="ExampleModel=ExampleModel" #>

    <# 'Uncomment this line to test that the host allows the engine to set the extension. #>
    <# '@ output extension=".htm" #>

    <# 'Uncomment this line if you want to see the generated transformation class. #>
    <# 'System.Diagnostics.Debugger.Break() #>

    <# 'this code uses the results of the examplemodel directive #>

    <#
       For Each box as ExampleElement In Me.ExampleModel.Elements

           WriteLine("Box: {0}", box.Name)

            For Each LinkedTo as ExampleElement In box.Targets
                WriteLine("Linked to: {0}", LinkedTo.Name)
            Next

            For Each LinkedFrom as ExampleElement In box.Sources
                WriteLine("Linked from: {0}", LinkedFrom.Name)
            Next

            WriteLine("")

       Next
    #>
    ```

3.  코드에서 대체 \<YOUR 경로 > 첫 번째 절차에서 만든 디자인 특정 언어에서 Sample.min 파일의 경로 사용 합니다.

4.  파일을 저장한 후 닫습니다.

#### <a name="to-test-the-custom-host"></a>사용자 지정 호스트를 테스트하려면

1.  명령 프롬프트 창을 엽니다.

2.  사용자 지정 호스트에 대한 실행 가능한 파일의 경로를 입력하고 Enter 키를 누르지 않습니다.

     예를 들어 다음과 같이 입력합니다.

     `<YOUR PATH>CustomHost\bin\Debug\CustomHost.exe`

    > [!NOTE]
    >  주소를 입력 하는 대신 CustomHost.exe 파일을 찾아볼 수 있습니다에 **Windows 탐색기**, 다음 명령 프롬프트 창에 파일을 끕니다.

3.  공백을 입력합니다.

4.  텍스트 템플릿 파일의 경로를 입력한 다음 Enter 키를 누릅니다.

     예를 들어 다음과 같이 입력합니다.

     `<YOUR PATH>TestTemplateWithDP.txt`

    > [!NOTE]
    >  주소를 입력 하는 대신 TestTemplateWithDP.txt 파일을 찾아볼 수 있습니다에 **Windows 탐색기**, 다음 명령 프롬프트 창에 파일을 끕니다.

     사용자 지정 호스트 응용 프로그램을 실행 하 고 텍스트 템플릿 변환 프로세스를 시작 합니다.

5.  **Windows 탐색기**, TestTemplateWithDP.txt 파일이 있는 폴더를 찾습니다.

     폴더에는 파일을 TestTemplateWithDP1.txt 있습니다.

6.  이 파일을 열어 텍스트 템플릿 변형의 결과를 확인합니다.

     생성된 된 텍스트 출력 결과 나타나고 다음과 같이 표시 됩니다.

    ```
    Text Template Host Test

    Box: ExampleElement1
    Linked to: ExampleElement2

    Box: ExampleElement2
    Linked from: ExampleElement1
    ```

## <a name="see-also"></a>참고 항목

- [연습: 사용자 지정 텍스트 템플릿 호스트 만들기](../modeling/walkthrough-creating-a-custom-text-template-host.md)

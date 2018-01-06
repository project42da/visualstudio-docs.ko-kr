---
title: "연습: C# 또는 Visual Basic을 사용 하 여 SDK 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef96a249-5eef-402a-a8d5-d74cb49239bd
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a8b0b8452fb20b9b6da4e8ad58c221010f23c9ed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-sdk-using-c-or-visual-basic"></a>연습: C# 또는 Visual Basic을 사용 하 여 SDK 만들기
이 연습에서는 Visual C#을 사용 하 여 단순한 수학 라이브러리 SDK를 만들고 다음 SDK는 Visual Studio 확장 (VSIX)로 패키지 하는 방법을 설명 합니다. 다음 절차를 완료 합니다.  
  
-   [SimpleMath Windows 런타임 구성 요소를 만들려면](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createClassLibrary)  
  
-   [SimpleMathVSIX 확장 프로젝트를 만들려면](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createVSIX)  
  
-   [클래스 라이브러리를 사용 하는 샘플 앱을 만들려면](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createSample)  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
##  <a name="createClassLibrary"></a>SimpleMath Windows 런타임 구성 요소를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **새 프로젝트**합니다.  
  
2.  템플릿 목록에서 확장 **Visual C#** 또는 **Visual Basic**, 선택는 **Windows 스토어** 노드를 선택한 후는 **Windows 런타임 구성 요소** 서식 파일입니다.  
  
3.  에 **이름** 상자를 지정 **SimpleMath**를 선택한 후는 **확인** 단추입니다.  
  
4.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SimpleMath** 프로젝트 노드를 선택한 후 **속성**합니다.  
  
5.  이름 바꾸기 **Class1.cs** 를 **Arithmetic.cs** 하 고 다음 코드와 일치 하도록 업데이트 합니다.  
  
     [!code-csharp[CreatingAnSDKUsingWinRT#3](../extensibility/codesnippet/CSharp/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_1.cs)]
     [!code-vb[CreatingAnSDKUsingWinRT#3](../extensibility/codesnippet/VisualBasic/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_1.vb)]  
  
6.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **솔루션 'SimpleMath'** 노드를 선택한 후 **Configuration Manager**합니다.  
  
     **Configuration Manager** 대화 상자가 열립니다.  
  
7.  에 **활성 솔루션 구성** 목록에서 선택 **릴리스**합니다.  
  
8.  에 **구성** 열을 되어 있는지 확인 **SimpleMath** 행으로 설정 되어 **릴리스**, 선택한 후는 **닫기** 적용할 단추는 변경 합니다.  
  
    > [!IMPORTANT]
    >  SimpleMath 구성 요소에 대 한 SDK에는 하나의 구성만 포함 됩니다. 이 구성은 릴리스 빌드 여야 합니다. 또는 구성 요소를 사용 하는 앱에 대 한 인증을 전달 하지는[!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]합니다.  
  
9. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SimpleMath** 프로젝트 노드를 선택한 후 **빌드**합니다.  
  
##  <a name="createVSIX"></a>SimpleMathVSIX 확장 프로젝트를 만들려면  
  
1.  에 대 한 바로 가기 메뉴는 **솔루션 'SimpleMath'** 노드를 선택 **추가**, **새 프로젝트**합니다.  
  
2.  템플릿 목록에서 확장 **Visual C#** 또는 **Visual Basic**, 선택는 **확장성** 노드를 선택한 후는 **VSIX 프로젝트** 서식 파일입니다.  
  
3.  에 **이름** 상자를 지정 **SimpleMathVSIX**를 선택한 후는 **확인** 단추입니다.  
  
4.  **솔루션 탐색기**, 선택는 **source.extension.vsixmanifest** 항목입니다.  
  
5.  메뉴 모음에서 **보기**, **코드**를 차례로 선택합니다.  
  
6.  기존 XML을 다음 XML로 바꿉니다.  
  
     [!code-xml[CreatingAnSDKUsingWinRT#1](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_2.xml)]
  
7.  **솔루션 탐색기**, 선택는 **SimpleMathVSIX** 프로젝트.  
  
8.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
9. 목록에서 **공통 항목**를 확장 하 고 **데이터**를 선택한 후 **XML 파일**합니다.  
  
10. 에 **이름** 상자를 지정 `SDKManifest.xml`를 선택한 후는 **추가** 단추입니다.  
  
11. **솔루션 탐색기**, 바로 가기 메뉴를 열고 `SDKManifest.xml`, 선택 **속성**, 다음의 값을 변경 하 고는 **VSIX에 포함** 속성 를**True**합니다.  
  
12. 파일의 내용을 다음 XML로 바꿉니다.  

    **C#**
    ```xml
    <FileList
      DisplayName="WinRT Math Library (CS)"
      MinVSVersion="11.0"
      TargetFramework=".NETCore,version=v4.5"
      AppliesTo="WindowsAppContainer"
      SupportsMultipleVersions="Error"
      MoreInfo="http://www.msdn.microsoft.com/">
    </FileList>
    ```

    **Visual Basic**
    ```xml
    <FileList
      DisplayName="WinRT Math Library (VB)"
      MinVSVersion="11.0"
      TargetFramework=".NETCore,version=v4.5"
      AppliesTo="WindowsAppContainer"
      SupportsMultipleVersions="Error"
      MoreInfo="http://www.msdn.microsoft.com/">
    </FileList>
    ```  
  
13. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SimpleMathVSIX** 프로젝트 **추가**를 선택한 후 **새 폴더**합니다.  
  
14. 폴더를 이름 `references`합니다.  
  
15. 에 대 한 바로 가기 메뉴를 열고는 **참조** 폴더를 선택 **추가**를 선택한 후 **새 폴더**합니다.  
  
16. 하위 폴더 이름 바꾸기 `commonconfiguration`내부에 하위 폴더를 만들고 이름을 `neutral`합니다.  
  
17. 이 시간에 첫 번째 폴더의 이름을 바꾼 이전 네 단계를 반복 `redist`합니다.  
  
     프로젝트에는 이제 다음 폴더 구조가 포함 되어 있습니다.  
  
    ```
    references\commonconfiguration\neutral  
    redist\commonconfiguration\neutral  
    ```  
  
18. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SimpleMath** 프로젝트를 선택한 후 **파일 탐색기에서 폴더 열기**합니다.  
  
19. **파일 탐색기**bin\Release 폴더, SimpleMath.winmd 파일에 대 한 바로 가기 메뉴를 열고 이동한 다음 선택 **복사**합니다.  
  
20. **솔루션 탐색기**, references\commonconfiguration\neutral 폴더에 파일을 붙여는 **SimpleMathVSIX** 프로젝트.  
  
21. SimpleMath.pri 파일 redist\commonconfiguration\neutral 폴더에 붙여 이전 단계를 반복는 **SimpleMathVSIX** 프로젝트.  
  
22. **솔루션 탐색기**, 선택 **SimpleMath.winmd**합니다.  
  
23. 메뉴 모음에서 **보기**, **속성** (키보드: F4 키를 선택).  
  
24. 에 **속성** 창에서 변경 된 **빌드 작업** 속성을 **콘텐츠**, 바꾼 다음는 **VSIX에 포함** 속성 를 **True 이면**합니다.  
  
25. **솔루션 탐색기**,이 프로세스를 반복 **SimpleMath.pri**합니다.  
  
26. **솔루션 탐색기**, 선택는 **SimpleMathVSIX** 프로젝트.  
  
27. 메뉴 모음에서 **빌드**, **빌드 SimpleMathVSIX**합니다.  
  
28. **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **SimpleMathVSIX** 프로젝트를 선택한 후 **파일 탐색기에서 폴더 열기**합니다.  
  
29. **파일 탐색기**, \bin\Release 폴더로 이동 하 고 다음 SimpleMathVSIX.vsix 설치를 실행 합니다.  
  
30. 선택 된 **설치** 단추 설치가 완료 되기를 기다린 후 다음 Visual Studio를 다시 시작 합니다.  
  
##  <a name="createSample"></a>클래스 라이브러리를 사용 하는 샘플 앱을 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **새 프로젝트**합니다.  
  
2.  템플릿 목록에서 확장 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **Windows 스토어** 노드.  
  
3.  선택는 **새 응용 프로그램** 서식 파일을 프로젝트 이름 **ArithmeticUI**를 선택한 후는 **확인** 단추입니다.  
  
4.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **ArithmeticUI** 프로젝트를 선택한 후 **추가**, **참조**합니다.  
  
5.  참조 형식의 목록에서 확장 **Windows**를 선택한 후 **확장**합니다.  
  
6.  세부 정보 창에서 선택 된 **단순한 수학 SDK** 확장 합니다.  
  
     해당 SDK에 대 한 추가 정보가 나타납니다. 선택할 수 있습니다는 **추가 정보** 이 연습의 앞부분에서 SDKManifest.xml 파일에 지정 된 대로 http://www.msdn.microsoft.com, 열기 위한 링크입니다.  
  
7.  에 **참조 관리자** 대화 상자는 **단순한 수학 SDK** 확인란을 선택한 후는 **확인** 단추입니다.  
  
8.  메뉴 모음에서 **보기**, **개체 브라우저**합니다.  
  
9. 에 **찾아보기** 목록에서 선택 **단순한 수학**합니다.  
  
     이제 SDK에 포함 된 기능을 탐색할 수 있습니다.  
  
10. **솔루션 탐색기**MainPage.xaml을 열고 해당 내용을 다음 XAML로 바꿉니다.  

    **C#**
    ```xml
    <Page
        x:Class="WinRTMathTestCS.MainPage"
        IsTabStop="False"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WinRTMathTestCS"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <TextBox x:Name="_firstNumber" HorizontalAlignment="Left" Margin="414,370,0,0" TextWrapping="Wrap" Text="First Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <TextBox x:Name="_secondNumber" HorizontalAlignment="Left" Margin="613,370,0,0" TextWrapping="Wrap" Text="Second Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <Button Content="+" HorizontalAlignment="Left" Margin="557,301,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="-" HorizontalAlignment="Left" Margin="557,345,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="*" HorizontalAlignment="Left" Margin="557,389,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="/" HorizontalAlignment="Left" Margin="557,433,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="=" HorizontalAlignment="Left" Margin="755,367,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnResultsClick"/>
            <TextBox x:Name="_result" HorizontalAlignment="Left" Margin="809,370,0,0" TextWrapping="Wrap" Text="Result" VerticalAlignment="Top" Height="32" Width="163" TextAlignment="Center" IsReadOnly="True"/>
        </Grid>
    </Page>
    ```
    
    **Visual Basic**
    ```xml
    <Page
        x:Class="WinRTMathTest.MainPage"
        IsTabStop="False"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WinRTMathTest"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <TextBox x:Name="_firstNumber" HorizontalAlignment="Left" Margin="414,370,0,0" TextWrapping="Wrap" Text="First Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <TextBox x:Name="_secondNumber" HorizontalAlignment="Left" Margin="613,370,0,0" TextWrapping="Wrap" Text="Second Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <Button Content="+" HorizontalAlignment="Left" Margin="557,301,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="-" HorizontalAlignment="Left" Margin="557,345,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="*" HorizontalAlignment="Left" Margin="557,389,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="/" HorizontalAlignment="Left" Margin="557,433,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="=" HorizontalAlignment="Left" Margin="755,367,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnResultsClick"/>
            <TextBox x:Name="_result" HorizontalAlignment="Left" Margin="809,370,0,0" TextWrapping="Wrap" Text="Result" VerticalAlignment="Top" Height="32" Width="163" TextAlignment="Center" IsReadOnly="True"/>
        </Grid>
    </Page>
    ```
  
11. 다음 코드와 일치 하도록 MainPage.xaml.cs를 업데이트 합니다.  
  
     [!code-csharp[CreatingAnSDKUsingWinRTDemoApp#2](../extensibility/codesnippet/CSharp/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_5.cs)]
     [!code-vb[CreatingAnSDKUsingWinRTDemoApp#2](../extensibility/codesnippet/VisualBasic/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_5.vb)]  
  
12. 앱을 실행 하려면 F5 키를 선택 합니다.  
  
13. 앱에서 다음을 있는 두 숫자를 입력 하 여 작업을 선택한 다음 선택에서  **=**  단추입니다.  
  
     올바른 결과가 나타납니다.  
  
 성공적으로 만들고 확장 SDK를 사용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: c + +를 사용 하 여 SDK 만들기](../extensibility/walkthrough-creating-an-sdk-using-cpp.md)   
 [연습: JavaScript를 사용 하 여 SDK 만들기](http://msdn.microsoft.com/en-us/6195ff56-4a27-45fc-bd29-4b0451225f4b)   
 [소프트웨어 개발 키트 만들기](../extensibility/creating-a-software-development-kit.md)
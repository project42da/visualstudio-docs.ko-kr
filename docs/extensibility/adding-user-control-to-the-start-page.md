---
title: "시작 페이지에 사용자 컨트롤 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작 페이지 dll"
  - "사용자 지정 시작 페이지"
  - "시작 페이지 어셈블리"
ms.assetid: 5b7997db-af6f-4fa9-a128-bceb42bddaf1
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# 시작 페이지에 사용자 컨트롤 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 사용자 지정 시작 페이지에 대 한 DLL 참조를 추가 하는 방법을 보여 줍니다. 예제에서는 솔루션에 사용자 정의 컨트롤 사용자 컨트롤을 빌드하고 시작 페이지.xaml 파일에서 빌드된 어셈블리를 참조 하는 다음을 추가 합니다. 새 탭의 기능을 기본 웹 브라우저 사용자 정의 컨트롤을 호스팅합니다.  
  
 .Xaml 파일에서 호출 될 수 있는 모든 어셈블리를 추가 하려면 동일한 프로세스를 사용할 수 있습니다.  
  
## 솔루션에 WPF 사용자 컨트롤 추가  
 첫째, 시작 페이지 솔루션에 Windows Presentation Foundation \(WPF\) 사용자 정의 컨트롤을 추가 합니다.  
  
1.  시작 페이지를 만들고 사용 하 여에서 만든 [사용자 지정 시작 페이지 만들기](../extensibility/creating-a-custom-start-page.md)합니다.  
  
2.  **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**, **새 프로젝트**를 차례로 클릭합니다.  
  
3.  왼쪽된 창에서는 **새 프로젝트** 대화 상자에서 확장 하 고는 **Visual Basic** 또는 **Visual C\#** 노드를 차례로 클릭 하 여 **Windows**합니다. 가운데 창에서 선택 **WPF 사용자 컨트롤 라이브러리**합니다.  
  
4.  컨트롤의 이름을 `WebUserControl` 클릭 하 고 **확인**합니다.  
  
## 사용자 정의 컨트롤을 구현합니다.  
 WPF 사용자 컨트롤을 구현 하려면 XAML에서 사용자 인터페이스 \(UI\)를 작성 하 고 C\# 또는 다른.NET 언어의 코드 숨김 이벤트를 작성 합니다.  
  
#### 사용자 정의 컨트롤에 대 한 XAML을 작성 하려면  
  
1.  사용자 정의 컨트롤에 대 한 XAML 파일을 엽니다. \< 표 \> 요소에 다음 행 정의 컨트롤에 추가 합니다.  
  
    ```vb  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto"/>  
        <RowDefinition Height="*" />  
    </Grid.RowDefinitions>  
  
    ```  
  
2.  기본에서 `Grid` 요소를 다음의 새로운 추가 `Grid` 새 주소를 설정 하기 위한 단추 및 웹 주소를 입력 하는 텍스트 상자를 포함 하는 요소입니다.  
  
    ```xml  
    <Grid Grid.Row="0">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="*" />  
            <ColumnDefinition Width="Auto" />  
        </Grid.ColumnDefinitions>  
        <TextBox x:Name="UserSource" Grid.Column="0" />  
        <Button Grid.Column="1" x:Name="SetButton" Content="Set Address" Click="SetButton_Click" />  
    </Grid>  
    ```  
  
3.  최상위 수준에 다음과 같은 프레임 추가 `Grid` 요소 바로 뒤의 `Grid` 단추와 텍스트 상자가 포함 된 요소입니다.  
  
    ```vb  
    <Frame Grid.Row="1" x:Name="WebFrame" Source="http://www.bing.com" Navigated="WebFrame_Navigated" />  
    ```  
  
4.  다음 예제에서는 사용자 정의 컨트롤에 대 한 완성된 된 XAML을 보여 줍니다.  
  
    ```xml  
    <UserControl x:Class="WebUserControl.UserControl1"  
                 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
                 mc:Ignorable="d"   
                 d:DesignHeight="300" d:DesignWidth="300">  
        <Grid>  
            <Grid.RowDefinitions>  
                <RowDefinition Height="Auto"/>  
                <RowDefinition Height="*" />  
            </Grid.RowDefinitions>  
            <Grid Grid.Row="0">  
                <Grid.ColumnDefinitions>  
                    <ColumnDefinition Width="*" />  
                    <ColumnDefinition Width="Auto" />  
                </Grid.ColumnDefinitions>  
                <TextBox x:Name="UserSource" Grid.Column="0" />  
                <Button Grid.Column="1" x:Name="SetButton" Content="Set Address" Click="SetButton_Click" />  
            </Grid>  
            <Frame Grid.Row="1" x:Name="WebFrame" Source="http://www.bing.com" Navigated="WebFrame_Navigated" />  
        </Grid>  
    </UserControl>  
  
    ```  
  
#### 사용자 정의 컨트롤에 대 한 코드 숨김 이벤트 쓰기  
  
1.  XAML 디자이너에서 두 번 클릭 하 고 **주소 설정** 단추 컨트롤에 추가 합니다.  
  
     UserControl1.cs 파일이 코드 편집기에서 열립니다.  
  
2.  SetButton\_Click 이벤트 처리기를 다음과 같이 입력 합니다.  
  
    ```c#  
    private void SetButton_Click(object sender, RoutedEventArgs e)  
    {  
        try  
        {  
            this.WebFrame.Source = new Uri(this.UserSource.Text, UriKind.Absolute);  
        }  
        catch (Exception error)  
        {  
            MessageBox.Show(error.Message);  
        }  
    }  
    ```  
  
     이 코드는 웹 브라우저에 대 한 대상으로 텍스트 상자에 입력 된 웹 주소를 설정 합니다. 주소가 올바르지 않으면 코드 오류를 throw 합니다.  
  
3.  또한 WebFrame\_Navigated 이벤트를 처리 해야 합니다.  
  
    ```c#  
    private void WebFrame_Navigated(object sender, EventArgs e)  
    { }  
    ```  
  
4.  솔루션을 빌드합니다.  
  
## 시작 페이지에 사용자 컨트롤 추가  
 이 컨트롤을 사용할 수 있도록 페이지 시작 프로젝트에 시작 페이지 프로젝트 파일에서 새 컨트롤 라이브러리에 대 한 참조를 추가 합니다. 그런 다음 시작 페이지 XAML 태그에 컨트롤을 추가할 수 있습니다.  
  
1.  **솔루션 탐색기**, 시작 페이지 프로젝트를 마우스 오른쪽 단추로 클릭 **참조** 클릭 하 고 **참조 추가**합니다.  
  
2.  에 **프로젝트** 탭에서 **WebUserControl** 클릭 하 고 **확인**합니다.  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     솔루션을 빌드하기에 게 사용자 정의 컨트롤 제공 IntelliSense 솔루션에서 다른 파일입니다.  
  
 컨트롤에 시작 페이지 XAML 태그를 추가 하려면 어셈블리에 대 한 네임 스페이스 참조를 추가 합니다. 다음 페이지에 컨트롤을 배치 합니다.  
  
#### 컨트롤의 태그를 추가 하려면  
  
1.  **솔루션 탐색기**, 시작 페이지.xaml 파일을 엽니다.  
  
2.  에 **XAML** 창에서 최상위에 다음 네임 스페이스 선언을 추가 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
    ```xml  
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"  
    ```  
  
3.  에 **XAML** 창에서 \< 표 \> 섹션으로 스크롤합니다.  
  
     이 섹션에 포함 한 <xref:System.Windows.Controls.TabControl> 요소에는 <xref:System.Windows.Controls.Grid> 요소입니다.  
  
4.  \< TabItem \>를 포함 하는 \< TabControl \> 요소를 추가 하는 사용자 정의 컨트롤에 대 한 참조를 포함 합니다.  
  
    ```xml  
  
    <TabItem Header="Web" Height="Auto">  
        <vsc:UserControl1 />  
    </TabItem>  
  
    ```  
  
 이제 컨트롤을 테스트할 수 있습니다.  
  
## 수동으로 만든된 사용자 지정 시작 페이지를 테스트합니다.  
  
1.  사용자는 XAML 파일 및 모든 지원 텍스트 파일 또는 태그 파일을 복사 된 **%USERPROFILE%\\My Documents\\Visual Studio 2015\\StartPages\\** 폴더입니다.  
  
2.  시작 페이지는 컨트롤 또는 Visual Studio가 설치 되지 않은 어셈블리의 형식을 참조 하는 경우 어셈블리를 복사 하 고 다음에 붙여 *Visual Studio 설치 폴더***\\Common7\\IDE\\PrivateAssemblies\\**합니다.  
  
3.  Visual Studio 명령 프롬프트에 다음을 입력 **devenv \/rootsuffix Exp** Visual Studio의 실험적 인스턴스를 엽니다.  
  
4.  실험적 인스턴스를에서으로 **도구 \/ 옵션 \/ 환경 \/ 시작** 페이지에 있는 XAML 파일을 선택 하 고는 **시작 페이지 사용자 지정** 드롭다운에서 합니다.  
  
5.  **보기** 메뉴에서 **시작 페이지**를 클릭합니다.  
  
     사용자 지정 시작 페이지 표시 되어야 합니다. 파일을 변경 하려는 경우 실험적 인스턴스, 변경, 복사 및 변경 된 파일을 붙여 닫고 해야 변경 내용을 보려면 실험적 인스턴스를 다시 엽니다.  
  
## 참고 항목  
 [WPF 컨테이너 컨트롤](http://msdn.microsoft.com/ko-kr/a0177167-d7db-4205-9607-8ae316952566)   
 [연습: 시작 페이지 사용자 지정 XAML에 추가](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)
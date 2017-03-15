---
title: "연습: 시작 페이지에서 사용자 설정을 저장 하는 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 754b9bf3-8681-4c77-b0a4-09146a4e1d2d
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c358bf79945b4f4eef5b19c60cad0bd866c175b3
ms.openlocfilehash: 1bf8a313898f9c12312beedb31238fb74e1a56a8
ms.lasthandoff: 02/22/2017

---
# <a name="walkthrough-saving-user-settings-on-a-start-page"></a>시작 페이지에서 사용자 설정을 저장 하는 연습:
시작 페이지에 대 한 사용자 설정을 유지할 수 있습니다. 이 연습을 수행 하 여 사용자가 단추를 클릭 한 다음 시작 페이지가 로드 될 때마다이 설정으로 검색 하는 경우 레지스트리 설정을 저장 하는 컨트롤을 만들 수 있습니다. 시작 페이지 프로젝트 템플릿은 사용자 지정 가능한 사용자 컨트롤을 포함 하 고 해당 컨트롤을 호출 하는 기본 시작 페이지 XAML 이기 때문에 자체 시작 페이지를 수정할 필요가 없습니다.  
  
 이 연습에서 인스턴스화되는 설정 저장소의 인스턴스가 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore>인터페이스 읽기 및 쓰기는 다음 레지스트리 위치를 호출 했을 때를: HKCU\Software\Microsoft\VisualStudio\14.0\\*CollectionName* </xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore>  
  
 Visual Studio의 실험적 인스턴스에서 실행 될 때 설정 저장소를 읽고 쓸 HKCU\Software\Microsoft\VisualStudio\14.0Exp\\*CollectionName 합니다.*  
  
 설정을 유지 하는 방법에 대 한 자세한 내용은 참조 [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
  
> [!NOTE]
>  이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
>   
>  시작 페이지 프로젝트 템플릿을 사용 하 여 다운로드할 수 있습니다 **확장 관리자**합니다.  
  
## <a name="setting-up-the-project"></a>프로젝트 설정  
  
#### <a name="to-configure-the-project-for-this-walkthrough"></a>이 연습에 대 한 프로젝트를 구성 하려면  
  
1.  에 설명 된 대로 시작 페이지 프로젝트 만들기 [사용자 지정 시작 페이지를 만들어](creating-a-custom-start-page.md)합니다. 프로젝트 이름을 **SaveMySettings**합니다.  
  
2.  **솔루션 탐색기**, StartPageControl 프로젝트에 다음 어셈블리 참조를 추가 합니다.  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.OLE.Interop  
  
    -   Microsoft.VisualStudio.Shell.Interop.11.0  
  
3.  MyControl.xaml을 엽니다.  
  
4.  XAML 창에서 최상위 수준에서 <xref:System.Windows.Controls.UserControl>요소 정의입니다. 네임 스페이스 선언 뒤에 다음 이벤트 선언을 추가 합니다.</xref:System.Windows.Controls.UserControl>  
  
    ```  
    Loaded="OnLoaded"  
    ```  
  
5.  디자인 창에서 컨트롤의 주요 영역을 클릭 한 다음 DELETE 키를 누릅니다.  
  
     이렇게 하면 제거는 <xref:System.Windows.Controls.Border>요소와, 및 최상위는 리프의 모든 기능 <xref:System.Windows.Controls.Grid>요소.</xref:System.Windows.Controls.Grid> </xref:System.Windows.Controls.Border>  
  
6.  **도구 상자**, 끌어는 <xref:System.Windows.Controls.StackPanel>컨트롤이 눈금에.</xref:System.Windows.Controls.StackPanel>  
  
7.  이제 끌어는 <xref:System.Windows.Controls.TextBlock>, <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.StackPanel>.</xref:System.Windows.Controls.StackPanel> 하는 단추</xref:System.Windows.Controls.TextBox> </xref:System.Windows.Controls.TextBlock>  
  
8.  추가 **X:name** 특성에 <xref:System.Windows.Controls.TextBox>, 및 `Click` 에 대 한 이벤트는 <xref:System.Windows.Controls.Button>다음 예제와 같이.</xref:System.Windows.Controls.Button> </xref:System.Windows.Controls.TextBox>  
  
    ```xml  
    <StackPanel Width="300" HorizontalAlignment="Center" VerticalAlignment="Center">  
        <TextBlock Width="140" FontSize="14">Enter your setting</TextBlock>  
        <TextBox x:Name="txtblk" Margin="0, 5, 0, 10" Width="140" />  
        <Button Click="Button_Click" Width="100">Save My Setting</Button>  
    </StackPanel>  
    ```  
  
## <a name="implementing-the-user-control"></a>사용자 정의 컨트롤을 구현합니다.  
  
#### <a name="to-implement-the-user-control"></a>사용자 정의 컨트롤을 구현 하려면  
  
1.  XAML 창에서 마우스 오른쪽 단추로 클릭는 `Click` 의 특성은 <xref:System.Windows.Controls.Button>요소와 클릭 한 다음 **이벤트 처리기 탐색**.</xref:System.Windows.Controls.Button>  
  
     MyControl.xaml.cs, 열리고 만듭니다에 대 한 스텁 처리기는 `Button_Click` 이벤트입니다.  
  
2.  다음 코드를 추가 `using` 문을 파일의 맨 위에 있습니다.  
  
     [!code-cs[StartPageDTE #&11;](../extensibility/codesnippet/CSharp/walkthrough-saving-user-settings-on-a-start-page_1.cs)]  
  
3.  추가 전용 `SettingsStore` 속성을 다음 예와에서 같이 합니다.  
  
    ```c#  
    private IVsWritableSettingsStore _settingsStore = null;  
    private IVsWritableSettingsStore SettingsStore  
    {  
        get  
        {  
            if (_settingsStore == null)  
            {  
                // Get a reference to the DTE from the DataContext.   
                var typeDescriptor = DataContext as ICustomTypeDescriptor;  
                var propertyCollection = typeDescriptor.GetProperties();  
                var dte = propertyCollection.Find("DTE", false).GetValue(  
                    DataContext) as DTE2;  
  
                // Get the settings manager from the DTE.   
                var serviceProvider = new ServiceProvider(  
                    (Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte);  
                var settingsManager = serviceProvider.GetService(  
                    typeof(SVsSettingsManager)) as IVsSettingsManager;  
  
                // Write the user settings to _settingsStore.  
                settingsManager.GetWritableSettingsStore(  
                    (uint)__VsSettingsScope.SettingsScope_UserSettings,  
                    out _settingsStore);  
            }  
            return _settingsStore;  
        }  
    }  
    ```  
  
     이 속성에 대 한 참조를 먼저 가져옵니다는 <xref:EnvDTE80.DTE2>자동화 개체 모델에서 포함 된 인터페이스는 <xref:System.Windows.FrameworkElement.DataContext%2A>는 사용자 정의 컨트롤을 사용 하 여 다음의 인스턴스를 가져올 DTE의는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsManager>인터페이스.</xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsManager> </xref:System.Windows.FrameworkElement.DataContext%2A> </xref:EnvDTE80.DTE2> 그런 다음 현재 사용자 설정을 반환 하려면 해당 인스턴스를 사용 합니다.  
  
4.  입력은 `Button_Click` 다음과 같이 이벤트로 합니다.  
  
    ```c#  
    private void Button_Click(object sender, RoutedEventArgs e)  
    {  
        int exists = 0;  
        SettingsStore.CollectionExists("MySettings", out exists);  
        if (exists != 1)  
        {  
            SettingsStore.CreateCollection("MySettings");  
        }  
        SettingsStore.SetString("MySettings", "MySetting", txtblk.Text);  
    }  
    ```  
  
     이 레지스트리에서는 "내 설정" 컬렉션의 "MySetting" 필드에 텍스트 상자의 콘텐츠를 씁니다. 컬렉션이 없는 경우 자동으로 만들어집니다.  
  
5.  에 대 한 다음 처리기를 추가 `OnLoaded` 사용자 정의 컨트롤의 이벤트입니다.  
  
    ```c#  
    private void OnLoaded(Object sender, RoutedEventArgs e)  
    {  
        string value;  
        SettingsStore.GetStringOrDefault(  
            "MySettings", "MySetting", "", out value);  
        txtblk.Text = value;  
    }  
    ```  
  
     이 입력란의 텍스트 "MySetting"의 현재 값을 설정합니다.  
  
6.  사용자 정의 컨트롤을 빌드하십시오.  
  
7.  **솔루션 탐색기**, source.extension.vsixmanifest를 엽니다.  
  
8.  매니페스트 편집기에서 설정 **제품 이름** 를 **내 설정 시작 페이지 저장**합니다.  
  
     이의 이름을 설정 하 여 시작 페이지에 표시 하는 것 만큼의 **시작 페이지 사용자 지정** 목록에 **옵션** 대화 상자입니다.  
  
9. StartPage.xaml를 빌드하십시오.  
  
## <a name="testing-the-control"></a>컨트롤 테스트  
  
#### <a name="to-test-the-user-control"></a>사용자 정의 컨트롤을 테스트 하려면  
  
1.  F5 키를 누릅니다.  
  
     Visual Studio의 실험적 인스턴스가 열립니다.  
  
2.  실험적 인스턴스에서는 **도구** 메뉴를 클릭 하 여 **옵션**합니다.  
  
3.  에 **환경** 노드를 클릭 하 여 **시작**, 선택한 다음는 **시작 페이지 사용자 지정** 목록에서 **[설치 된 확장] 저장 내 설정 시작 페이지**.  
  
     **확인**을 클릭합니다.  
  
4.  열려 있으면 한 다음 시작 페이지를 닫습니다는 **보기** 메뉴를 클릭 하 여 **시작 페이지**합니다.  
  
5.  시작 페이지에서 클릭 된 **MyControl** 탭 합니다.  
  
6.  텍스트 상자에 입력 **Cat**를 클릭 하 고 **내 설정 저장**합니다.  
  
7.  시작 페이지를 닫고 다시 엽니다.  
  
     단어 "고양이" 텍스트 상자에 표시 됩니다.  
  
8.  "Dog" 라는 단어 "고양이" 라는 단어를 바꿉니다. 단추를 클릭 하지 마십시오.  
  
9. 시작 페이지를 닫고 다시 엽니다.  
  
     하지만 설정이 저장 되지 않았습니다 "Dog" 라는 단어가 텍스트 상자에 표시 됩니다. 이런 Visual Studio 도구 창을 메모리에 유지 하기 때문에 Visual Studio 자체를 닫을 때까지 닫혀 있는 경우에 있습니다.  
  
10. Visual Studio의 실험적 인스턴스를 닫습니다.  
  
11. F5 키를 눌러 실험적 인스턴스를 다시 엽니다.  
  
12. 단어 "고양이" 텍스트 상자에 표시 됩니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 사용자 정의 컨트롤을 저장 하 고 원하는 수의 사용자 지정 설정 가져오고 설정 하는 다른 값을 다른 이벤트 처리기를 사용 하 여 검색을 수정할 수는 `SettingsStore` 속성입니다. 다른 사용 하 여으로 `propertyName` 각 호출에 대 한 매개 변수 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore.SetString%2A>, 값을 덮어쓰지 것입니다 서로 레지스트리에.</xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore.SetString%2A>  
  
## <a name="see-also"></a>참고 항목  
 <xref:EnvDTE80.DTE2?displayProperty=fullName></xref:EnvDTE80.DTE2?displayProperty=fullName>     
 [시작 페이지에 Visual Studio 명령 추가](../extensibility/adding-visual-studio-commands-to-a-start-page.md)

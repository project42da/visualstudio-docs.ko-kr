---
title: "Visual Studio에서 Xamarin.Forms를 사용한 앱 빌드 기본 사항 알아보기 | Microsoft 문서"
ms.custom: 
ms.date: 01/19/2018
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: 3a066156f66a4e89132010a8c83edc7029dbe19e
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2018
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Visual Studio에서 Xamarin.Forms를 사용한 앱 빌드 기본 사항 알아보기
[Setup and install](../cross-platform/setup-and-install.md) 및 [Verify your Xamarin environment](../cross-platform/verify-your-xamarin-environment.md)의 단계를 완료했으면 이 연습 과정을 통해 Xamarin.Forms로 기본 앱을 구축하는 방법을 확인합니다(아래 참조). Xamarin.Forms를 사용하여 모든 UI 코드를 .NET Standard 클래스 라이브러리로 한꺼번에 작성합니다. 그러면 Xamarin은 iOS, Android 및 Windows 유니버설 플랫폼에 대한 네이티브 UI 컨트롤을 자동으로 렌더링합니다. .NET Standard 라이브러리는 모든 대상 플랫폼에서 지원되는 .NET API만 포함하고 Xamarin.Forms는 플랫폼 간 UI 코드 공유를 가능하게 하므로 공유 프로젝트가 아닌 이 접근 방법이 권장됩니다.  
  
 ![Android, iOS 및 Windows의 날씨 앱 샘플](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 앱을 빌드하려면 다음 작업을 수행합니다.  
  
-   [솔루션 설정](#solution)  
  
-   [공유 데이터 서비스 코드 작성](#dataservice)  
  
-   [공유 UI 코드 작성 시작](#uicode)  
  
-   [Android용 Visual Studio 에뮬레이터를 사용하여 앱을 테스트합니다.](#test)  
  
-   [플랫폼 간에 네이티브 모양 및 느낌을 지정하여 UI 완료](#finish)  
  
> [!TIP]
>  [GitHub의 xamarin-forms-samples 리포지토리](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather)에서 이 프로젝트에 대한 전체 소스 코드를 찾을 수 있습니다.  
  
##  <a name="solution"></a> 솔루션 설정  
 다음 단계에서는 공유 코드에 대한 .NET Standard 클래스 라이브러리와 두 개의 추가 NuGet 패키지를 포함하는 Xamarin.Forms 솔루션을 만듭니다.  
  
1.  Visual Studio에서 새 **플랫폼 간 앱(Xamarin.Forms)** 솔루션을 만들고 **WeatherApp**으로 이름을 지정합니다. 왼쪽 목록에서 **Visual C#** 및 **플랫폼 간**을 선택하여 템플릿을 찾습니다.  
  
     템플릿이 이 위치에 없으면 Xamarin을 설치하거나 Visual Studio 2017 기능을 사용하도록 설정해야 합니다. [설정 및 설치](../cross-platform/setup-and-install.md)를 참조하세요.  
  
     ![새 빈 앱 &#40;플랫폼 간 Xamarin.Forms 앱&#41; 프로젝트 만들기](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

2.  [확인]을 클릭하면 일부 옵션을 선택할 수 있습니다. **빈 앱**, **Xamarin.Forms** 및 **.NET Standard**를 선택합니다.

     ![새 플랫폼 간 앱 프로젝트 만들기](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")
  
3.  [확인]을 클릭하여 솔루션을 만든 후에는 많은 개별 프로젝트가 만들어집니다.  
  
    -   **WeatherApp**: 일반적인 비즈니스 논리 및 Xamarin.Forms를 사용하는 UI 코드를 포함하여 플랫폼 간에 공유되는 코드를 작성하는 .NET Standard 라이브러리.  
  
    -   **WeatherApp.Android**: 네이티브 Android 코드를 포함하는 프로젝트. 이 프로젝트가 기본 시작 프로젝트로 설정됩니다.  
  
    -   **WeatherApp.iOS**: 네이티브 iOS 코드를 포함하는 프로젝트  
  
    -   **WeatherApp.UWP**: Windows 10 UWP 코드를 포함하는 프로젝트  
  
    > [!NOTE]
    >  대상으로 하지 플랫폼에 대한 프로젝트는 삭제할 수 있습니다.   
  
     각 네이티브 프로젝트 내에서 해당 플랫폼에 대한 네이티브 디자이너에 액세스하여 플랫폼 특정 화면 및 기능을 필요에 따라 구현할 수 있습니다.  
  
4.  다음과 같이 솔루션의 Xamarin.Forms NuGet 패키지를 안정적인 최신 버전으로 업그레이드합니다. 새 Xamarin 솔루션을 만들 때마다 다음 작업을 수행하는 것이 좋습니다.  
  
    -   **도구 > NuGet 패키지 관리자 > 솔루션용 NuGet 패키지 관리**를 선택합니다.  
  
    -   **업데이트** 탭 아래에서 **Xamarin.Forms** 패키지를 선택하고 솔루션의 모든 프로젝트를 업데이트하도록 선택합니다. (참고: Xamarin.Android.Support에 대한 모든 업데이트는 선택되지 않은 상태로 둡니다.)  
  
    -   **버전** 필드를 사용 가능한 **안정적인 최신** 버전으로 업데이트합니다.  
  
    -   **설치**를 클릭합니다.  
  
         ![Xamarin.Forms NuGet 패키지 업데이트](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")  
  
5.  **Newtonsoft.Json** 및 NuGet 패키지를 **WeatherApp** 프로젝트에 추가합니다. 이 프로젝트는 날씨 데이터 서비스에서 검색된 정보를 처리하는 데 사용됩니다.  
  
    -   NuGet 패키지 관리자(4단계부터 열려 있음)에서 **찾아보기** 탭을 선택하고 **Newtonsoft**를 검색합니다.  
  
    -   **Newtonsoft.Json**을 선택합니다.  
  
    -   **WeatherApp** 프로젝트를 선택합니다(패키지를 설치하는 데는 이 프로젝트만 필요함).  
  
    -   **버전** 필드가 **안정적인 최신 버전** 으로 설정되어 있는지 확인합니다.  
  
    -   **설치**를 클릭합니다.  
  
    ![Newtonsoft.Json NuGet 패키지 찾기 및 설치](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
6.  5단계를 반복하여 **Microsoft.Net.Http** 패키지를 찾아서 설치합니다.  
  
7.  솔루션을 빌드하고 빌드 오류가 없는지 확인합니다.  
  
##  <a name="dataservice"></a> 공유 데이터 서비스 코드 작성  
 **WeatherApp** 프로젝트는 모든 플랫폼에서 공유되는 .NET Standard 라이브러리에 대한 코드를 작성하는 프로젝트입니다. 이 라이브러리는 iOS, Android, Windows 프로젝트에서 빌드된 앱 패키지에 자동으로 포함됩니다.  
  
 이 샘플을 실행하려면 무료 API 키를 위해 [http://openweathermap.org/appid](http://openweathermap.org/appid)에 먼저 등록해야 합니다.  
  
 다음 단계에서는 날씨 서비스의 데이터를 액세스하고 저장하기 위한 코드를 .NET Standard 라이브러리에 추가합니다.  
  
1.  **WeatherApp** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 클래스...**를 선택합니다. **새 항목 추가** 대화 상자에서 파일 이름을 **Weather.cs**로 지정합니다. 이 클래스는 날씨 데이터 서비스의 데이터를 저장하는 데 사용합니다.  
  
2.  **Weather.cs** 의 전체 내용을 다음으로 바꿉니다.  
  
    ```csharp  
    namespace WeatherApp
    {
        public class Weather
        {
            // Because labels bind to these values, set them to an empty string to
            // ensure that the label appears on all platforms by default.
            public string Title { get; set; } = " ";
            public string Temperature { get; set; } = " ";
            public string Wind { get; set; } = " ";
            public string Humidity { get; set; } = " ";
            public string Visibility { get; set; } = " ";
            public string Sunrise { get; set; } = " ";
            public string Sunset { get; set; } = " ";
        }
    }
    ```  
  
3.  **WeatherApp** 프로젝트에 **DataService.cs**라는 다른 클래스를 추가합니다. 이 프로젝트는 날씨 데이터 서비스의 JSON 데이터를 처리하는 데 사용됩니다.  
  
4.  **DataService.cs** 의 전체 내용을 다음 코드로 바꿉니다.  
  
    ```csharp  
    using System.Net.Http;  
    using System.Threading.Tasks;  
    using Newtonsoft.Json;  
    
    namespace WeatherApp  
    {  
        public class DataService  
        {  
            public static async Task<dynamic> getDataFromService(string queryString)  
            {  
                HttpClient client = new HttpClient();  
                var response = await client.GetAsync(queryString);  
  
                dynamic data = null;  
                if (response != null)  
                {  
                    string json = response.Content.ReadAsStringAsync().Result;  
                    data = JsonConvert.DeserializeObject(json);  
                }  
  
                return data;  
            }  
        }  
    }  
    ```  
  
5.  **WeatherApp** 프로젝트에 공유 비즈니스 논리를 넣을 **Core**라는 세 번째 클래스를 추가합니다. 이 코드는 우편 번호를 사용하여 쿼리 문자열을 구성하고, 날씨 서비스를 호출하고, **Weather** 클래스의 인스턴스를 채웁니다.  
  
6.  그런 후 **Core.cs** 의 내용을 다음으로 바꿉니다.  
  
    ```csharp  
    using System;  
    using System.Threading.Tasks;  
  
    namespace WeatherApp  
    {  
        public class Core  
        {  
            public static async Task<Weather> GetWeather(string zipCode)  
            {  
                //Sign up for a free API key at http://openweathermap.org/appid  
                string key = "YOUR KEY HERE";  
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="  
                    + zipCode + ",us&appid=" + key + "&units=imperial";  
  
                dynamic results = await DataService.getDataFromService(queryString).ConfigureAwait(false);  
  
                if (results["weather"] != null)  
                {  
                    Weather weather = new Weather();  
                    weather.Title = (string)results["name"];                  
                    weather.Temperature = (string)results["main"]["temp"] + " F";  
                    weather.Wind = (string)results["wind"]["speed"] + " mph";                  
                    weather.Humidity = (string)results["main"]["humidity"] + " %";  
                    weather.Visibility = (string)results["weather"][0]["main"];  
  
                    DateTime time = new System.DateTime(1970, 1, 1, 0, 0, 0, 0);  
                    DateTime sunrise = time.AddSeconds((double)results["sys"]["sunrise"]);  
                    DateTime sunset = time.AddSeconds((double)results["sys"]["sunset"]);  
                    weather.Sunrise = sunrise.ToString() + " UTC";  
                    weather.Sunset = sunset.ToString() + " UTC";  
                    return weather;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
        }  
    }  
    ```  
  
7.  **WeatherApp** 라이브러리 프로젝트를 빌드하여 코드가 올바른지 확인합니다.  
  
##  <a name="uicode"></a> 공유 UI 코드 작성 시작  
 Xamarin.Forms를 사용하여 .NET Standard 라이브러리에서 공유 UI 코드를 구현할 수 있습니다. 이 단계에서는 이전 섹션에서 추가한 코드를 날씨 데이터 서비스 코드에 의해 반환된 데이터로 해당 텍스트를 업데이트하는 단추가 있는 페이지를 프로젝트에 추가합니다.  
  
1.  **WeatherApp** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가 > 새 항목...**을 선택하여 **WeatherPage.cs**라는 **콘텐츠 페이지**를 추가합니다. **새 항목 추가** 대화 상자에서 **콘텐츠 페이지**를 선택합니다. **콘텐츠 페이지(C#)** 또는 **콘텐츠 보기**를 선택하지 않도록 주의하세요. 이름을 **WeatherPage.cs**로 지정합니다.  
  
     ![새 Xamarin.Forms XAML 페이지 추가](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")  
  
     Xamarin.Forms는 XAML 기반이므로 이 단계에서는 중첩된 코드 숨김 파일 **WeatherPage.xaml.cs** 와 함께 **WeatherPage.xaml**파일을 만듭니다. 이 방법을 사용하면 XAML 또는 코드를 통해 UI를 생성할 수 있습니다. 이 연습에서는 둘 중 일부 작업을 수행합니다.  
  
2.  WeatherPage 화면에 단추를 추가하려면 **WeatherPage.xaml**의 내용을 다음 코드로 바꿉니다.  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
           x:Class="WeatherApp.WeatherPage"
           Title="Sample Weather App">  
      <Button x:Name="getWeatherBtn" 
              Text="Get Weather"
              Clicked="GetWeatherBtn_Clicked" />  
    </ContentPage>  
    ```  
  
     코드 숨김 파일 내에서 이름으로 이 단추를 참조할 수 있도록 단추 이름은 **x:Name** 특성을 사용하여 정의해야 합니다.  
  
3.  단추의 **Clicked** 이벤트에 대한 이벤트 처리기를 추가하여 단추 텍스트를 업데이트하려면 **WeatherPage.xaml.cs**의 내용을 아래 코드로 바꿉니다. (“60601”을 다른 우편 번호로 변경해도 됩니다.)  
  
    ```csharp  
    using System;  
    using Xamarin.Forms;  
  
    namespace WeatherApp  
    {  
        public partial class WeatherPage: ContentPage  
        {  
            public WeatherPage()  
            {  
                InitializeComponent();  
  
                //Set the default binding to a default object for now  
                BindingContext = new Weather();  
            }  
  
            private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
            {  
                Weather weather = await Core.GetWeather("60601");  
                getWeatherBtn.Text = weather.Title;  
            }  
        }  
    }  
    ```  
  
4.  앱이 시작될 때 첫 번째 화면으로 **WeatherPage** 를 열려면 **App.cs** 의 기본 생성자를 다음 코드로 바꿉니다.  
  
    ```csharp  
    public App()  
    {
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());  
    }  
    ```  
  
5.  **WeatherApp** 프로젝트를 빌드하여 코드가 올바른지 확인합니다.  
  
##  <a name="test"></a> Android용 Visual Studio 에뮬레이터를 사용하여 앱을 테스트합니다.  
 이제 앱을 실행할 준비가 되었습니다. 지금은 앱이 날씨 서비스의 데이터를 가져오는지를 Android 버전에서만 확인해 보겠습니다. iOS 및 UWP 버전은 다른 UI 요소를 추가한 후에 실행해 보겠습니다.   
  
1.  **WeatherApp.Android** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택하여 해당 프로젝트를 시작 프로젝트로 설정합니다.  
  
2.  Visual Studio 도구 모음에서 **WeatherApp.Android**가 대상 프로젝트로 표시됩니다. 디버깅을 위해 Android 에뮬레이터 중 하나를 선택하고 **F5**키를 누릅니다. Visual Studio Emulator for Android에서 앱을 실행하는 **VisualStudio** 에뮬레이터 옵션 중 하나를 사용하는 것이 좋습니다.  
  
     ![Android Emulator 디버그 대상 선택](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")  
  
3.  에뮬레이터에서 앱이 시작되면 **날씨 검색** 단추를 클릭합니다. 단추 텍스트가 **Chicago**로 업데이트되어 표시되며, 이것은 날씨 서비스에서 가져온 데이터의 *Title* 속성입니다.  
  
     ![단추를 탭하기 전후의 날씨 앱](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")  
  
##  <a name="finish"></a> 플랫폼 간에 네이티브 모양 및 느낌을 지정하여 UI 완료  
 Xamarin.Forms는 앱이 자동으로 네이티브 모양 및 느낌을 갖도록 각 플랫폼에 대해 네이티브 UI 컨트롤을 렌더링합니다. 이를 보다 명확히 이해하기 위해 우편 번호 입력 필드로 UI를 완료한 다음 서비스에서 반환되는 날씨 데이터를 표시해 보겠습니다.  
  
1.  **WeatherPage.xaml** 의 내용을 아래 코드로 바꿉니다. 앞서 설명된 대로 **X:name** 특성을 사용하여 이름이 지정된 요소는 코드에서 참조될 수 있습니다. 또한 Xamarin.Forms는 다양한 [레이아웃 옵션](http://developer.xamarin.com/guides/xamarin-forms/controls/layouts/)(xamarin.com)을 제공합니다. 여기서 WeatherPage는 [Grid](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/)(xamarin.com) 및 [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/)(xamarin.com)을 사용합니다.  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
                 x:Class="WeatherApp.WeatherPage"
                 Title="Sample Weather App">

        <ContentPage.Resources>
            <ResourceDictionary>
                <Style x:Key="labelStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Small" />
                    <Setter Property="TextColor" Value="#404040" />
                </Style>
                <Style x:Key="fieldStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Medium" />
                    <Setter Property="Margin" Value="10,0,0,0" />
                </Style>
            </ResourceDictionary>
        </ContentPage.Resources>

        <StackLayout>
            <Grid BackgroundColor="#545454" Padding="10, 10, 10, 10">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto" />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>

                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="*" />
                    <ColumnDefinition Width="Auto" />
                </Grid.ColumnDefinitions>
            
                <Label Text="Search by Zip Code" 
                       Grid.Row="0" Grid.Column="0" Grid.ColumnSpan="3"
                       HorizontalOptions="Center"
                       TextColor="White" FontAttributes="Bold" FontSize="Medium" />
            
                <Label x:Name="zipCodeLabel" Text="Zip Code:" 
                       Grid.Row="1" Grid.Column="0"
                       VerticalOptions="Center"
                       Style="{StaticResource labelStyle}"
                       TextColor="#C0C0C0" />
            
                <Entry x:Name="zipCodeEntry"
                       Grid.Row="1" Grid.Column="1"
                       VerticalOptions="Center"
                       Margin="5,0"
                       BackgroundColor="DarkGray"
                       TextColor="White" />
            
                <Button x:Name="getWeatherBtn" Text="Get Weather" 
                        Grid.Row="1" Grid.Column="2"
                        HorizontalOptions="Center"
                        VerticalOptions="Center"
                        BorderWidth="1"
                        BorderColor="White"
                        BackgroundColor="DarkGray"
                        TextColor="White"
                        Clicked="GetWeatherBtn_Clicked" />
            </Grid>

            <ScrollView VerticalOptions="FillAndExpand">
                <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">
                    <Label Text="Location" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Title}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Temperature" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Temperature}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Wind Speed" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Wind}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Humidity" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Humidity}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Visibility" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Visibility}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Time of Sunrise" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunrise}" Style="{StaticResource fieldStyle}" />
                
                    <Label Text="Time of Sunset" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunset}" Style="{StaticResource fieldStyle}" />
                </StackLayout>
            </ScrollView>
        </StackLayout>
    </ContentPage>  
     ```  
  
     여기에 표시되지 않지만 **OnPlatform** 태그를 사용하여 앱이 실행되고 있는 현재 플랫폼에 국한되는 속성 값을 선택할 수 있습니다([필수 XAML 구문](http://developer.xamarin.com/guides/xamarin-forms/user-interface/xaml-basics/essential_xaml_syntax/) 참조)(xamarin.com). 코드 숨김 파일에서는 같은 용도로 [Device.OnPlatform API](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) 를 사용할 수 있습니다.  
  
2.  **WeatherPage.xaml.cs**에서 **GetWeatherBtn_Clicked** 이벤트 처리기를 아래 코드로 바꿉니다. 이 코드는 입력 필드에 우편 번호가 있는지 확인하고, 해당 우편 번호에 대한 데이터를 검색하고, 전체 페이지 바인딩 컨텍스트를 결과 **Weather** 인스턴스로 설정한 다음, 단추 텍스트를 “다시 검색”으로 설정합니다. UI의 각 레이블은 **Weather** 클래스의 속성에 바인딩되므로 화면의 바인딩 컨텍스트를 **Weather** 인스턴스로 설정하면 해당 레이블이 자동으로 업데이트됩니다.  
  
    ```csharp  
    private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
    {  
        if (!String.IsNullOrEmpty(zipCodeEntry.Text))  
        {  
            Weather weather = await Core.GetWeather(zipCodeEntry.Text);  
            BindingContext = weather;  
            getWeatherBtn.Text = "Search Again";  
        }  
    }  
    ```  
  
3.  해당 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택한 후 장치 또는 에뮬레이터나 시뮬레이터에서 앱을 시작하여 세 플랫폼(Android, iOS 및 Windows) 모두에서 앱을 실행합니다. 아래와 같이 유효한 미국 5자리 우편 번호를 입력하고 **날씨 검색** 단추를 눌러 해당 지역의 날씨 데이터를 표시합니다. iOS 프로젝트의 경우 네트워크의 Mac OS X 컴퓨터에 Visual Studio가 연결되어 있어야 합니다.  
  
     ![Android, iOS 및 Windows Phone의 날씨 앱 샘플](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 이 프로젝트에 대한 전체 소스 코드는 [GitHub의 xamarin-forms-samples 리포지토리](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather)에 있습니다.
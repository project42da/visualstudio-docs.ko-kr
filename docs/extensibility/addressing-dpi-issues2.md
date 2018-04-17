---
title: DPI Issues2 주소 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 359184aa-f5b6-4b6c-99fe-104655b3a494
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc0801d3fb43188ac3371ed7e5e7394b0e3aad72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="addressing-dpi-issues"></a>DPI 문제 해결
"고해상도" 화면 장치 증가 함에 제공 합니다. 이 화면에는 일반적으로 200 개가 넘는 픽셀 (ppi) 필요. 이러한 컴퓨터에서 응용 프로그램 사용 콘텐츠를 장치에 대 한 일반 보기로 거리에 있는 콘텐츠를 표시 하는 요구 사항에 맞게 확장할 수 있어야 합니다. 2014 년 현재 고밀도 디스플레이 대 한 기본 대상은 모바일 장치 (태블릿, 클램쉘 랩톱 및 휴대폰)를 계산 합니다.  
  
 Windows 8.1 이상에 이러한 컴퓨터를 표시 하 고 컴퓨터 고밀도 둘 다에 연결 된 표준 밀도 동시에 표시 하는 환경에 맞게 사용할 수 있도록 몇 가지 기능이 포함 되어 있습니다.  
  
-   Windows는 "그대로 수행" 텍스트 및 기타 항목 더 크거나 작게 "를 사용 하 여 장치에 콘텐츠를 조정 하도록 설정 (Windows XP부터 사용할 수 있음).  
  
-   Windows 8.1 이상 자동으로 대부분의 응용 프로그램의 서로 다른 픽셀 밀도 표시 간 이동 하면 일관 되도록 콘텐츠 확장 됩니다. 기본 디스플레이 고밀도 (200% 배율)는 보조 디스플레이가 표준 밀도 (100%) 하는 경우 Windows는 자동으로 줄이고 응용 프로그램 창 내용 보조 디스플레이에 (1 픽셀에서 렌더링 되는 모든 4 픽셀에 대해 표시 되는 응용 프로그램)입니다.  
  
-   Windows는 픽셀 밀도 대 한 크기 조정 및 표시 (Windows 7 이상, OEM 구성 가능)에 대 한 거리 보기 오른쪽 기본값으로 설정 됩니다.  
  
-   280 ppi (현재 Windows 8.1 S14)를 초과 하는 새 장치에서 Windows를 콘텐츠를 250% 확장할 자동으로 수 있습니다.  
  
 Windows에 향상 된 픽셀 수를 활용 하기 위해 ui 크기 조정을 처리 하는 방법이 있습니다. 응용 프로그램 자체 "시스템 DPI를 인식 합니다."를 선언 하 여이 시스템에 옵트인 이렇게 하지 않으면 응용 프로그램 시스템에 의해 확장 됩니다. 이 "유사" 사용자 경험을 여기서는 전체 응용 프로그램은 균일 하 게 픽셀 확대 될 수 있습니다. 예를 들어:  
  
 ![DPI 문제 퍼지](../extensibility/media/dpi-issues-fuzzy.png "DPI 문제 퍼지")  
  
 Visual Studio은 DPI 배율에서 인식 되 고에 옵트인 하 고 따라서은 가상화 되지 않습니다"."  
  
 Windows (및 Visual Studio) 시스템으로 설정 하는 요소 크기 조정을 처리 하는 여러 가지 방법으로 여러 가지 UI 기술을 활용 합니다. 예를 들어:  
  
-   WPF (단위, 픽셀이 아닌) 장치 독립적인 방식으로 컨트롤을 측정합니다. WPF UI 현재 DPI에 대해 자동으로 조정합니다.  
  
-   UI 프레임 워크에 관계 없이 모든 텍스트 크기 포인트 단위로 표현 않으며 따라서 시스템에 의해 DPI 독립적으로 처리 됩니다. Win32, WinForms, 및 WPF 텍스트 이미 확장할 올바르게 디스플레이 장치에 그리는 경우.  
  
-   Win32/WinForms 대화 상자 및 창 크기를 조정 텍스트로-예를 들어 그리드, 흐름 및 테이블 레이아웃 패널을 통해 레이아웃을 사용 하도록 설정할 수 있어야 합니다. 이러한 글꼴 크기 증가 배율이 조정 되지 않으므로 하드 코드 된 픽셀 위치 방지를 사용 하도록 설정 합니다.  
  
-   시스템에서 제공 하는 아이콘이 나 시스템 메트릭을 (예를 들어 SM_CXICON 및 SM_CXSMICON)에 따라 리소스는 이미 확장.  
  
## <a name="older-win32-gdi-gdi-and-winforms-based-ui"></a>이전 Win32 (GDI, GDI +) 및 WinForms 기반 UI  
 WPF DPI를 인식 높은 이미 상태인 동안 Win32/GDI 기반 코드의 대부분 되지로 기록 되었으나 염두에서 DPI 인식 합니다. DPI 조정 Api를 제공 했습니다. Win32 문제를 수정 제품 전체에서 일관 되 게 사용 해야 합니다. Visual Studio는 도우미 메서드를 제공 하는 제품 전체에서 일관성을 확인 하 고 기능이 중복을 방지 하려면 클래스 라이브러리입니다.  
  
## <a name="high-resolution-images"></a>고해상도 이미지  
 이 섹션은 주로 Visual Studio 2013을 확장 하는 개발자가 됩니다. Visual Studio 2015에 대 한 Visual Studio에 기본 제공 되는 이미지 서비스를 사용 합니다. 지원/대상 여러 버전의 Visual Studio에 필요 하 고 따라서 2015에서 이미지 서비스를 사용 하 여이 옵션이 아닌 이전 버전에 존재 하지 않는 알 수 있습니다. 이 여기서는 또한 다음입니다.  
  
## <a name="scaling-up-images-that-are-too-small"></a>되기에는 너무 작은 이미지를 배율 조정  
 되기에는 너무 작은 이미지 수 "확장" 하 고 GDI 및 몇 가지 일반적인 방법을 사용 하 여 WPF에 렌더링 합니다. 관리 되는 DPI 도우미 클래스는 확장 아이콘, 비트맵, imagestrips, 및 imagelists 주소로 내부 및 외부 Visual Studio 통합을 사용할 수 있습니다. Win32 기반 네이티브 C / C + + 도우미는 HICON, HBITMAP, HIMAGELIST, 및 VsUI::GdiplusImage 크기 조정에 사용할 수 있습니다. 일반적으로 비트맵의 배율 도우미 라이브러리에 대 한 참조를 포함 한 후 한 줄 변경만 필요 합니다. 예를 들어:  
  
```cpp  
(Unmanaged)  VsUI::DpiHelper::LogicalToDeviceUnits(&hBitmap);  
```  
  
```csharp  
(WinForms) DpiHelper.LogicalToDeviceUnits(ref image);  
```  
  
 Imagelist를 크기 조정 imagelist 로드할 때 완료 된 또는 실행 시 추가 여부 따라 다릅니다. 로드 시 완료 하는 경우에 비트맵와 마찬가지로 LogicalToDeviceUnits() imagelist를 호출 합니다. 코드를 imagelist를 작성 하기 전에 개별 비트맵을 로드 해야 하는 경우에 imagelist의 이미지 크기를 확장 해야 합니다.  
  
```csharp  
imagelist.ImageSize = DpiHelper.LogicalToDeviceUnits(imagelist.ImageSize);  
```  
  
 네이티브 코드에서 imagelist를 다음과 같이 만들 때 차원 확장 될 수 있습니다.  
  
```cpp  
ImageList_Create(VsUI::DpiHelper::LogicalToDeviceUnitsX(16),VsUI::DpiHelper::LogicalToDeviceUnitsY(16), ILC_COLOR32|ILC_MASK, nCount, 1);  
```  
  
 함수 라이브러리의 크기 조정 알고리즘을 지정할 수 있음 때 imagelists를 배치 하려면 크기 조정 이미지 투명도, 사용 되는 배경색을 지정 해야 또는 NearestNeighbor 배율 (125%와 150% 왜곡 발생)를 사용 합니다.  
  
 참조는 <xref:Microsoft.VisualStudio.PlatformUI.DpiHelper> MSDN에 대 한 설명서입니다.  
  
 다음 표에서 요소 크기 조정 이미지를 해당 DPI에서 확보 해야 하는 방법의 예를 보여 줍니다. 녹색에서 이미지 표시 (100%에서 200 %DPI 배율)는 Visual Studio 2013부터 우리의 모범 사례:  
  
 ![DPI 문제 배율](../extensibility/media/dpi-issues-scaling.png "DPI 문제 배율")  
  
## <a name="layout-issues"></a>레이아웃 문제  
 절대 위치 (특히, 픽셀 단위)를 사용 하는 대신 주로 UI 조정에 및 서로 기준으로 요소를 유지 하 여 일반적인 레이아웃 문제를 방지할 수 있습니다. 예를 들어:  
  
-   레이아웃/텍스트 위치를 이미지에 대 한 계정으로 조정 해야 합니다.  
  
-   표에서 열 너비가 수직 텍스트에 대 한 조정 해야 합니다.  
  
-   하드 코드 된 크기나 요소 사이의 간격 크기 조정할 수 해야 합니다. 텍스트 크기에 대해서만 기반 하는 크기는 글꼴 자동으로 조정 되므로 일반적으로 세밀 하 게 합니다.  
  
 사용할 수 있는 도우미 함수는 <xref:Microsoft.VisualStudio.PlatformUI.DpiHelper> X 및 Y 축에서 크기 조정을 허용 하는 클래스:  
  
-   LogicalToDeviceUnitsX/LogicalToDeviceUnitsY (함수 X의 크기 조정을 허용 / Y 축)  
  
-   int 공간 = DpiHelper.LogicalToDeviceUnitsX (10);  
  
-   int 높이 = VsUI::DpiHelper::LogicalToDeviceUnitsY(5);  
  
 확장 Rect, 지점 및 크기와 같은 개체를 허용 하도록 LogicalToDeviceUnits 오버 로드가 있습니다.  
  
## <a name="using-the-dpihelper-libraryclass-to-scale-images-and-layout"></a>이미지 배율을 조정 및 레이아웃을 DPIHelper 라이브러리/클래스를 사용 하 여  
 Visual Studio DPI 도우미 라이브러리 네이티브 및 관리 되는 양식에서 사용할 수 있으며 다른 응용 프로그램에서 Visual Studio shell 외부에서 사용할 수 있습니다.  
  
 라이브러리를 사용 하려면로 이동 된 [Visual Studio VSSDK 확장성 샘플](https://github.com/Microsoft/VSSDK-Extensibility-Samples) 높은 DPI_Images_Icons 샘플을 복제 하 고  
  
 소스 파일에서 VsUIDpiHelper.h 등 VsUI::DpiHelper 클래스의 정적 함수를 호출 합니다.  
  
```cpp  
#include "VsUIDpiHelper.h"  
  
int cxScaled = VsUI::DpiHelper::LogicalToDeviceUnitsX(cx);  
VsUI::DpiHelper::LogicalToDeviceUnits(&hBitmap);  
  
```  
  
> [!NOTE]
>  모듈 수준 또는 클래스 수준 정적 변수에 도우미 함수를 사용 하지 마십시오. 라이브러리에 사용 하 고 정적 스레드를 동기화 하 고 순서 초기화 문제가 발생할 수 있습니다. 비정적 멤버 변수를 해당 정적 변수를 변환 하거나 (첫 번째 액세스에서 건설 가져오기) 하도록 함수를 래핑하십시오.  
  
 Visual Studio 환경 내에서 실행 될 관리 코드에서 DPI 도우미 함수에 액세스 합니다.  
  
-   사용 중인 프로젝트 셸 MPF의 최신 버전을 참조 해야 합니다. 예를 들어:  
  
    ```csharp  
    <Reference Include="Microsoft.VisualStudio.Shell.14.0.dll" />  
    ```  
  
-   프로젝트에 대 한 참조가 확인 **System.Windows.Forms**, **PresentationCore**, 및 **PresentationUI**합니다.  
  
-   코드에서 사용 된 **Microsoft.VisualStudio.PlatformUI** DpiHelper 클래스의 정적 함수 네임 스페이스를 호출 합니다. 지원 되는 종류 (포인트, 크기, 사각형 및 등)는 새로운 반환 하는 확장 함수 개체를 확장할 제공. 예를 들어:  
  
    ```csharp  
    using Microsoft.VisualStudio.PlatformUI;  
    double x = DpiHelper.LogicalToDeviceUnitsX(posX);  
    Point ptScaled = ptOriginal.LogicalToDeviceUnits();  
    DpiHelper.LogicalToDeviceUnits(ref bitmap);  
  
    ```  
  
## <a name="dealing-with-wpf-image-fuzziness-in-zoomable-ui"></a>가능한 UI에서 WPF 이미지가 흐릿해 처리  
 WPF에서 비트맵 자동으로 조정 됩니다 WPF에서 그림 이나 큰 스크린 샷을에 적합 하지만 인식된 허용량을 가져오기 때문에 메뉴 항목 아이콘에 적합 하지 않은 고품질 쌍입방 알고리즘 (기본값)을 사용 하 여 현재 DPI 확대/축소 수준에 대 한 .  
  
 권장 사항:  
  
-   로고 이미지 및 배너 아트 워크를 기본에 대 한 <xref:System.Windows.Media.BitmapScalingMode> 모드를 크기 조정 사용 될 수 있습니다.  
  
-   메뉴 항목과도 해 이미지에 대 한는 <xref:System.Windows.Media.BitmapScalingMode> 허용량 (%200 및 300%)에서 제거 하는 다른 왜곡 아티팩트를 발생 하지 않는 경우에 사용 해야 합니다.  
  
-   큰 확대/축소 수준을 100% (예를 들어 250% 또는 %350)의 배수로 하지,에 대 한 유사 항목, 바랜 UI 발생 쌍입방을 사용 하 여의 해 이미지 크기 조정 합니다. 첫 번째 100% (예: 200% 또는 300%)의 가장 큰 배수로 NearestNeighbor와 이미지의 크기 조정 및 여기에서 쌍입방으로 확장 하 여 더 나은 결과 얻습니다. 특별 한 경우 참조: 자세한 내용은 수준 큰 DPI에 대 한 WPF 이미지 prescaling 합니다.  
  
 Microsoft.VisualStudio.PlatformUI 네임 스페이스에 DpiHelper 클래스 멤버를 제공 <xref:System.Windows.Media.BitmapScalingMode> 바인딩에 대 한 사용할 수 있습니다. Visual Studio 셸을 크기 조정 모드 제품 전체에서 일관 되 게 DPI 배율 인수에 따라 비트맵을 제어 하는 허용 됩니다.  
  
 XAML에서 사용 하려면 다음을 추가 합니다.  
  
```xaml  
xmlns:vsui="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
  
<Setter Property="RenderOptions.BitmapScalingMode" Value="{x:Static vs:DpiHelper.BitmapScalingMode}" />  
  
```  
  
 이미 Visual Studio shell 최상위 창 및 대화 상자에서이 속성을 설정합니다. 이미 Visual Studio에서 실행 하는 WPF 기반 UI 것을 상속 합니다. 설정 사용자 인터페이스의 특정 말에 전파 하지 않습니다, XAML/WPF UI의 루트 요소에 대해 설정할 수 있습니다. Blend 같은 중 실행 되는 디자이너 창 처리 및이 발생 하는 위치, 팝업 Win32 부모 요소에 포함 됩니다.  
  
 일부 UI가 Visual Studio 텍스트 편집기 및 WPF 기반 디자이너 (WPF 데스크톱 및 Windows 스토어)와 같은 시스템 집합 DPI 확대/축소 수준을 독립적으로 확장할 수 있습니다. 이러한 경우 DpiHelper.BitmapScalingMode 사용 해야 합니다. 편집기에서이 문제를 해결 하려면 사용자 지정 속성을 만든 IDE 팀 RenderOptions.BitmapScalingMode 제목 있습니다. HighQuality 또는 NearestNeighbor 시스템과 UI의 결합 된 확대/축소 수준에 따라 해당 속성 값을 설정 합니다.  
  
## <a name="special-case-prescaling-wpf-images-for-large-dpi-levels"></a>특별 한 경우: prescaling 큰 DPI 수준에 대 한 WPF 이미지  
 100% (예를 들어 250%, 350%, 및 등)의 배수로 없는 매우 큰 확대/축소 수준에 대 한 유사 항목, 바랜 UI에서 쌍입방 결과로도 해 이미지 크기 조정 합니다. 선명한 텍스트와 함께 이러한 이미지의 효과 주기는 거의 것과 유사 하는 것 처럼 보입니다. 사람 마다 하 고 텍스트와 관련 하 여 포커스 없이 가깝게 이미지가 나타납니다. 첫 번째 100% (예: 200% 또는 300%)의 가장 큰 배수로 NearestNeighbor와 이미지의 크기 조정 및 나머지 (추가 50%)로 쌍입방 사용해 서 확장 크기 조정의 결과이 확대 된 크기를 향상 시킬 수 있습니다.  
  
 다음은 결과의 차이의 예는 첫 번째 이미지 조정 된 200% 250%-> 100%-> 향상 된 이중 크기 조정 알고리즘을 사용 하 고-> 250% 쌍입방 100%가 포함 된 두 번째 식입니다.  
  
 ![DPI 문제 배율 Double 예제](../extensibility/media/dpi-issues-double-scaling-example.png "DPI 문제 배율 Double 예제")  
  
 각 이미지 요소를 표시 하기 위한이 이중 크기 조정, XAML 태그를 사용 하는 UI를 사용 하도록 설정 하려면 수정 해야 합니다. 다음 예에서는 DpiHelper 라이브러리 및 Shell.12/14를 사용 하 여 Visual Studio에서 WPF의 이중 확장을 사용 하는 방법을 보여 줍니다.  
  
 1 단계: 300%에서 200% 이미지 Prescale 등에 NearestNeighbor를 사용 하 여입니다.  
  
 바인딩에서 또는 XAML 태그 확장으로 적용할 변환기를 사용 하 여 이미지를 prescale 합니다. 예를 들어:  
  
```xaml  
<vsui:DpiPrescaleImageSourceConverter x:Key="DpiPrescaleImageSourceConverter" />  
  
<Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" Width="16" Height="16" />  
  
<Image Source="{vsui:DpiPrescaledImage Images/Help.png}" Width="16" Height="16" />  
  
```  
  
 하는 경우 이미지도 테마를 적용할 수 (아니지만 대부분, 해야) 태그를 먼저 이미지 및 다음 미리 확장에서 테마를 수행 하는 다른 변환기를 사용할 수 있습니다. 태그를 사용할 수 <xref:Microsoft.VisualStudio.PlatformUI.DpiPrescaleThemedImageConverter> 또는 <xref:Microsoft.VisualStudio.PlatformUI.DpiPrescaleThemedImageSourceConverter>원하는 변환 출력에 따라 합니다.  
  
```xaml  
<vsui:DpiPrescaleThemedImageSourceConverter x:Key="DpiPrescaleThemedImageSourceConverter" />  
  
<Image Width="16" Height="16">  
  <Image.Source>  
    <MultiBinding Converter="{StaticResource DpiPrescaleThemedImageSourceConverter}">  
      <Binding Path="Icon" />  
      <Binding Path="(vsui:ImageThemingUtilities.ImageBackgroundColor)"    
               RelativeSource="{RelativeSource Self}" />  
      <Binding Source="{x:Static vsui:Boxes.BooleanTrue}" />  
    </MultiBinding>  
  </Image.Source>  
</Image>  
```  
  
 2 단계: 현재 DPI에 대 한 최종 크기가 올바른지 확인 합니다.  
  
 WPF는 UIElement에 설정 BitmapScalingMode 속성을 사용 하 여 현재 DPI에 대 한 UI 조정 하기 때문에 소스 2-3 배 것 보다 더 큰 보이는지 prescaled 이미지를 사용 하 여 이미지 컨트롤은 있어야 합니다. 다음 몇 가지 방법이이 효과 카운터:  
  
-   100%에 원본 이미지의 치수를 알고 있는 경우 이미지 컨트롤의 정확한 크기를 지정할 수 있습니다. 이러한 크기를 확장 하기 전에 UI의 크기를 적용 반영 합니다.  
  
    ```xaml  
    <Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" Width="16" Height="16" />  
    ```  
  
-   원본 이미지의 크기를 알 수 없는 경우는 LayoutTransform 최종 이미지 개체를 축소 하 사용할 수 있습니다. 예를 들어:  
  
    ```xaml  
    <Image Source="{Binding Path=SelectedImage, Converter={StaticResource DpiPrescaleImageSourceConverter}}" >  
        <Image.LayoutTransform>  
         <ScaleTransform  
             ScaleX="{x:Static vsui:DpiHelper.PreScaledImageLayoutTransformScale}"  
             ScaleY="{x:Static vsui:DpiHelper.PreScaledImageLayoutTransformScale}" />  
        </Image.LayoutTransform>  
    </Image>  
    ```  
  
## <a name="enabling-hdpi-support-to-the-weboc"></a>에 WebOC HDPI 지원을 사용 하도록 설정  
 기본적으로 WebOC 컨트롤 (예: WPF 또는 IWebBrowser2 인터페이스에서 WebBrowser 컨트롤) HDPI 검색 및 지원을 사용할 수 없습니다. 결과 포함된 된 컨트롤을 너무 작은 고해상도 디스플레이에 표시 콘텐츠로 됩니다. 높은 DPI 지원 특정 웹 WebOC 인스턴스에서 사용 하는 방법을 설명 합니다.  
  
 IDocHostUIHandler 인터페이스를 구현 (MSDN 문서에 참조는 [IDocHostUIHandler](http://msdn.microsoft.com/library/aa753260.aspx) 인터페이스):  
  
```idl  
[ComImport, InterfaceType(ComInterfaceType.InterfaceIsIUnknown),  
 Guid("BD3F23C0-D43E-11CF-893B-00AA00BDCE1A")]  
public interface IDocHostUIHandler  
{  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ShowContextMenu(  
        [In, MarshalAs(UnmanagedType.U4)] int dwID,  
        [In] POINT pt,  
        [In, MarshalAs(UnmanagedType.Interface)] object pcmdtReserved,  
        [In, MarshalAs(UnmanagedType.IDispatch)] object pdispReserved);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetHostInfo([In, Out] DOCHOSTUIINFO info);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ShowUI(  
        [In, MarshalAs(UnmanagedType.I4)] int dwID,  
        [In, MarshalAs(UnmanagedType.Interface)] object activeObject,  
        [In, MarshalAs(UnmanagedType.Interface)] object commandTarget,  
        [In, MarshalAs(UnmanagedType.Interface)] object frame,  
        [In, MarshalAs(UnmanagedType.Interface)] object doc);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int HideUI();  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int UpdateUI();  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int EnableModeless([In, MarshalAs(UnmanagedType.Bool)] bool fEnable);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int OnDocWindowActivate([In, MarshalAs(UnmanagedType.Bool)] bool fActivate);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int OnFrameWindowActivate([In, MarshalAs(UnmanagedType.Bool)] bool fActivate);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int ResizeBorder(  
        [In] COMRECT rect,  
        [In, MarshalAs(UnmanagedType.Interface)] object doc,  
        bool fFrameWindow);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int TranslateAccelerator(  
        [In] ref MSG msg,  
        [In] ref Guid group,  
        [In, MarshalAs(UnmanagedType.I4)] int nCmdID);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetOptionKeyPath(  
        [Out, MarshalAs(UnmanagedType.LPArray)] string[] pbstrKey,  
        [In, MarshalAs(UnmanagedType.U4)] int dw);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetDropTarget(  
        [In, MarshalAs(UnmanagedType.Interface)] IOleDropTarget pDropTarget,  
        [MarshalAs(UnmanagedType.Interface)] out IOleDropTarget ppDropTarget);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int GetExternal([MarshalAs(UnmanagedType.IDispatch)] out object ppDispatch);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int TranslateUrl(  
        [In, MarshalAs(UnmanagedType.U4)] int dwTranslate,  
        [In, MarshalAs(UnmanagedType.LPWStr)] string strURLIn,  
        [MarshalAs(UnmanagedType.LPWStr)] out string pstrURLOut);  
    [return: MarshalAs(UnmanagedType.I4)]  
    [PreserveSig]  
    int FilterDataObject(  
        IDataObject pDO,  
        out IDataObject ppDORet);  
    }   
```  
  
 필요에 따라 ICustomDoc 인터페이스를 구현 (MSDN 문서에 참조는 [ICustomDoc](http://msdn.microsoft.com/library/aa753272.aspx) 인터페이스):  
  
```idl  
[InterfaceType(ComInterfaceType.InterfaceIsIUnknown),  
 Guid("3050F3F0-98B5-11CF-BB82-00AA00BDCE0B")]  
public interface ICustomDoc  
{  
    void SetUIHandler(IDocHostUIHandler pUIHandler);  
}   
```  
  
 IDocHostUIHandler WebOC의 문서와 구현 하는 클래스를 연결 합니다. 위의 ICustomDoc 인터페이스를 구현한 경우 다음 바로 WebOC의 문서 속성은 사용할는 ICustomDoc 캐스팅와 IDocHostUIHandler를 구현 하는 클래스를 전달 하 여 SetUIHandler 메서드를 호출 합니다.  
  
```csharp  
// "this" references that class that owns the WebOC control and in this case also implements the IDocHostUIHandler interface  
ICustomDoc customDoc = (ICustomDoc)webBrowser.Document;  
customDoc.SetUIHandler(this);  
  
```  
  
 ICustomDoc 인터페이스를 구현 하지 않은 경우 다음 WebOC의 문서 속성은 사용할으로 해야 하는 IOleObject 캐스팅 하 고 IDocHostUIHandler를 구현 하는 클래스 전달 SetClientSite 메서드를 호출 합니다. GetHostInfo 메서드 호출에 전달 된 DOCHOSTUIINFO에 DOCHOSTUIFLAG_DPI_AWARE 플래그를 설정 합니다.  
  
```csharp  
public int GetHostInfo(DOCHOSTUIINFO info)  
{  
    // This is what the default site provides.  
    info.dwFlags = (DOCHOSTUIFLAG)0x5a74012;  
    // Add the DPI flag to the defaults  
    info.dwFlags |=.DOCHOSTUIFLAG.DOCHOSTUIFLAG_DPI_AWARE;  
    return S_OK;  
}  
```  
  
 이 WebOC 컨트롤 HPDI를 지 원하는 데 필요한 모든 이어야 합니다.  
  
## <a name="tips"></a>팁  
  
1.  WebOC 컨트롤의 문서 속성이 변경 되 면 IDocHostUIHandler 클래스와 문서를 다시 연결 해야 합니다.  
  
2.  위의 옵션을 사용할 경우 DPI 플래그에 대 한 변경을 가져오지 못함 WebOC는 알려진된 문제가 있습니다. 이 문제를 해결 하는 가장 안정적인 방법은 의미 확대/축소 비율에 대 한 값이 두 개의 서로 다른 두 번 호출 하 고 WebOC의 광학 확대/축소를 설정/해제 하는 합니다. 또한이 해결 방법은 필요한 경우 모든 탐색 호출에서 수행 해야 할 수 있습니다.  
  
    ```csharp  
    // browser2 is a SHDocVw.IWebBrowser2 in this case  
    // EX: Call the Exec twice with DPI%-1 and then DPI% as the zoomPercent values  
    IOleCommandTarget cmdTarget = browser2.Document as IOleCommandTarget;  
    if (cmdTarget != null)  
    {  
        object commandInput = zoomPercent;  
        cmdTarget.Exec(IntPtr.Zero,  
                       OLECMDID_OPTICAL_ZOOM,  
                       OLECMDEXECOPT_DONTPROMPTUSER,  
                       ref commandInput,  
                       ref commandOutput);  
    }  
    ```
---
title: "XAML 디자이너에서 개체를 레이아웃 컨테이너로 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 29c80c38-0fa3-48d6-b3a8-3b864f482e44
caps.latest.revision: 15
caps.handback.revision: 15
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# XAML 디자이너에서 개체를 레이아웃 컨테이너로 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

페이지에 개체를 표시할 위치를 가정해 보겠습니다. 개체로는 이미지, 단추, 비디오 등을 들 수 있습니다.  개체를 행 및 열로 표시하거나 가로나 세로로 한 줄로 표시하거나 고정된 위치에 표시할 수 있습니다.  
  
 페이지에 어떻게 표시할지 결정했으면 레이아웃 패널을 선택합니다.  개체를 추가할 대상이 필요하기 때문에 모든 페이지 작업은 여기에서 시작됩니다.  기본적으로 **Grid**가 설정되지만 변경할 수 있습니다.  
  
 레이아웃 패널은 페이지에 개체를 정렬하는 데 도움이 될 뿐만 아니라 그 이상의 역할을 합니다.  서로 다른 화면 크기 및 해상도를 설계하는 데에도 도움이 됩니다.  사용자가 앱을 실행할 때 레이아웃 패널의 모든 항목은 장치의 실제 화면 공간에 맞게 크기가 조정됩니다.  자동으로 크기가 조정되지 않도록 하려면 레이아웃 일부 또는 전체 레이아웃에 대해 이러한 동작을 재정의할 수 있습니다.  이러한 동작은 높이 및 너비 속성을 사용하여 제어할 수 있습니다.  
  
 이 페이지에서는 레이아웃 패널 및 컨트롤에 대해 설명하고 패널 및 컨트롤을 시작하는 데 도움이 되는 짧은 비디오로 안내해 줍니다.  
  
> [!NOTE]
>  동영상 중 일부에서는 Visual Studio 및 Blend for Visual Studio와 동일한 XAML 디자이너를 사용하는 Blend 또는 Expression Blend를 다룰 수 있습니다.  
  
## 레이아웃 패널  
 다음 레이아웃 패널 중 하나를 선택하여 페이지를 시작합니다.  페이지에 둘 이상의 레이아웃 패널을 지정할 수 있습니다.  예를 들어 **Grid** 레이아웃 패널에서 시작한 후 **Grid**의 영역에 **StackPanel**을 추가하여 해당 요소에서 컨트롤을 세로로 정렬할 수 있습니다.  
  
 다음은 가장 많이 사용되는 레이아웃 패널이며, 다른 레이아웃 패널도 있습니다.  이러한 컨트롤은 모두 **자산** 패널에 있습니다.  
  
-   [모눈](#Grid)  
  
-   [UniformGrid](#Uniform)  
  
-   [Canvas](#Canvas)  
  
-   [StackPanel](#Stack)  
  
-   [WrapPanel](#Wrap)  
  
-   [DockPanel](#Dock)  
  
###  <a name="Grid"></a> 모눈  
 개체를 행 및 열로 정렬합니다.  
  
 **짧은 동영상 보기:** ![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.png "BldAdminConsoleInitialConfigIcon") [모눈 사용](http://www.popscreen.com/v/6A4hj/Microsoft-Expression-Blend-Using-Grids)  
  
###  <a name="Uniform"></a> UniformGrid  
 개체를 동일하게 또는 균일하게 모눈 영역에 정렬합니다.  이 패널은 이미지의 목록을 정렬할 때 매우 유용 합니다.  
  
 \(WPF 프로젝트에만 사용 가능\)  
  
 **짧은 동영상 보기:** ![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.png "BldAdminConsoleInitialConfigIcon") [UniformGrid 작업](http://www.popscreen.com/v/6A4iq/Microsoft-Expression-Blend-Working-with-a-UniformGrid)  
  
###  <a name="Canvas"></a> Canvas  
 원하는 방식으로 개체를 정렬합니다.  사용자가 앱을 실행할 때 이러한 요소는 화면에서 고정 위치에 표시됩니다.  
  
 **짧은 동영상 보기:** ![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.png "BldAdminConsoleInitialConfigIcon") [캔버스 작업](http://www.popscreen.com/v/6A4hT/Microsoft-Expression-Blend-Working-with-the-Canvas)  
  
###  <a name="Stack"></a> StackPanel  
 개체를 가로 또는 세로로 한 줄로 정렬합니다.  
  
 **짧은 동영상 보기:** ![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.png "BldAdminConsoleInitialConfigIcon") [StackPanel 및 WrapPanel 작업](http://www.popscreen.com/v/6A4i5/Microsoft-Expression-Blend-Using-the-StackPanel-and-WrapPanel)  
  
###  <a name="Wrap"></a> WrapPanel  
 개체를 순서대로 왼쪽에서 오른쪽으로 정렬합니다.  패널의 맨 오른쪽 가장자리에 공간이 부족한 경우 콘텐츠를 다음 줄로 *줄바꿈*하며 왼쪽에서 오른쪽, 위쪽에서 아래쪽 가로로 배치됩니다.  위쪽에서 아래쪽, 왼쪽에서 오른쪽 세로로 배치할 수도 있습니다.  
  
 \(WPF 프로젝트에만 사용 가능\)  
  
 **짧은 동영상 보기:** ![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.png "BldAdminConsoleInitialConfigIcon") [StackPanel 및 WrapPanel 작업](http://www.popscreen.com/v/6A4i5/Microsoft-Expression-Blend-Using-the-StackPanel-and-WrapPanel)  
  
###  <a name="Dock"></a> DockPanel  
 개체가 패널의 한쪽 가장자리에 *고정*되도록 개체를 정렬합니다.  
  
 \(WPF 프로젝트에만 사용 가능\)  
  
 **짧은 동영상 보기:** ![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.png "BldAdminConsoleInitialConfigIcon") [WPF \- DockPanel](https://www.youtube.com/watch?v=EBH_OIM-zPo)  
  
## 레이아웃 컨트롤  
 개체를 레이아웃 컨트롤에도 추가할 수 있습니다.  이러한 개체는 레이아웃 패널만큼 기능이 다양하지는 않지만 특정 시나리오에서 유용할 수 있습니다.  
  
 다음은 가장 많이 사용되는 레이아웃 컨트롤이며, 다른 레이아웃 컨트롤도 있습니다.  이러한 컨트롤은 모두 **자산** 패널에 있습니다.  
  
-   [테두리](#Border)  
  
-   [Popup](#Popup)  
  
-   [ScrollViewer](#Scroll)  
  
-   [UniformGrid](#Uniform)  
  
-   [Viewbox](#View)  
  
###  <a name="Border"></a> 테두리  
 개체 주위에 테두리, 배경 또는 둘 다를 그립니다.  **Border**에는 개체를 하나만 추가할 수 있습니다.  둘 이상의 개체에 테두리나 배경을 적용하려면 레이아웃 패널을 **Border**에 추가합니다.  그런 다음 해당 패널 또는 컨트롤에 개체를 추가합니다.  
  
 **짧은 동영상 보기:** ![설치된 기능 구성](../designers/media/bldadminconsoleinitialconfigicon.png "BldAdminConsoleInitialConfigIcon") [테두리 작업](http://www.popscreen.com/v/6A4hB/Microsoft-Expression-Blend-Working-with-Borders)  
  
###  <a name="Popup"></a> Popup  
 창의 사용자에게 정보나 옵션을 표시합니다.  **Popup**에 개체를 하나만 추가할 수 있습니다.  기본적으로 **Popup**에는 **Grid**가 포함되지만 변경할 수 있습니다.  
  
###  <a name="Scroll"></a> ScrollViewer  
 페이지나 페이지의 특정 영역을 스크롤할 수 있습니다.  **ScrollViewer**에 개체를 하나만 추가할 수 있으므로 **Grid** 또는 **StackPanel** 등과 같은 레이아웃 패널을 추가합니다.  
  
###  <a name="View"></a> Viewbox  
 확대\/축소 컨트롤과 유사하게 개체의 비율 크기를 조정합니다.  **Viewbox**에 하나의 개체만 추가할 수 있습니다.  둘 이상의 개체에 해당 효과를 적용하려면 레이아웃 패널을 **ViewBox**에 추가한 후 컨트롤을 해당 레이아웃 패널에 추가합니다.  
  
 \(WPF 프로젝트에만 사용 가능\)  
  
## 참고 항목  
 [XAML Designer에서의 요소 작업](../designers/working-with-elements-in-xaml-designer.md)   
 [XAML 디자이너를 사용하여 UI 만들기](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)
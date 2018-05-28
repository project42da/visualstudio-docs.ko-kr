---
title: Working with elements in XAML Designer
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
ms.assetid: a29690bf-f212-4ac6-a77a-adc53d14102e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 676c8767691610349cc2eee4c09970318feda9f5
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# <a name="working-with-elements-in-xaml-designer"></a>Working with elements in XAML Designer
코드의 XAML에 또는 XAML 디자이너를 사용하여 컨트롤, 레이아웃 및 모양과 같은 요소를 추가할 수 있습니다. 이 항목에서는 Visual Studio 또는 Blend for Visual Studio의 XAML 디자이너에서 요소에 대해 작업하는 방법을 설명합니다.

## <a name="adding-an-element-to-a-layout"></a>레이아웃에 요소 추가
 *레이아웃*은 UI에서 요소의 크기를 조정하고 배치하는 프로세스입니다. 시각적 요소를 배치하려면 [패널](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.panel.aspx) 레이아웃에 가져다 놓아야 합니다. `Panel`에는 [FrameworkElement](http://msdn.microsoft.com/library/windows/apps/br208706.aspx) 형식의 컬렉션인 자식 속성이 있습니다. [Canvas](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.canvas.aspx), [StackPanel](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.stackpanel.aspx) 및 [Grid](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx)와 같은 다양한 `Panel` 자식 요소를 사용하여 레이아웃 컨테이너 역할을 하고, 페이지에서 요소를 배치 및 정렬할 수 있습니다.

 기본적으로는 `Grid` 패널은 페이지 또는 폼 내에서 최상위 레이아웃 컨테이너로 사용됩니다. 최상위 페이지 레이아웃에서 패널, 컨트롤 또는 기타 요소를 추가할 수 있습니다.

#### <a name="to-add-an-element-to-a-layout"></a>레이아웃에 요소를 추가하려면

-   XAML 디자이너에서 다음 중 하나를 수행합니다.

    -   **도구 상자**에서 요소를 두 번 클릭하거나 도구 상자에서 요소를 선택하고 Enter 키를 누릅니다.

    -   요소를 **도구 상자**에서 아트보드로 끌어 놓습니다.

    -   **도구 상자**에서 그리기 도구(예: [타원](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.ellipse.aspx) 또는 [사각형](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.shapes.rectangle.aspx)) 중 하나를 선택한 다음 활성 패널에서 요소를 그립니다.

## <a name="changing-the-layering-order-of-elements"></a>요소의 쌓기 순서 변경
 XAML 디자이너의 아트보드에 두 요소가 있는 경우 한 요소가 쌓기 순서대로 다른 요소 앞에 표시됩니다. [문서 개요] 창의 요소 목록 아래쪽에는 맨 앞의 요소가 있습니다(요소에 대해 **ZIndex** 속성이 설정된 경우 제외). 페이지, 폼 또는 레이아웃 컨테이너에 요소를 삽입할 때 요소가 활성 컨테이너 요소의 다른 요소 앞에 자동으로 배치됩니다. 요소의 순서를 변경하려면 **Order** 명령을 사용하거나 [문서 개요] 창의 개체 트리에서 요소를 끌면 됩니다.

#### <a name="to-change-the-layering-order"></a>쌓기 순서를 변경하려면

-   다음 작업 중 하나를 수행합니다.

    -   **문서 개요** 창에서 요소를 위쪽이나 아래쪽으로 끌어 원하는 쌓기 순서를 만듭니다.

    -   [문서 개요] 창 또는 쌓기 순서를 변경하려는 아트보드에서 요소를 마우스 오른쪽 단추로 클릭하고, **Order**를 가리키고, 다음 중 하나를 클릭합니다.

        -   **맨 앞으로 가져오기** - 요소를 순서의 맨 앞으로 가져옵니다.

        -   **앞으로 가져오기** - 요소를 순서대로 한 수준 앞으로 가져옵니다.

        -   **뒤로 보내기** - 요소를 순서대로 한 수준 뒤로 보냅니다.

        -   **맨 뒤로 보내기** - 요소를 순서의 맨 뒤로 보냅니다.

     [속성] 창의 **레이아웃** 섹션에서 **ZIndex** 속성을 변경합니다. 겹치는 요소의 경우 **ZIndex** 속성이 [문서 개요] 창에 표시되는 요소의 순서보다 우선합니다. 요소가 겹치는 경우 **Z 인덱스** 값이 더 큰 요소가 앞에 표시됩니다.

## <a name="changing-the-alignment-of-an-element"></a>요소의 맞춤 변경
 메뉴 명령을 사용하거나 맞춤선에 요소를 끌어 아트 보드에서 요소를 맞출 수 있습니다.

 *맞춤선*은 앱의 다른 요소를 기준으로 요소를 맞추는 데 도움이 되는 시각적 표시입니다.

#### <a name="to-align-two-or-more-elements-by-using-menu-commands"></a>메뉴 명령을 사용하여 둘 이상의 요소를 맞추려면

1.  맞출 요소를 선택합니다. 요소를 선택하는 동안 Ctrl 키를 누르고 두 개 이상의 요소를 선택할 수 있습니다.

2.  [속성] 창의 **레이아웃** 섹션에 있는 **HorizontalAlignment** 아래에서 **Left**, **Center**, **Right** 또는 **Stretch** 속성 중 하나를 선택합니다.

3.  [속성] 창의 **레이아웃** 섹션에 있는 **VerticalAlignment** 아래에서 **Top**, **Center**, **Bottom** 또는 **Stretch** 속성 중 하나를 선택합니다.

#### <a name="to-align-two-or-more-elements-by-using-snaplines"></a>맞춤선을 사용하여 둘 이상의 요소를 맞추려면

-   XAML 디자이너에서, 둘 이상의 요소가 포함된 레이아웃에서 가장자리가 다른 요소에 맞춰지도록 요소 중 하나를 끌거나 크기를 조정합니다.

     가장자리가 맞춰지는 경우 *맞춤 경계선*이 표시되어 맞춤을 나타냅니다. 맞춤 경계선은 빨간색 파선입니다. **맞춤선에 맞추기** 를 사용하도록 설정한 경우에만 맞춤 경계선이 나타납니다. 맞춤 경계선을 표시하는 아트보드의 그림은 [XAML 디자이너를 사용하여 UI 만들기](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)를 참조하세요.

## <a name="changing-an-elements-margins"></a>요소의 여백 변경
 XAML 디자이너의 여백이 아트 보드에서 요소 주위에 있는 빈 공간의 크기를 결정합니다. 예를 들어 여백은 요소의 바깥쪽 가장자리와 요소가 포함된 `Grid` 패널 경계 사이의 공백 양을 지정합니다. 여백은 `StackPanel`에 포함된 요소 간의 공백을 지정합니다.

#### <a name="to-change-an-elements-margins-in-the-properties-window"></a>속성 창에서 요소의 여백을 변경하려면

1.  여백을 변경할 요소를 선택합니다.

2.  [속성] 창의 **레이아웃** 아래에서 **Margin** 속성(**Top**, **Left**, **Right** 또는 **Bottom**) 값(픽셀 단위 또는 장치와 독립적인 단위, 대략 1/96인치)을 변경합니다.

#### <a name="to-change-an-elements-margins-in-the-artboard"></a>아트 보드에서 요소의 여백을 변경하려면

-   레이아웃 컨테이너를 기준으로 요소의 여백을 변경하려면 요소를 선택하거나 요소가 레이아웃 컨테이너에 있을 때 아트보드의 요소 주위에 나타나는*여백 표시기*를 클릭합니다. 여백 표시기를 표시하는 그림은 [XAML 디자이너를 사용하여 UI 만들기](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)를 참조하세요.

     여백 표시기가 가로 또는 세로로 열려 있으면 여백이 설정되지 않고, 여백 표시기가 닫히면 여백이 설정됩니다.

     여백 표시기를 열 때 반대쪽 여백이 설정되지 않았으면 반대쪽 여백이 아트보드에 있는 요소의 위치에 따라 올바른 값으로 설정됩니다. **Left** 및 **Right** 여백과 같은 반대쪽 여백에는 항상 하나 이상의 속성이 설정됩니다.

    > [!IMPORTANT]
    >  <xref:Windows.UI.Xaml.Controls.Canvas>와 같은 일부 레이아웃 컨테이너에 배치된 요소에는 여백 표시기가 없습니다. <xref:Windows.UI.Xaml.Controls.StackPanel>에 배치된 요소에는 `StackPanel`의 방향에 따라 왼쪽 및 오른쪽 여백이나 위쪽 및 아래쪽 여백에 대한 여백 표시기가 있습니다.

## <a name="grouping-and-ungrouping-elements"></a>요소 그룹화 및 그룹 해제
 XAML 디자이너에서 둘 이상의 요소를 그룹화하면 새로운 레이아웃 컨테이너가 생성되고 해당 컨테이너 내에 이러한 요소가 배치됩니다. 레이아웃 컨테이너에 둘 이상의 요소를 함께 배치하면 해당 그룹의 요소가 하나의 요소인 것처럼 그룹을 쉽게 선택하고, 이동하고, 변환할 수 있습니다. 요소를 그룹화하면 탐색 요소를 구성하는 단추처럼 특정 방식으로 서로 관련된 요소를 식별하는 데 도움이 됩니다. 요소를 그룹 해제할 때 요소가 포함된 레이아웃 컨테이너를 삭제하면 됩니다.

#### <a name="to-group-elements-into-a-new-layout-container"></a>새 레이아웃 컨테이너에 요소를 그룹화하려면

1.  그룹화할 요소를 선택합니다. (여러 요소를 선택하려면 Ctrl 키를 누른 상태에서 요소를 클릭합니다.)

2.  선택한 요소를 마우스 오른쪽 단추로 클릭하고, **그룹으로 묶기**를 가리킨 다음, 그룹을 배치할 레이아웃 컨테이너의 형식을 클릭합니다.

    > [!TIP]
    >  <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border> 또는 <xref:Windows.UI.Xaml.Controls.ScrollViewer>를 선택하여 요소를 그룹화하는 경우 새로운 <xref:Windows.UI.Xaml.Controls.Grid> 패널 내에서 <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border> 또는 <xref:Windows.UI.Xaml.Controls.ScrollViewer> 요소 내에 요소가 배치됩니다. 이러한 레이아웃 컨테이너 중 하나에서 요소를 그룹 해제하는 경우 <xref:Windows.UI.Xaml.Controls.Viewbox>, <xref:Windows.UI.Xaml.Controls.Border> 또는 <xref:Windows.UI.Xaml.Controls.ScrollViewer>만 삭제되고 <xref:Windows.UI.Xaml.Controls.Grid> 패널은 유지됩니다. `Grid` 패널을 삭제하려면 요소를 다시 그룹 해제하세요.

#### <a name="to-ungroup-elements-and-delete-the-layout"></a>요소를 그룹 해제하고 레이아웃을 삭제하려면

-   그룹 해제하려는 그룹을 마우스 오른쪽 단추로 클릭하고 **그룹 해제**를 클릭합니다.

 [문서 개요] 창에서 선택한 항목을 마우스 오른쪽 단추로 클릭하고 **그룹으로 묶기** 또는 **그룹 해제**를 클릭하여 요소를 그룹화하거나 그룹 해제할 수도 있습니다.

## <a name="resetting-the-element-layout"></a>요소 레이아웃 재설정
 레이아웃 다시 설정 명령을 사용하여 요소의 특정 레이아웃 속성에 대한 기본값을 복원할 수 있습니다. 이 명령을 사용하여 개별적으로 또는 전체적으로 요소의 여백, 맞춤, 너비, 높이 및 있는 크기를 재설정할 수 있습니다.

#### <a name="to-reset-the-element-layout"></a>요소 레이아웃을 재설정하려면

-   [문서 개요] 창 또는 아트보드에서 요소를 마우스 오른쪽 단추로 클릭하고, **레이아웃**, *PropertyName* **다시 설정**을 차례로 선택하거나(여기서 *PropertyName*은 다시 설정하려는 속성), **레이아웃**, **모두 다시 설정**을 차례로 선택하여 요소에 대한 모든 레이아웃 속성을 다시 설정합니다.

## <a name="see-also"></a>참고 항목

- [XAML 디자이너를 사용하여 UI 만들기](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)

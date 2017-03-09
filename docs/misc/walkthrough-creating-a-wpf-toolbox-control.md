---
title: "연습: WPF 도구 상자 컨트롤 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 상자"
  - "wpf"
ms.assetid: 8223c06e-f327-4778-8709-e0cc7eae2c78
caps.latest.revision: 15
caps.handback.revision: 15
manager: "douge"
---
# 연습: WPF 도구 상자 컨트롤 만들기
Visual Studio SDK에 포함된 WPF 도구 상자 컨트롤 템플릿을 사용하면 확장 기능이 설치될 때 자동으로 **도구 상자**에 추가되는 WPF\(Windows Presentation Foundation\) 컨트롤을 만들 수 있습니다. 이 연습에서는 템플릿을 사용하여 다른 사용자에게 배포할 수 있는 카운터 컨트롤을 만드는 방법을 보여 줍니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하세요.  
  
## Visual Studio에서 WPF 도구 상자 컨트롤 템플릿 찾기  
 WPF 도구 상자 컨트롤 템플릿은 다음 위치에 있는 **새 프로젝트** 대화 상자의 **설치된 템플릿**에서 사용할 수 있습니다.  
  
-   **Visual Basic**, **확장성**. 프로젝트의 언어는 Visual Basic입니다.  
  
-   **Visual C\#**, **확장성**. 프로젝트의 언어는 C\#입니다.  
  
## WPF 도구 상자 컨트롤 프로젝트 만들기  
 WPF 도구 상자 컨트롤 템플릿은 정의되지 않은 사용자 지정 컨트롤을 만들고 **도구 상자**에 컨트롤을 추가하는 데 필요한 모든 기능을 제공합니다.  
  
#### 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **설치된 템플릿**에서 원하는 프로그래밍 언어에 대한 노드를 클릭하고 **확장성**을 선택합니다. 프로젝트 형식 목록에서 **WPF 도구 상자 컨트롤**을 선택합니다.  
  
3.  **이름** 상자에 원하는 프로젝트 이름을 입력합니다. 이 연습에서는 `Counter`라는 이름을 사용합니다.**확인**을 클릭합니다.  
  
     사용자 지정 컨트롤, **도구 상자**의 컨트롤을 배치할 특성 및 배포의 VSIX 매니페스트가 포함된 솔루션이 만들어집니다.**이름** 상자는 솔루션 이름 및 네임스페이스 이름을 설정하지만 **도구 상자**에 나타나는 컨트롤 이름은 설정하지 않습니다. 이 이름은 이 연습의 뒷부분에서 설정합니다.  
  
### 컨트롤에 대한 사용자 인터페이스 작성  
 `Counter` 컨트롤에는 텍스트와 현재 카운트를 표시하는 <xref:System.Windows.Controls.Label> 컨트롤 2개와 카운트를 0으로 다시 설정하는 <xref:System.Windows.Controls.Button> 컨트롤 1개 등 총 3개의 자식 컨트롤이 필요합니다. 호스팅 응용 프로그램은 카운터를 프로그래밍 방식으로 증가시키므로 다른 자식 컨트롤이 필요하지 않습니다.  
  
##### 사용자 인터페이스를 작성하려면  
  
1.  **솔루션 탐색기**에서 ToolboxControl.cs를 두 번 클릭하여 디자이너에서 이 파일을 엽니다.  
  
     디자이너에 <xref:System.Windows.Controls.Button> 컨트롤이 포함된 <xref:System.Windows.Controls.Grid> 컨트롤이 표시됩니다.  
  
2.  <xref:System.Windows.Controls.Grid> 컨트롤을 선택한 다음 그리드의 왼쪽 위에 나타난 파란색 막대를 클릭하여 2개의 행과 2개의 열로 분할합니다.  
  
3.  **도구 상자**에서 그리드의 맨 위 행에 있는 각 셀로 <xref:System.Windows.Controls.Label> 컨트롤을 끌어 놓습니다.  
  
     이 시점에서 그리드의 요소를 정렬하여 컨트롤의 레이아웃을 설정할 수 있습니다. 또는 컨트롤의 크기가 텍스트에 맞게 동적으로 조정되도록 XAML\(Extensible Application Markup Language\)을 직접 편집할 수도 있습니다.  
  
4.  **XAML** 창에서 `RowDefinition` 요소의 높이와 `ColumnDefinition` 요소의 너비를 `"auto"`로 설정합니다.  
  
5.  단추와 두 레이블의 태그를 다음 예제와 같이 편집합니다.  
  
     [!code-xml[ToolboxControlWPF#11](../misc/codesnippet/Xaml/walkthrough-creating-a-wpf-toolbox-control_1.xaml)]  
  
     `Grid.Row` 및 `Grid.Column` 특성은 그리드에서의 요소 위치를 설정합니다. 단추의 `Grid.ColumnSpan` 특성을 사용하면 단추 너비에 관계없이 첫 번째 열의 크기를 조정할 수 있습니다.  
  
     레이블의 `Content` 특성은 `{Binding}` 구문을 사용하여 나중에 연습에서 정의할 속성에 바인딩합니다.  
  
### 사용자 정의 컨트롤 코딩  
 `Counter` 컨트롤은 카운터를 증가시키는 메서드, 카운터가 증가될 때마다 발생하는 이벤트, `Reset` 단추 및 현재 카운트, 표시 텍스트 및 `Reset` 단추의 표시\/숨김 여부를 저장하는 속성 3개를 노출합니다.`ProvideTolboxControl` 특성은 **도구 상자**에서 `Counter` 컨트롤이 나타나는 위치를 결정합니다.  
  
 이 컨트롤은 Windows Forms 컨트롤을 작성할 때와 같은 방식으로 작성할 수 있습니다. 즉, 이벤트 처리기와 공용 메서드를 사용하여 레이블의 콘텐츠를 설정합니다. 그러나 XAML 요소 특성을 코드의 속성에 직접 바인딩할 수 있도록 WPF에서 컨트롤의 데이터 컨텍스트를 설정할 수 있습니다. 이 모델은 컨트롤의 UI\(사용자 인터페이스\)와 핵심 기능을 구분하는 추상화 계층도 제공합니다.  
  
 이 연습에서는 데이터 모델 클래스를 만든 다음 컨트롤의 데이터 컨텍스트를 데이터 모델에 바인딩하는 방법을 보여 줍니다.  
  
##### 데이터 모델을 만들려면  
  
1.  단추를 두 번 클릭하여 코드 창을 엽니다.  
  
2.  파일의 맨 위에 <xref:System.ComponentModel> 네임스페이스에 대한 `using` 지시문을 추가합니다.  
  
3.  생성된 클래스 뒤에 공용 클래스를 만들어 데이터 컨텍스트를 정의합니다.  
  
     [!code-cs[ToolboxControlWPF#01](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_2.cs)]  
  
     이 클래스는 XAML 요소를 정의된 속성에 바인딩할 수 있는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현합니다.  
  
4.  <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스 선언을 마우스 오른쪽 단추로 클릭하고 **인터페이스 구현**을 클릭한 다음 **인터페이스 구현**을 다시 클릭합니다.  
  
     Visual Studio에서 `PropertyChanged` 이벤트를 선언합니다.  
  
5.  이벤트 선언 후 이벤트를 발생시키는 다음 전용 메서드를 만듭니다.  
  
     [!code-cs[ToolboxControlWPF#02](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_3.cs)]  
  
6.  컨트롤의 두 레이블 값을 저장할 다음과 같은 전용 필드 및 공용 속성을 만듭니다.  
  
     [!code-cs[ToolboxControlWPF#03](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_4.cs)]  
  
     `PropertyChanged` 이벤트가 발생하면 XAML 바인딩이 바인딩된 컨트롤의 콘텐츠를 업데이트합니다. 속성을 `public`으로 설정하면 디자이너가 사용할 수 있지만 이 데이터 컨텍스트를 바인딩할 때까지 다른 프로그램에서 사용할 수 없습니다.  
  
 데이터 모델을 만든 후에는 컨트롤의 코드 숨김 기능을 구현할 수 있습니다.  
  
##### 컨트롤을 구현하려면  
  
1.  컨트롤을 구현하는 partial 클래스 정의에서 클래스 이름을 마우스 오른쪽 단추로 클릭하고 **리팩터링**과 **이름 바꾸기**를 클릭한 다음 클래스 이름을 `Counter`로 바꿉니다. 이 이름은 확장 기능이 설치될 때 **도구 상자**에 표시됩니다.  
  
2.  클래스 정의 바로 위의 `ProvideToolboxControl` 특성 선언에서 첫 번째 매개 변수 값을 `"Counter"`에서 `"General"`로 변경합니다.**도구 상자**에서 컨트롤을 호스트할 항목 그룹의 이름이 설정됩니다.  
  
     다음 예제에서는 `ProvideToolboxControl` 특성 및 조정된 클래스 정의를 보여 줍니다.  
  
     [!code-cs[ToolboxControlWPF#04](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_5.cs)]  
  
3.  컨트롤의 데이터 컨텍스트를 저장할 전용 필드를 만들고 다음 예제와 같이 생성자에서 데이터 컨텍스트를 `MyDataModel` 클래스에 할당합니다.  
  
     [!code-cs[ToolboxControlWPF#05](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_6.cs)]  
  
4.  다음 공용 속성을 만들어 데이터 컨텍스트에서 `Text` 및 `Count` 속성을 미러링합니다.  
  
     [!code-cs[ToolboxControlWPF#06](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_7.cs)]  
  
     이러한 속성은 해당 컨트롤이 포함된 응용 프로그램에서 데이터 컨텍스트의 콘텐츠를 사용할 수 있도록 만듭니다.  
  
5.  카운터를 증가시키는 다음 공용 메서드와 호스팅 응용 프로그램에 알리는 이벤트를 만듭니다.  
  
     [!code-cs[ToolboxControlWPF#07](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_8.cs)]  
  
6.  다음과 같이 `Reset` 단추에 대한 클릭 처리기를 구현합니다.  
  
     [!code-cs[ToolboxControlWPF#08](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_9.cs)]  
  
7.  다음 공용 속성을 추가하여 `Reset` 단추를 표시하거나 숨깁니다.  
  
     [!code-cs[ToolboxControlWPF#09](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_10.cs)]  
  
## 컨트롤 테스트  
 **도구 상자** 컨트롤을 테스트하려면 먼저 개발 환경에서 테스트한 다음 호스팅 응용 프로그램에서 테스트합니다.  
  
#### 컨트롤을 테스트하려면  
  
1.  F5 키를 누릅니다.  
  
     프로젝트가 빌드되고 컨트롤이 설치된 Visual Studio의 두 번째 인스턴스가 열립니다.  
  
2.  Visual Studio의 새 인스턴스에서 WPF 응용 프로그램 프로젝트를 만듭니다.  
  
3.  **솔루션 탐색기**에서 MainWindow.xaml을 두 번 클릭하여 디자이너에서 이 파일을 엽니다.  
  
4.  **도구 상자**의 **일반** 섹션에서 **카운터** 컨트롤을 폼으로 끈 다음 선택합니다.  
  
     **속성** 창에 `Text` 및 `ShowReset` 속성과 함께 <xref:System.Windows.Controls.UserControl>에서 상속된 다른 속성이 표시됩니다.`Count` 속성은 읽기 전용이므로 표시되지 않습니다.  
  
5.  `Text` 속성 값을 변경합니다.  
  
     디자이너에 표시되는 레이블 텍스트를 변경해야 합니다.  
  
6.  `ShowReset` 속성을 `Hidden`으로 설정한 다음 다시 `Visible`로 설정합니다.  
  
     컨트롤의 `Reset` 단추가 사라졌다가 다시 나타납니다.  
  
7.  <xref:System.Windows.Controls.Button> 컨트롤을 폼으로 끌고 해당 `Content```특성을 `Test`로 설정한 다음 단추를 두 번 클릭하여 코드 뷰에서 해당 클릭 처리기를 엽니다.  
  
8.  컨트롤의 `Increment` 메서드를 호출하도록 클릭 처리기를 구현합니다.  
  
     [!code-cs[ToolboxControlWPF#21](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_11.cs)]  
  
9. 생성자 함수에서 `InitializeComponent` 호출 후 `counter1.Implemented +=`을 입력한 다음 \<Tab\> 키를 두 번 눌러 `Counter.Incremented` 이벤트에 대한 처리기를 생성합니다.  
  
10. 다음 예제에서처럼 새 처리기를 구현합니다.  
  
     [!code-cs[ToolboxControlWPF#22](../misc/codesnippet/CSharp/walkthrough-creating-a-wpf-toolbox-control_12.cs)]  
  
11. F5 키를 누릅니다.  
  
     WPF 응용 프로그램이 열립니다.  
  
12. **테스트**를 클릭합니다.  
  
     카운터가 증분되고 단추가 약간 페이드됩니다.  
  
13. **테스트**를 4번 더 클릭합니다.  
  
     이 카운터가 증가하고 단추가 사라질 때까지 계속 페이드됩니다. 단추 위치를 계속 클릭하면 카운터가 계속 증가합니다.  
  
14. **다시 설정**을 클릭합니다.  
  
     카운터가 **0**으로 다시 설정됩니다.  
  
## 다음 단계  
 **도구 상자** 컨트롤을 작성할 때 Visual Studio는 프로젝트의 \\bin\\debug\\ 폴더에 *ProjectName*.vsix라는 파일을 만듭니다. 네트워크 또는 웹 사이트에.vsix 파일을 업로드하여 컨트롤을 배포할 수 있습니다. 사용자가 .vsix 파일을 열면 컨트롤이 설치되고 Visual Studio **도구 상자**에 추가됩니다. 또는 사용자가 **확장 관리자**에서 찾아볼 수 있도록 .vsix 파일을 [Visual Studio 갤러리](http://go.microsoft.com/fwlink/?LinkID=123847) 웹 사이트에 업로드할 수도 있습니다.  
  
## 참고 항목  
 [도구 상자 확장](../misc/extending-the-toolbox.md)   
 [Windows Forms 도구 상자 컨트롤 만들기](../extensibility/creating-a-windows-forms-toolbox-control.md)   
 [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)   
 [WPF 디자이너에서 컨트롤 작업](http://msdn.microsoft.com/ko-kr/c6235492-b10d-4c3c-ba67-6b6a545faee1)   
 [컨트롤 제작 개요](../Topic/Control%20Authoring%20Overview.md)
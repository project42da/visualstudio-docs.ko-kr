---
title: "방법: Visual Studio에서 데이터에 WPF 컨트롤 바인딩 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[WPF], 표시"
  - "데이터 바인딩, WPF"
  - "데이터 표시, WPF"
  - "WPF[WPF], 데이터"
  - "WPF 데이터 바인딩[Visual Studio]"
  - "WPF Designer, 데이터 바인딩"
  - "WPF, Visual Studio의 데이터 바인딩"
ms.assetid: 00dd5147-db0b-4b59-8d6c-8229b09ca9dd
caps.latest.revision: 26
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: Visual Studio에서 데이터에 WPF 컨트롤 바인딩
**데이터 소스** 창을 통해 데이터 바인딩된 [!INCLUDE[TLA#tla_titlewinclient](../data-tools/includes/tlasharptla_titlewinclient_md.md)] 컨트롤을 만들 수 있습니다.  먼저 **데이터 소스** 창에 데이터 소스를 추가합니다.  그런 다음 **데이터 소스** 창에서 **WPF 디자이너**로 항목을 끌어 옵니다.  
  
##  <a name="adding"></a> 데이터 소스 창에 데이터 소스 추가  
 데이터 바인딩된 컨트롤을 만들려면 먼저 **데이터 소스** 창에 데이터 소스를 추가해야 합니다.  
  
#### 데이터 소스 창에 데이터 소스를 추가하려면  
  
1.  **뷰** 메뉴에서 **다른 창**을 가리키고 **데이터 소스**를 클릭합니다.  
  
2.  **새 데이터 소스 추가**를 클릭하고 **데이터 소스 구성 마법사**를 완료합니다.  
  
3.  다음 작업 중 하나를 수행하여 데이터 바인딩된 컨트롤을 만듭니다.  
  
    -   [단일 데이터 필드에 바인딩되는 컨트롤 만들기](#simple)  
  
    -   [여러 데이터 필드에 바인딩되는 컨트롤 만들기](#complex)  
  
    -   [여러 데이터 필드에 바인딩되는 컨트롤 집합 만들기](#details)  
  
    -   [디자이너의 기존 컨트롤에 데이터 바인딩](#existing)  
  
##  <a name="simple"></a> 단일 데이터 필드에 바인딩되는 컨트롤 만들기  
 **데이터 소스** 창에 데이터 소스를 추가한 후에는 <xref:System.Windows.Controls.ComboBox> 또는 <xref:System.Windows.Controls.TextBox>와 같은 단일 데이터 필드를 표시하는 새 데이터 바인딩된 컨트롤을 만들 수 있습니다.  
  
#### 단일 데이터 필드에 바인딩되는 컨트롤을 만들려면  
  
1.  **데이터 소스** 창에서 테이블이나 개체를 나타내는 항목을 확장합니다.  바인딩할 열이나 속성을 나타내는 자식 항목을 찾습니다.  시각적 예제를 보려면 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)을 참조하세요.  
  
2.  원하는 경우 만들 컨트롤을 선택합니다.  **데이터 소스** 창의 각 항목에는 디자이너로 항목을 끌어 올 때 만들어지는 기본 컨트롤이 있습니다.  기본 컨트롤은 항목의 기본 데이터 형식에 따라 달라집니다.  
  
     다른 컨트롤을 선택하려면 항목 옆의 드롭다운 화살표를 클릭하고 컨트롤을 선택합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
3.  <xref:System.Windows.Controls.Grid>와 같은 디자이너의 유효한 컨테이너로 항목을 끌어 옵니다.  유효한 컨테이너에 대한 자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하세요.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 새 데이터 바인딩된 컨트롤 및 적절하게 제목이 지정된 <xref:System.Windows.Controls.Label>을 컨테이너에 만듭니다.  또한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]는 컨트롤을 데이터에 바인딩하기 위한 코드와 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]도 생성합니다.  자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
##  <a name="complex"></a> 여러 데이터 필드에 바인딩되는 컨트롤 만들기  
 **데이터 소스** 창에 데이터 소스를 추가한 후에는 <xref:System.Windows.Controls.DataGrid> 또는 <xref:System.Windows.Controls.ListView>와 같은 여러 데이터 필드를 표시하는 새 데이터 바인딩된 컨트롤을 만들 수 있습니다.  
  
#### 여러 데이터 필드에 바인딩되는 컨트롤을 만들려면  
  
1.  **데이터 소스** 창에서 테이블이나 개체를 나타내는 항목을 선택합니다.  시각적 예제를 보려면 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)을 참조하세요.  
  
2.  원하는 경우 만들 컨트롤을 선택합니다.  기본적으로 데이터 테이블이나 개체를 나타내는 **데이터 소스** 창의 각 항목은 <xref:System.Windows.Controls.DataGrid>\(프로젝트가 .NET Framework 4를 대상으로 하는 경우\) 또는 <xref:System.Windows.Controls.ListView>\(이전 .NET Framework 버전의 경우\)를 만들도록 설정됩니다.  
  
     다른 컨트롤을 선택하려면 항목 옆의 드롭다운 화살표를 클릭하고 컨트롤을 선택합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
    > [!NOTE]
    >  특정 열이나 속성을 표시하지 않으려면 항목을 확장하여 해당 자식을 표시합니다.  그런 다음 표시하지 않을 열이나 속성 옆의 드롭다운 화살표를 클릭하고 **없음**을 클릭합니다.  
  
3.  <xref:System.Windows.Controls.Grid>와 같은 디자이너의 유효한 컨테이너로 항목을 끌어 옵니다.  유효한 컨테이너에 대한 자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하세요.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 컨테이너에 새 데이터 바인딩된 컨트롤을 만듭니다. 또한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]는 컨트롤을 데이터에 바인딩하기 위한 코드와 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]도 생성합니다.  자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
##  <a name="details"></a> 여러 데이터 필드에 바인딩되는 컨트롤 집합 만들기  
 **데이터 소스** 창에 데이터 소스를 추가한 후에는 데이터 테이블 또는 개체를 컨트롤 집합에 바인딩할 수 있습니다.  테이블이나 개체의 각 열 또는 속성에 대해 서로 다른 컨트롤이 만들어집니다.  
  
#### 여러 데이터 필드에 바인딩되는 컨트롤 집합을 만들려면  
  
1.  **데이터 소스** 창에서 테이블이나 개체를 나타내는 항목을 선택합니다.  시각적 예제를 보려면 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)을 참조하세요.  
  
2.  항목 옆의 드롭다운 화살표를 클릭하고 **세부 정보**를 선택합니다.  
  
    > [!NOTE]
    >  특정 열이나 속성을 표시하지 않으려면 항목을 확장하여 해당 자식을 표시합니다.  그런 다음 표시하지 않을 열이나 속성 옆의 드롭다운 화살표를 클릭하고 **없음**을 클릭합니다.  
  
3.  <xref:System.Windows.Controls.Grid>와 같은 디자이너의 유효한 컨테이너로 항목을 끌어 옵니다.  유효한 컨테이너에 대한 자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하세요.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 새 데이터 바인딩된 컨트롤을 컨테이너에 만듭니다.  각 컨트롤은 서로 다른 열이나 속성에 바인딩되며, 적절한 제목이 지정된 <xref:System.Windows.Controls.Label> 컨트롤이 함께 제공됩니다. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 데이터에 컨트롤을 바인딩하는 코드와 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]도 생성합니다.  자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
##  <a name="existing"></a> 디자이너의 기존 컨트롤에 데이터 바인딩  
 **데이터 소스** 창에 데이터 소스를 추가한 후에는 디자이너의 기존 컨트롤에 대한 데이터 바인딩을 추가할 수 있습니다.  
  
#### 디자이너의 기존 컨트롤에 데이터를 바인딩하려면  
  
1.  **데이터 소스** 창에서 다음 절차 중 하나를 수행합니다.  
  
    -   <xref:System.Windows.Controls.DataGrid> 또는 <xref:System.Windows.Controls.ListView>와 같이 여러 데이터 필드를 표시하는 기존 컨트롤에 대한 데이터 바인딩을 추가하려면 컨트롤에 바인딩할 테이블이나 개체를 나타내는 항목을 선택합니다.  
  
    -   <xref:System.Windows.Controls.ComboBox> 또는 <xref:System.Windows.Controls.TextBox>와 같이 단일 데이터 필드를 표시하는 기존 컨트롤에 대한 데이터 바인딩을 추가하려면 데이터가 포함된 테이블 또는 개체를 나타내는 항목을 확장한 다음 컨트롤에 바인딩할 데이터를 나타내는 항목을 선택합니다.  
  
2.  선택한 항목을 **데이터 소스** 창에서 디자이너의 기존 컨트롤로 끌어 옵니다.  컨트롤은 유효한 놓기 대상이어야 합니다.  자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]가 컨트롤을 데이터에 바인딩하기 위한 코드와 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)]을 생성합니다.  자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
    > [!NOTE]
    >  컨트롤이 이미 데이터에 바인딩된 경우 컨트롤의 데이터 바인딩이 가장 최근에 컨트롤로 끌어 온 항목으로 다시 설정됩니다.  
  
## 참고 항목  
 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)   
 [방법: WPF 응용 프로그램에서 조회 테이블 만들기](../data-tools/create-lookup-tables-in-wpf-applications.md)   
 [방법: WPF 응용 프로그램에서 관련 데이터 표시](../data-tools/display-related-data-in-wpf-applications.md)   
 [연습: 데이터 집합에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-dataset.md)   
 [연습: WCF 데이터 서비스에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)   
 [연습: WPF 응용 프로그램에서 관련 데이터 표시](../data-tools/walkthrough-displaying-related-data-in-a-wpf-application.md)
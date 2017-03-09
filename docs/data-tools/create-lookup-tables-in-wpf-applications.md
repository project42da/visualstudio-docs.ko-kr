---
title: "방법: WPF 응용 프로그램에서 조회 테이블 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
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
ms.assetid: 56a1fbff-c7e8-4187-a1c1-ffd17024bc1b
caps.latest.revision: 16
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: WPF 응용 프로그램에서 조회 테이블 만들기
**데이터 소스** 창에서 부모 테이블이나 개체의 기본 노드를 관련 자식 테이블의 열이나 속성에 이미 바인딩된 컨트롤로 끌어 조회 테이블을 만들 수 있습니다.  *조회 바인딩*이라고도 하는 *조회 테이블*은 한 데이터 테이블의 정보를 다른 테이블에 있는 외래 키 필드의 값을 기반으로 표시하는 컨트롤을 나타냅니다.  
  
 예를 들어, 판매 데이터베이스에 `Orders` 테이블이 있다고 가정할 경우  `Orders` 테이블의 각 레코드에는 주문한 고객을 나타내는 `CustomerID`가 포함됩니다.  `CustomerID`는 `Customers` 테이블의 고객 레코드를 가리키는 외래 키입니다.  `Orders` 테이블의 주문 목록을 표시할 때 `CustomerID` 대신 실제 고객 이름을 표시할 수 있습니다.  이 경우 고객 이름이 `Customers` 테이블에 있기 때문에 고객 이름을 표시하는 조회 테이블을 만들어야 합니다.  조회 테이블은 `Orders` 레코드의 `CustomerID` 값을 사용하여 관계를 탐색하고 사용자에게 친숙한 고객 이름을 반환합니다.  
  
### 조회 테이블을 만들려면  
  
1.  다음 형식의 데이터 소스 중 하나를 관련 데이터와 함께 프로젝트에 추가합니다.  
  
    -   데이터 집합 또는 엔터티 데이터 모델.  자세한 내용은 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)을 참조하십시오.  
  
    -   WCF 데이터 서비스, WCF 서비스 또는 웹 서비스.  자세한 내용은 [방법: 서비스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-service.md)을 참조하십시오.  
  
    -   개체.  자세한 내용은 [방법: 개체의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20Objects.md)을 참조하십시오.  
  
    > [!NOTE]
    >  조회 테이블을 만들려면 두 개의 관련 테이블이나 개체가 프로젝트의 데이터 소스로 존재해야 합니다.  
  
2.  **WPF Designer**를 열고 **데이터 소스** 창의 항목을 끌어 놓을 수 있는 컨테이너가 있는지 확인합니다.  
  
     유효한 놓기 대상에 대한 자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
3.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭하여 **데이터 소스** 창을 엽니다.  
  
4.  **데이터 소스** 창에서 부모 테이블이나 개체 및 관련 자식 테이블이나 개체가 보일 때까지 노드를 확장합니다.  
  
    > [!NOTE]
    >  관련 자식 테이블이나 개체는 부모 테이블이나 개체의 아래에 확장 가능한 자식 노드로 나타나는 노드입니다.  
  
5.  자식 노드의 드롭다운 메뉴를 클릭하고 **자세히**를 선택합니다.  
  
6.  자식 노드를 확장합니다.  
  
7.  자식 노드 아래에서 자식 데이터와 부모 데이터를 연결하는 항목의 드롭다운 메뉴를 클릭합니다. 위에 나온 예제에서는 이 노드가 **CustomerID** 노드입니다.  조회 바인딩을 지원하는 다음 형식의 컨트롤 중 하나를 선택합니다.  
  
    -   **ComboBox**  
  
    -   **ListBox**  
  
    -   **ListView**  
  
        > [!NOTE]
        >  **ListBox** 또는 **ListView** 컨트롤이 목록에 없으면 이러한 컨트롤을 목록에 추가할 수 있습니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
    -   <xref:System.Windows.Controls.Primitives.Selector>에서 파생되는 사용자 지정 컨트롤  
  
        > [!NOTE]
        >  **데이터 소스** 창에서 항목에 대해 선택할 수 있는 컨트롤의 목록에 사용자 지정 컨트롤을 추가하는 방법에 대한 자세한 내용은 [데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)를 참조하십시오.  
  
8.  **데이터 소스** 창에서 WPF Designer의 컨테이너로 자식 노드를 끕니다. 위에 나온 예제에서는 자식 노드가 **Orders** 노드입니다.  
  
     Visual Studio에서 끌어 오는 각 항목에 대한 새 데이터 바인딩된 컨트롤을 만드는 XAML을 생성합니다.  또한 XAML은 자식 테이블이나 개체의 새 <xref:System.Windows.Data.CollectionViewSource>를 놓기 대상의 리소스에 추가합니다.  일부 데이터 소스의 경우 Visual Studio에서 데이터를 테이블이나 개체에 로드하는 코드도 생성합니다.  자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
9. **데이터 소스** 창에서 부모 노드를 앞에서 만든 조회 바인딩 컨트롤로 끕니다. 위에 나온 예제에서는 부모 노드가 **Customers** 노드입니다.  
  
     Visual Studio에서 조회 바인딩을 구성하는 컨트롤에 대한 몇 가지 속성을 설정합니다.  다음 표에는 Visual Studio에서 수정하는 속성이 나와 있습니다.  필요한 경우 XAML이나 **Properties** 창에서 이러한 속성을 변경할 수 있습니다.  
  
    |Property|설정 설명|  
    |--------------|-----------|  
    |<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>|이 속성은 컨트롤에 표시되는 데이터를 가져오는 데 사용되는 컬렉션이나 바인딩을 지정합니다.  Visual Studio에서는 이 속성을 컨트롤로 끌어 온 부모 데이터의 <xref:System.Windows.Data.CollectionViewSource>로 설정합니다.|  
    |<xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A>|이 속성은 컨트롤에 표시되는 데이터 항목의 경로를 지정합니다.  Visual Studio에서는 이 속성을 데이터 형식이 문자열인 부모 데이터에서 기본 키 다음에 오는 첫 번째 열이나 속성으로 설정합니다.<br /><br /> 부모 데이터에 있는 다른 열이나 속성을 표시하려면 이 속성을 다른 속성의 경로로 변경합니다.|  
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>|Visual Studio에서 디자이너로 끌어 온 자식 데이터의 열이나 속성에 이 속성을 바인딩합니다.  이 자식 데이터는 부모 데이터의 외래 키입니다.|  
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValuePath%2A>|Visual Studio에서 이 속성을 부모 데이터의 외래 키인 자식 데이터의 열이나 속성에 대한 경로로 설정합니다.|  
  
## 참고 항목  
 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)   
 [방법: Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)   
 [방법: WPF 응용 프로그램에서 관련 데이터 표시](../data-tools/display-related-data-in-wpf-applications.md)   
 [연습: WPF 응용 프로그램에서 관련 데이터 표시](../data-tools/walkthrough-displaying-related-data-in-a-wpf-application.md)
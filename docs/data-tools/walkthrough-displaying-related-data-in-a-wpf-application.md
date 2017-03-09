---
title: "연습: WPF 응용 프로그램에서 관련 데이터 표시 | Microsoft Docs"
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
  - "WPF 데이터 바인딩[Visual Studio], 연습"
  - "WPF Designer, 데이터 바인딩"
  - "WPF, Visual Studio의 데이터 바인딩"
ms.assetid: 5c48f188-e9c4-40a6-97d9-67cdb2f90127
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 연습: WPF 응용 프로그램에서 관련 데이터 표시
이 연습에서는 부모\/자식 관계가 있는 데이터베이스 테이블의 데이터를 표시하는 WPF 응용 프로그램을 만듭니다.  데이터는 엔터티 데이터 모델의 엔터티에 캡슐화되고  부모 엔터티는 주문 집합에 대한 개요 정보를 제공합니다.  이 엔터티의 각 속성은 응용 프로그램의 다른 컨트롤에 바인딩되고  자식 엔터티는 각 주문에 대한 자세한 정보를 제공합니다.  이 데이터 집합은 <xref:System.Windows.Controls.DataGrid> 컨트롤에 바인딩됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   AdventureWorksLT 샘플 데이터베이스의 데이터에서 생성되는 엔터티 데이터 모델과 WPF 응용 프로그램 만들기  
  
-   주문 집합에 대한 개요 정보를 표시하는 데이터 바인딩된 컨트롤 집합 만들기.  이 컨트롤을 만들려면 **데이터 소스** 창에서 **WPF Designer**로 부모 엔터티를 끕니다.  
  
-   선택된 각 주문과 관련된 자세한 정보를 표시하는 <xref:System.Windows.Controls.DataGrid> 컨트롤 만들기.  이 컨트롤을 만들려면 **데이터 소스** 창에서 **WPF Designer**의 창으로 자식 엔터티를 끕니다.  
  
     [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
-   AdventureWorksLT 샘플 데이터베이스가 연결되어 있는 SQL Server 또는 SQL Server Express의 실행 중인 인스턴스에 액세스.  AdventureWorksLT 데이터베이스는 [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)에서 다운로드할 수 있습니다.  
  
 연습을 완료하려면 다음 개념에 대한 사전 지식이 유용하지만 반드시 필요하지는 않습니다.  
  
-   엔터티 데이터 모델 및 ADO.NET Entity Framework.  자세한 내용은 [Entity Framework 개요](../Topic/Entity%20Framework%20Overview.md)를 참조하십시오.  
  
-   WPF Designer 작업.  자세한 내용은 [WPF 및 Silverlight 디자이너 개요](http://msdn.microsoft.com/ko-kr/570b7a5c-0c86-4326-a371-c9b63378fc62)를 참조하십시오.  
  
-   WPF 데이터 바인딩.  자세한 내용은 [데이터 바인딩 개요](../Topic/Data%20Binding%20Overview.md)를 참조하십시오.  
  
## 프로젝트 만들기  
 주문 레코드를 표시하는 새 WPF 프로젝트를 만듭니다.  
  
#### 새 WPF 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  **Visual C\#**이나 **Visual Basic**을 확장한 다음 **Windows**를 선택합니다.  
  
4.  대화 상자 맨 위의 콤보 상자에서 **.NET Framework 4**가 선택되어 있는지 확인합니다.  이 연습에 사용되는 <xref:System.Windows.Controls.DataGrid> 컨트롤은 .NET Framework 4에서만 사용할 수 있습니다.  
  
5.  **WPF 응용 프로그램** 프로젝트 템플릿을 선택합니다.  
  
6.  **이름** 상자에 `AdventureWorksOrdersViewer`를 입력합니다.  
  
7.  **확인**을 클릭합니다.  
  
     `AdventureWorksOrdersViewer` 프로젝트가 만들어집니다.  
  
## 응용 프로그램의 엔터티 데이터 모델 만들기  
 데이터 바인딩된 컨트롤을 만들려면 먼저 응용 프로그램의 데이터 모델을 정의하여 **데이터 소스** 창에 추가해야 합니다.  이 연습에서는 데이터 모델이 엔터티 데이터 모델입니다.  
  
#### 엔터티 데이터 모델을 만들려면  
  
1.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭하여 **데이터 소스 구성 마법사**를 엽니다.  
  
2.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 클릭하고 **다음**을 클릭합니다.  
  
3.  **데이터베이스 모델 선택** 페이지에서 **엔터티 데이터 모델**을 클릭하고 **다음**을 클릭합니다.  
  
4.  **모델 콘텐츠 선택** 페이지에서 **데이터베이스에서 생성**을 클릭하고 **다음**을 클릭합니다.  
  
5.  **데이터 연결 선택** 페이지에서 다음 중 하나를 수행합니다.  
  
    -   AdventureWorksLT 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   **새 연결**을 클릭하고 AdventureWorksLT 데이터베이스에 대한 연결을 만듭니다.  
  
     **App.Config의 엔터티 연결 설정을 다음으로 저장** 옵션이 선택되어 있는지 확인하고 **다음**을 클릭합니다.  
  
6.  **데이터베이스 개체 선택** 페이지에서 **테이블**을 확장하고 다음 테이블을 선택합니다.  
  
    -   **SalesOrderDetail**  
  
    -   **SalesOrderHeader**  
  
7.  **마침**을 클릭합니다.  
  
8.  프로젝트를 빌드합니다.  
  
## 주문을 표시하는 데이터 바인딩된 컨트롤 만들기  
 **데이터 소스** 창에서 WPF Designer로 `SalesOrderHeaders` 엔터티를 끌어 주문 레코드를 표시하는 컨트롤을 만듭니다  
  
#### 주문 레코드를 표시하는 데이터 바인딩된 컨트롤을 만들려면  
  
1.  **솔루션 탐색기**에서 MainWindow.xaml을 두 번 클릭합니다.  
  
     WPF Designer에서 창이 열립니다.  
  
2.  XAML을 편집하여 **Height** 및 **Width** 속성을 800으로 설정합니다.  
  
3.  **데이터 소스** 창에서 **SalesOrderHeaders** 노드의 드롭다운 메뉴를 클릭하고 **자세히**를 선택합니다.  
  
4.  **SalesOrderHeaders** 노드를 확장합니다.  
  
5.  **SalesOrderID** 옆의 드롭다운 메뉴를 클릭하고 **ComboBox**를 선택합니다.  
  
6.  **SalesOrderHeaders** 노드에 있는 다음의 각 자식 노드에 대해 해당 노드 옆의 드롭다운 메뉴를 클릭하고 **없음**을 선택합니다.  
  
    -   **RevisionNumber**  
  
    -   **OnlineOrderFlag**  
  
    -   **ShipToAddressID**  
  
    -   **BillToAddressID**  
  
    -   **CreditCardApprovalCode**  
  
    -   **SubTotal**  
  
    -   **TaxAmt**  
  
    -   **Freight**  
  
    -   **rowguid**  
  
    -   **ModifiedDate**  
  
     이 동작은 Visual Studio가 다음 단계에서 이러한 노드의 데이터 바인딩된 컨트롤을 만들지 못하게 합니다.  이 연습에서는 최종 사용자가 이 데이터를 볼 필요가 없다고 가정합니다.  
  
7.  **데이터 소스** 창에서 **WPF Designer**의 창으로 **SalesOrderHeaders** 노드를 끕니다.  
  
     **SalesOrderHeaders** 엔터티의 데이터에 바인딩된 컨트롤 집합을 만드는 XAML과 데이터를 로드하는 코드가 생성됩니다.  생성된 XAML 및 코드에 대한 자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하십시오.  
  
8.  디자이너에서 **판매 주문 ID** 레이블 옆의 콤보 상자를 클릭합니다.  
  
9. **속성** 창에서 **IsReadOnly** 속성 옆의 확인란을 선택합니다.  
  
## 자세한 주문 정보를 표시하는 DataGrid 만들기  
 **데이터 소스** 창에서 WPF Designer로 `SalesOrderDetails` 엔터티를 끌어 자세한 주문 정보를 표시하는 <xref:System.Windows.Controls.DataGrid> 컨트롤을 만듭니다.  
  
#### 자세한 주문 정보를 표시하는 DataGrid를 만들려면  
  
1.  **데이터 소스** 창에서 **SalesOrderHeaders** 노드의 자식인 **SalesOrderDetails** 노드를 찾습니다.  
  
    > [!NOTE]
    >  **SalesOrderHeaders** 노드의 피어인 **SalesOrderDetails** 노드도 있으므로  **SalesOrderHeaders** 노드의 자식 노드를 선택했는지 확인하십시오.  
  
2.  자식 **SalesOrderDetails** 노드를 확장합니다.  
  
3.  **SalesOrderDetails** 노드에 있는 다음의 각 자식 노드에 대해 해당 노드 옆의 드롭다운 메뉴를 클릭하고 **없음**을 선택합니다.  
  
    -   **SalesOrderID**  
  
    -   **SalesOrderDetailID**  
  
    -   **rowguid**  
  
    -   **ModifiedDate**  
  
     이 동작은 Visual Studio가 다음 단계에서 만드는 <xref:System.Windows.Controls.DataGrid> 컨트롤에 이 데이터를 포함하지 못하게 합니다.  이 연습에서는 최종 사용자가 이 데이터를 볼 필요가 없다고 가정합니다.  
  
4.  **데이터 소스** 창에서 **WPF Designer**의 창으로 자식 **SalesOrderDetails** 노드를 끕니다.  
  
     새 데이터 바인딩된 <xref:System.Windows.Controls.DataGrid> 컨트롤을 정의하는 XAML이 생성되고 디자이너에 이 컨트롤이 나타납니다.  또한 **SalesOrderDetails** 엔터티의 데이터를 포함하도록 코드 숨김 파일에서 생성된 `GetSalesOrderHeadersQuery` 메서드가 업데이트됩니다.  
  
## 응용 프로그램 테스트  
 응용 프로그램을 빌드하고 실행하여 응용 프로그램에서 주문 레코드를 표시하는지 확인합니다.  
  
#### 응용 프로그램을 테스트하려면  
  
1.  **F5** 키를 누릅니다.  
  
     응용 프로그램이 빌드되고 실행됩니다.  다음을 확인합니다.  
  
    -   **판매 주문 ID** 콤보 상자에 **71774**가 표시됩니다.  이는 엔터티의 첫 주문 ID입니다.  
  
    -   **판매 주문 ID** 콤보 상자에서 선택한 각 주문에 대한 자세한 주문 정보가 <xref:System.Windows.Controls.DataGrid>에 표시됩니다.  
  
2.  응용 프로그램을 닫습니다.  
  
## 다음 단계  
 이 연습을 마치고 나면 Visual Studio에서 **데이터 소스** 창을 사용하여 WPF 컨트롤을 다른 형식의 데이터 소스에 바인딩하는 방법을 배웁니다.  자세한 내용은 [연습: WCF 데이터 서비스에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md) 및 [연습: 데이터 집합에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-dataset.md)을 참조하십시오.  
  
## 참고 항목  
 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)   
 [방법: WPF 응용 프로그램에서 관련 데이터 표시](../data-tools/display-related-data-in-wpf-applications.md)
---
title: "연습: 데이터 집합에 WPF 컨트롤 바인딩 | Microsoft Docs"
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
ms.assetid: 177420b9-568b-4dad-9d16-1b0e98a24d71
caps.latest.revision: 32
caps.handback.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 데이터 집합에 WPF 컨트롤 바인딩
이 연습에서는 데이터 바인딩된 컨트롤을 포함하는 WPF 응용 프로그램을 만듭니다.  이러한 컨트롤은 데이터 집합에서 캡슐화된 제품 레코드에 바인딩됩니다.  또한 제품을 찾아보고 제품 레코드 변경 내용을 저장할 수 있는 단추도 추가합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   AdventureWorksLT 샘플 데이터베이스의 데이터에서 생성되는 데이터 집합 및 WPF 응용 프로그램을 만듭니다.  
  
-   **데이터 소스** 창에서 WPF 디자이너의 창으로 데이터 테이블을 끌어 데이터 바인딩된 컨트롤 집합을 만듭니다.  
  
-   제품 레코드를 앞뒤로 탐색하는 데 사용할 단추를 만듭니다.  
  
-   사용자가 제품 레코드에 대해 적용한 변경 내용을 데이터 테이블 및 기본 데이터 소스에 저장하는 단추를 만듭니다.  
  
     [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
  
-   AdventureWorksLT 샘플 데이터베이스가 연결된 SQL Server 또는 SQL Server Express의 실행 중인 인스턴스 액세스 권한.  AdventureWorksLT 데이터베이스는 [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)에서 다운로드할 수 있습니다.  
  
 또한 다음 개념에 대한 지식은 연습을 완료하는 데 반드시 필요하지는 않지만 사전에 파악해 두면 유용할 수 있습니다.  
  
-   데이터 집합 및 TableAdapter.  자세한 내용은 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md) 및 [TableAdapter 개요](../data-tools/tableadapter-overview.md)를 참조하십시오.  
  
-   WPF 디자이너 사용법.  자세한 내용은 [WPF 및 Silverlight 디자이너 개요](http://msdn.microsoft.com/ko-kr/570b7a5c-0c86-4326-a371-c9b63378fc62)을 참조하십시오.  
  
-   WPF 데이터 바인딩.  자세한 내용은 [데이터 바인딩 개요](../Topic/Data%20Binding%20Overview.md)을 참조하십시오.  
  
## 프로젝트 만들기  
 새 WPF 프로젝트를 만듭니다.  이 프로젝트에 제품 레코드가 표시됩니다.  
  
#### 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  **Visual Basic** 또는 **Visual C\#**을 확장한 다음 **Windows**를 선택합니다.  
  
4.  **WPF 응용 프로그램** 프로젝트 템플릿을 선택합니다.  
  
5.  **이름** 상자에 `AdventureWorksProductsEditor`를 입력한 다음 **확인**을 클릭합니다.  
  
     `AdventureWorksProductsEditor` 프로젝트가 만들어집니다.  
  
## 응용 프로그램용 데이터 집합 만들기  
 데이터 바인딩된 컨트롤을 만들려면 응용 프로그램의 데이터 모델을 정의한 다음 **데이터 소스** 창에 추가해야 합니다.  이 연습에서는 데이터 모델로 사용할 데이터 집합을 만듭니다.  
  
#### 데이터 집합을 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
     **데이터 소스** 창이 열립니다.  
  
2.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.  
  
     **데이터 소스 구성 마법사**가 열립니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  **데이터베이스 모델 선택** 페이지에서 **데이터 집합**을 선택하고 **다음**을 클릭합니다.  
  
5.  **데이터 연결 선택** 페이지에서 다음 옵션 중 하나를 선택합니다.  
  
    -   AdventureWorksLT 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택하고 **다음**을 클릭합니다.  
  
         또는  
  
    -   **새 연결**을 클릭하고 AdventureWorksLT 데이터베이스에 대한 연결을 만듭니다.  
  
6.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **예, 다음으로 연결을 저장합니다.** 확인란을 선택하고 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체 선택** 페이지에서 **테이블**을 확장하고 **Product\(SalesLT\)** 테이블을 선택합니다.  
  
8.  **마침**을 클릭합니다.  
  
     새 AdventureWorksLTDataSet.xsd 파일이 프로젝트에 추가되고 해당하는 **AdventureWorksLTDataSet** 항목이 **데이터 소스** 창에 추가됩니다.  AdventureWorksLTDataSet.xsd 파일은 `AdventureWorksLTDataSet`라는 형식화된 데이터 집합과 `ProductTableAdapter`라는 TableAdapter를 정의합니다.  이 연습 뒷부분에서 `ProductTableAdapter`를 사용하여 데이터 집합에 데이터를 채우고 변경 내용을 데이터베이스에 다시 저장합니다.  
  
9. 프로젝트를 빌드합니다.  
  
## TableAdapter의 기본 Fill 메서드 편집  
 데이터 집합을 데이터로 채우려면 `ProductTableAdapter`의 `Fill` 메서드를 사용합니다.  기본적으로 `Fill` 메서드는 Product 테이블의 모든 데이터 행을 `AdventureWorksLTDataSet`의 `ProductDataTable`에 채웁니다.  이 메서드가 행 하위 집합만 반환하도록 수정할 수 있습니다.  이 연습에서는 사진이 있는 제품의 행만 반환하도록 `Fill` 메서드를 수정합니다.  
  
#### 사진이 있는 제품 행을 로드하려면  
  
1.  **솔루션 탐색기**에서 AdventureWorksLTDataSet.xsd 파일을 두 번 클릭합니다.  
  
     데이터 집합 디자이너가 열립니다.  
  
2.  디자이너에서 **Fill,GetData\(\)** 쿼리를 마우스 오른쪽 단추로 클릭하고 **구성**을 선택합니다.  
  
     **TableAdapter 구성 마법사**가 열립니다.  
  
3.  **SQL 문을 입력하십시오.** 페이지의 텍스트 상자에서 `SELECT` 문 뒤에 다음 WHERE 절을 추가합니다.  
  
    ```  
    WHERE ThumbnailPhotoFileName <> 'no_image_available_small.gif'  
    ```  
  
4.  **마침**을 클릭합니다.  
  
## 사용자 인터페이스 정의  
 WPF 디자이너에서 XAML을 수정하여 창에 여러 단추를 추가합니다.  이 연습 뒷부분에서 사용자가 이러한 단추를 사용해 제품 레코드를 스크롤하고 변경 내용을 저장할 수 있도록 하는 코드를 추가합니다.  
  
#### 창의 사용자 인터페이스를 정의하려면  
  
1.  **솔루션 탐색기**에서 MainWindow.xaml을 두 번 클릭합니다.  
  
     WPF 디자이너에서 창이 열립니다.  
  
2.  디자이너의 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] 뷰에서 `<Grid>` 태그 사이에 다음 코드를 추가합니다.  
  
    ```  
    <Grid.RowDefinitions>  
        <RowDefinition Height="75" />  
        <RowDefinition Height="625" />  
    </Grid.RowDefinitions>  
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>  
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>  
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>  
    ```  
  
3.  프로젝트를 빌드합니다.  
  
## 데이터 바인딩된 컨트롤 만들기  
 **데이터 소스** 창에서 WPF 디자이너로 `Product` 테이블을 끌어 고객 레코드를 표시하는 컨트롤을 만듭니다.  
  
#### 데이터 바인딩된 컨트롤을 만들려면  
  
1.  **데이터 소스** 창에서 **Product** 노드의 드롭다운 메뉴를 클릭하고 **정보**를 선택합니다.  
  
2.  **Product** 노드를 확장합니다.  
  
3.  이 예에서는 일부 필드를 표시하지 않을 것이므로 다음 노드 옆의 드롭다운 메뉴를 클릭하고 **없음**을 선택합니다.  
  
    -   ProductCategoryID  
  
    -   ProductModelID  
  
    -   ThumbnailPhotoFileName  
  
    -   rowguid  
  
    -   ModifiedDate  
  
4.  **ThumbNailPhoto** 노드 옆의 드롭다운 메뉴를 클릭하고 **이미지**를 선택합니다.  
  
    > [!NOTE]
    >  기본적으로 **데이터 소스** 창에서 사진을 나타내는 항목의 기본 컨트롤은 **없음**으로 설정되어 있습니다.  사진은 데이터베이스에서 바이트 배열로 저장되는데 바이트 배열은 단순한 바이트의 배열에서 대형 응용 프로그램의 실행 파일에 이르기까지 모든 항목을 포함할 수 있기 때문입니다.  
  
5.  **데이터 소스** 창에서 단추가 포함된 행 아래의 데이터 표 행으로 **Product** 노드를 끌어 옵니다.  
  
     **Product** 테이블의 데이터에 바인딩되는 컨트롤 집합을 정의하는 XAML이 생성됩니다.  또한 데이터를 로드하는 코드도 생성됩니다.  생성된 XAML 및 코드에 대한 자세한 내용은 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)을 참조하세요.  
  
6.  디자이너에서 **제품 ID** 레이블 옆의 텍스트 상자를 클릭합니다.  
  
7.  **속성** 창에서 **IsReadOnly** 속성 옆의 확인란을 선택합니다.  
  
## 제품 레코드 탐색  
 사용자가 **\<** 및 **\>** 단추를 사용하여 제품 레코드를 스크롤할 수 있도록 하는 코드를 추가합니다.  
  
#### 사용자가 제품 레코드를 탐색할 수 있도록 설정하려면  
  
1.  디자이너의 창 화면에서 **\<** 단추를 두 번 클릭합니다.  
  
     코드 숨김 파일이 열리고 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대해 새 `backButton_Click` 이벤트 처리기가 만들어집니다.  
  
2.  `ProductViewSource`, `AdventureWorksLTDataSet` 및 `AdventureWorksLTDataSetProductTableAdapter`가 메서드 외부에 있으며 전체 폼에서 액세스할 수 있는 상태가 되도록 `Window_Loaded` 이벤트 처리기를 수정합니다.  다음 코드와 같이 이러한 전역 항목만 폼에 대해 선언하고 `Window_Loaded` 이벤트 내에서 할당합니다.  
  
     [!code-cs[Data_WPFDATASET#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_1.cs)]
     [!code-vb[Data_WPFDATASET#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_1.vb)]  
  
3.  다음 코드를 `backButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-cs[Data_WPFDATASET#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_2.cs)]
     [!code-vb[Data_WPFDATASET#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_2.vb)]  
  
4.  디자이너로 돌아온 다음 **\>** 단추를 두 번 클릭합니다.  
  
5.  다음 코드를 `nextButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-cs[Data_WPFDATASET#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_3.cs)]
     [!code-vb[Data_WPFDATASET#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_3.vb)]  
  
## 제품 레코드 변경 내용 저장  
 사용자가 **변경 내용 저장** 단추를 사용하여 제품 레코드 변경 내용을 저장할 수 있도록 하는 코드를 추가합니다.  
  
#### 제품 레코드 변경 내용을 저장하는 기능을 추가하려면  
  
1.  디자이너에서 **변경 내용 저장** 단추를 두 번 클릭합니다.  
  
     코드 숨김 파일이 열리고 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대해 새 `saveButton_Click` 이벤트 처리기가 만들어집니다.  
  
2.  다음 코드를 `saveButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-cs[Data_WPFDATASET#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_4.cs)]
     [!code-vb[Data_WPFDATASET#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_4.vb)]  
  
    > [!NOTE]
    >  이 예에서는 `TableAdapter`의 `Save` 메서드를 사용하여 변경 내용을 저장합니다.  이 연습에서는 데이터 테이블을 하나만 변경하므로 이러한 방식이 적절합니다.  여러 데이터 테이블의 변경 내용을 저장해야 하는 경우에는 데이터 집합과 함께 생성되는 `TableAdapterManager`의 `UpdateAll` 메서드를 사용할 수 있습니다.  자세한 내용은 [TableAdapterManager 개요](../Topic/TableAdapterManager%20Overview.md)을 참조하십시오.  
  
## 응용 프로그램 테스트  
 응용 프로그램을 빌드 및 실행합니다.  제품 레코드를 보고 업데이트할 수 있는지 확인합니다.  
  
#### 응용 프로그램을 테스트하려면  
  
1.  **F5** 키를 누릅니다.  
  
     응용 프로그램이 빌드되고 실행됩니다.  다음 사항을 확인합니다.  
  
    -   텍스트 상자에 사진이 포함된 첫 번째 제품 레코드의 데이터가 표시됩니다.  이 제품의 ID는 713이고 이름은 **Long\-Sleeve Logo Jersey, S**입니다.  
  
    -   **\>** 또는 **\<** 단추를 클릭하여 다른 제품 레코드를 탐색할 수 있습니다.  
  
2.  제품 레코드 중 하나의 **크기** 값을 변경하고 **변경 내용 저장**을 클릭합니다.  
  
3.  응용 프로그램을 닫았다가 Visual Studio에서 **F5** 키를 눌러 다시 시작합니다.  
  
4.  변경한 제품 레코드로 이동하여 변경 내용이 유지되었는지를 확인합니다.  
  
5.  응용 프로그램을 닫습니다.  
  
## 다음 단계  
 이 연습을 완료하고 나면 다음과 같은 관련 작업을 수행할 수 있습니다.  
  
-   Visual Studio에서 **데이터 소스** 창을 사용하여 WPF 컨트롤을 다른 형식의 데이터 소스에 바인딩합니다.  자세한 내용은 [연습: WCF 데이터 서비스에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)을 참조하십시오.  
  
-   Visual Studio에서 **데이터 소스** 창을 사용하여 관련 데이터, 즉 부모\-자식 관계가 적용된 데이터를 WPF 컨트롤에 표시합니다.  자세한 내용은 [연습: WPF 응용 프로그램에서 관련 데이터 표시](../data-tools/walkthrough-displaying-related-data-in-a-wpf-application.md)을 참조하십시오.  
  
## 참고 항목  
 [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio1.md)   
 [방법: Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio2.md)   
 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)   
 [WPF 및 Silverlight 디자이너 개요](http://msdn.microsoft.com/ko-kr/570b7a5c-0c86-4326-a371-c9b63378fc62)   
 [데이터 바인딩 개요](../Topic/Data%20Binding%20Overview.md)
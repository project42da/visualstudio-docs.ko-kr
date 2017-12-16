---
title: "데이터 집합에 WPF 컨트롤 바인딩 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio], walkthroughs
- WPF Designer, data binding
ms.assetid: 177420b9-568b-4dad-9d16-1b0e98a24d71
caps.latest.revision: "32"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 96d5407672ff94749731f9d00088b27e8c4da036
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="bind-wpf-controls-to-a-dataset"></a>데이터 집합에 WPF 컨트롤 바인딩
이 연습에서는 데이터 바인딩된 컨트롤을 포함하는 WPF 응용 프로그램을 만듭니다. 이러한 컨트롤은 데이터 집합에서 캡슐화된 제품 레코드에 바인딩됩니다. 또한 제품을 찾아보고 제품 레코드 변경 내용을 저장할 수 있는 단추도 추가합니다.  
  
이 연습에서는 다음 작업을 수행합니다.  
  
- AdventureWorksLT 샘플 데이터베이스의 데이터에서 생성되는 데이터 집합 및 WPF 응용 프로그램을 만듭니다.  
  
- 데이터 테이블을 끌어 데이터 바인딩된 컨트롤의 집합을 만들기는 **데이터 소스** 창 WPF 디자이너의 창.  
  
- 제품 레코드를 앞뒤로 탐색하는 데 사용할 단추를 만듭니다.  
  
- 사용자가 제품 레코드에 대해 적용한 변경 내용을 데이터 테이블 및 기본 데이터 소스에 저장하는 단추를 만듭니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
  
-   AdventureWorksLT 샘플 데이터베이스가 연결된 SQL Server 또는 SQL Server Express의 실행 중인 인스턴스 액세스 권한. AdventureWorksLT 데이터베이스를 다운로드할 수 있습니다는 [CodePlex 웹 사이트](http://go.microsoft.com/fwlink/?linkid=87843)합니다.  
  
또한 다음 개념에 대한 지식은 연습을 완료하는 데 반드시 필요하지는 않지만 사전에 파악해 두면 유용할 수 있습니다.  
  
-   데이터 집합 및 TableAdapter. 자세한 내용은 참조 [Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md) 및 [TableAdapter](../data-tools/create-and-configure-tableadapters.md)합니다.  
  
-   WPF 데이터 바인딩. 자세한 내용은 [데이터 바인딩 개요](/dotnet/framework/wpf/data/data-binding-overview)를 참조하세요.  
  
## <a name="create-the-project"></a>프로젝트를 만듭니다.  
 새 WPF 프로젝트를 만듭니다. 이 프로젝트에 제품 레코드가 표시됩니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  **파일** 메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭합니다.  
  
3.  확장 **Visual Basic** 또는 **Visual C#**를 선택한 후 **Windows**합니다.  
  
4.  선택 된 **WPF 응용 프로그램** 서식 파일 프로젝트.  
  
5.  에 **이름** 상자에 입력 합니다 `AdventureWorksProductsEditor` 클릭 **확인**합니다.  
  
     Visual Studio 만듭니다는 `AdventureWorksProductsEditor` 프로젝트.  
  
## <a name="create-a-dataset-for-the-application"></a>응용 프로그램에 대 한 데이터 집합 만들기  
 응용 프로그램에 대 한 데이터 모델을 정의 하 고에 추가 해야 데이터 바인딩된 컨트롤을 만들 수 있습니다, 전에 **데이터 소스** 창. 이 연습에서는 데이터 모델로 사용할 데이터 집합을 만듭니다.  
  
#### <a name="to-create-a-dataset"></a>데이터 집합을 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
     **데이터 소스** 창이 열립니다.  
  
2.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.  
  
     **데이터 소스 구성** 마법사가 열립니다.  
  
3.  에 **데이터 소스 형식 선택** 페이지에서 **데이터베이스**, 클릭 하 고 **다음**합니다.  
  
4.  에 **데이터베이스 모델 선택** 페이지에서 **Dataset**, 클릭 하 고 **다음**합니다.  
  
5.  에 **데이터 연결 선택** 페이지에서 다음 옵션 중 하나를 선택 합니다.  
  
    -   AdventureWorksLT 샘플 데이터베이스에 데이터 연결이 드롭다운 목록에서 사용할 수 있으면 선택 하 고 클릭 **다음**합니다.  
  
    -   클릭 **새 연결**, AdventureWorksLT 데이터베이스에 연결을 만듭니다.  
  
6.  에 **응용 프로그램 구성 파일에 연결 문자열 저장** 선택 페이지는 **예,으로 연결을 저장** 확인란을 선택한 다음 클릭 **다음**합니다.  
  
7.  에 **데이터베이스 개체 선택** 페이지에서 **테이블**를 선택한 후는 **Product (SalesLT)** 테이블입니다.  
  
8.  **마침**을 클릭합니다.  
  
     Visual Studio를 새로 추가 `AdventureWorksLTDataSet.xsd` 해당 파일을 프로젝트에 추가 **AdventureWorksLTDataSet** 항목의 **데이터 소스** 창. `AdventureWorksLTDataSet.xsd` 파일 라는 형식화 된 데이터 집합 정의 `AdventureWorksLTDataSet` 및 라는 TableAdapter `ProductTableAdapter`합니다. 이 연습 뒷부분에서 `ProductTableAdapter`를 사용하여 데이터 집합에 데이터를 채우고 변경 내용을 데이터베이스에 다시 저장합니다.  
  
9. 프로젝트를 빌드합니다.  
  
## <a name="edit-the-default-fill-method-of-the-tableadapter"></a>TableAdapter의 기본 fill 메서드 편집  
 데이터 집합을 데이터로 채우려면 `Fill`의 `ProductTableAdapter` 메서드를 사용합니다. 기본적으로 `Fill` 메서드는 Product 테이블의 모든 데이터 행을 `ProductDataTable`의 `AdventureWorksLTDataSet`에 채웁니다. 이 메서드가 행 하위 집합만 반환하도록 수정할 수 있습니다. 이 연습에서는 사진이 있는 제품의 행만 반환하도록 `Fill` 메서드를 수정합니다.  
  
#### <a name="to-load-product-rows-that-have-photos"></a>사진이 있는 제품 행을 로드하려면  
  
1.  **솔루션 탐색기**, 두 번 클릭 하 고 `AdventureWorksLTDataSet.xsd` 파일.  
  
     데이터 집합 디자이너가 열립니다.  
  
2.  디자이너에서 마우스 오른쪽 단추로 클릭는 **getdata ()를 채우지** 쿼리하고 선택 **구성**합니다.  
  
     **TableAdapter 구성** 마법사가 열립니다.  
  
3.  에 **SQL 문을 입력** 페이지 뒤에 다음 WHERE 절을 추가 합니다는 `SELECT` 텍스트 상자에 문의 합니다.  
  
    ```  
    WHERE ThumbnailPhotoFileName <> 'no_image_available_small.gif'  
    ```  
  
4.  **마침**을 클릭합니다.  
  
## <a name="define-the-user-interface"></a>사용자 인터페이스를 정의 합니다.  
 WPF 디자이너에서 XAML을 수정하여 창에 여러 단추를 추가합니다. 이 연습 뒷부분에서 사용자가 이러한 단추를 사용해 제품 레코드를 스크롤하고 변경 내용을 저장할 수 있도록 하는 코드를 추가합니다.  
  
#### <a name="to-define-the-user-interface-of-the-window"></a>창의 사용자 인터페이스를 정의하려면  
  
1.  **솔루션 탐색기**, MainWindow.xaml을 두 번 클릭 합니다.  
  
     WPF 디자이너에서 창이 열립니다.  
  
2.  디자이너의 [!INCLUDE[TLA#tla_titlexaml](../data-tools/includes/tlasharptla_titlexaml_md.md)] 뷰에서 `<Grid>` 태그 사이에 다음 코드를 추가합니다.  
  
    ```xaml  
    <Grid.RowDefinitions>  
        <RowDefinition Height="75" />  
        <RowDefinition Height="625" />  
    </Grid.RowDefinitions>  
    <Button HorizontalAlignment="Left" Margin="22,20,0,24" Name="backButton" Width="75"><</Button>  
    <Button HorizontalAlignment="Left" Margin="116,20,0,24" Name="nextButton" Width="75">></Button>  
    <Button HorizontalAlignment="Right" Margin="0,21,46,24" Name="saveButton" Width="110">Save changes</Button>  
    ```  
  
3.  프로젝트를 빌드합니다.  
  
## <a name="create-data-bound-controls"></a>데이터 바인딩된 컨트롤 만들기  
 끌어 고객 레코드를 표시 하는 컨트롤 만들기는 `Product` 에서 테이블의 **데이터 소스** 창에서 WPF 디자이너로 합니다.  
  
#### <a name="to-create-data-bound-controls"></a>데이터 바인딩된 컨트롤을 만들려면  
  
1.  에 **데이터 원본** 창에 대 한 드롭다운 메뉴를 클릭는 **제품** 노드 선택한 **세부 정보**합니다.  
  
2.  확장 된 **제품** 노드.  
  
3.  이 예제에서는 일부 필드 표시 되지 것입니다., 이므로 다음 노드 옆의 드롭다운 메뉴를 클릭 및 선택 **None**:  
  
    -   ProductCategoryID  
  
    -   ProductModelID  
  
    -   ThumbnailPhotoFileName  
  
    -   rowguid  
  
    -   ModifiedDate  
  
4.  옆의 드롭다운 메뉴를 클릭는 **ThumbNailPhoto** 노드 선택한 **이미지**합니다.  
  
    > [!NOTE]
    >  기본적으로 항목에 **데이터 원본** 사진을 나타내는 창의 기본 컨트롤을 설정 하는 필요한 **None**합니다. 사진은 데이터베이스에서 바이트 배열로 저장되는데 바이트 배열은 단순한 바이트의 배열에서 대형 응용 프로그램의 실행 파일에 이르기까지 모든 항목을 포함할 수 있기 때문입니다.  
  
5.  **데이터 원본** 끌어 창에서 **제품** 단추가 포함 된 행 아래의 표 행으로 노드.  
  
     Visual Studio에서 데이터에 바인딩되는 컨트롤의 집합을 정의 하는 XAML이 생성 된 **제품** 테이블입니다. 또한 데이터를 로드하는 코드도 생성됩니다. 생성 된 XAML 및 코드에 대 한 자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤을 바인딩하는 WPF](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)합니다.  
  
6.  디자이너에서 클릭 하 여 텍스트 상자 옆에 **제품 ID** 레이블.  
  
7.  에 **속성** 창에서 옆에 확인란은 **IsReadOnly** 속성입니다.  
  
## <a name="navigating-product-records"></a>제품 레코드 탐색  
 사용자가을 사용 하 여 제품 레코드를 스크롤할 수 있도록 하는 코드를 추가  **\<**  및  **>**  단추입니다.  
  
#### <a name="to-enable-users-to-navigate-product-records"></a>사용자가 제품 레코드를 탐색할 수 있도록 설정하려면  
  
1.  디자이너에서 두 번 클릭 하 고  **<**  창 화면에서 단추입니다.  
  
     Visual Studio 코드 숨김 파일이 열리고 새 `backButton_Click` 에 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
2.  수정는 `Window_Loaded` 이벤트 처리기 이므로 `ProductViewSource`, `AdventureWorksLTDataSet`, 및 `AdventureWorksLTDataSetProductTableAdapter` 메서드는 외부 및 전체 폼에 액세스할 수 있습니다. 폼에 전역에 이러한 선언 하 고 내에서 할당 된 `Window_Loaded` 다음과 비슷한 이벤트 처리기:  
  
     [!code-csharp[Data_WPFDATASET#1](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_1.cs)]
     [!code-vb[Data_WPFDATASET#1](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_1.vb)]  
  
3.  다음 코드를 `backButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[Data_WPFDATASET#2](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_2.cs)]
     [!code-vb[Data_WPFDATASET#2](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_2.vb)]  
  
4.  디자이너를 돌아가서 두 번 클릭은  **>**  단추입니다.  
  
5.  다음 코드를 `nextButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[Data_WPFDATASET#3](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_3.cs)]
     [!code-vb[Data_WPFDATASET#3](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_3.vb)]  
  
## <a name="save-changes-to-product-records"></a>제품 레코드 변경 내용을 저장합니다  
사용자가 사용 하 여 제품 레코드 변경 내용을 저장할 수 있는 코드를 추가 **ब ा ळ** 단추입니다.  
  
#### <a name="to-add-the-ability-to-save-changes-to-product-records"></a>제품 레코드 변경 내용을 저장하는 기능을 추가하려면  
  
1.  디자이너에서 두 번 클릭 하 여 **ब ा ळ** 단추입니다.  
  
     Visual Studio 코드 숨김 파일이 열리고 새 `saveButton_Click` 에 대 한 이벤트 처리기는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트입니다.  
  
2.  다음 코드를 `saveButton_Click` 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[Data_WPFDATASET#4](../data-tools/codesnippet/CSharp/bind-wpf-controls-to-a-dataset_4.cs)]
     [!code-vb[Data_WPFDATASET#4](../data-tools/codesnippet/VisualBasic/bind-wpf-controls-to-a-dataset_4.vb)]  
  
    > [!NOTE]
    >  이 예에서는 `Save`의 `TableAdapter` 메서드를 사용하여 변경 내용을 저장합니다. 이 연습에서는 데이터 테이블을 하나만 변경하므로 이러한 방식이 적절합니다. 여러 데이터 테이블의 변경 내용을 저장해야 하는 경우에는 데이터 집합과 함께 생성되는 `UpdateAll`의 `TableAdapterManager` 메서드를 사용할 수 있습니다. 자세한 내용은 참조 [Tableadapter](../data-tools/create-and-configure-tableadapters.md)합니다.  
  
## <a name="test-the-application"></a>응용 프로그램 테스트  
 응용 프로그램을 빌드 및 실행합니다. 제품 레코드를 보고 업데이트할 수 있는지 확인합니다.  
  
#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면  
  
1.  **F5**키를 누릅니다.  
  
     응용 프로그램이 빌드되고 실행됩니다. 다음 사항을 확인합니다.  
  
    -   텍스트 상자에 사진이 포함된 첫 번째 제품 레코드의 데이터가 표시됩니다. 이 제품의 이름과 ID는 713 **Long-sleeve Logo Jersey, S**합니다.  
  
    -   클릭할 수는  **>**  또는  **<**  다른 제품 레코드를 탐색 하는 단추입니다.  
  
2.  제품 레코드 중 하나에서 변경 된 **크기** 값을 클릭 한 다음 **ब ा ळ**합니다.  
  
3.  응용 프로그램을 닫은 다음 키를 눌러 응용 프로그램을 다시 시작 **F5** Visual Studio에서.  
  
4.  변경한 제품 레코드로 이동하여 변경 내용이 유지되었는지를 확인합니다.  
  
5.  응용 프로그램을 닫습니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습을 완료하고 나면 다음과 같은 관련 작업을 수행할 수 있습니다.  
  
-   사용 하는 **데이터 소스** WPF 바인딩할 Visual Studio의 창 컨트롤을 다른 형식의 데이터 원본. 자세한 내용은 참조 [WCF 데이터 서비스에 바인딩할 WPF 컨트롤](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)합니다.  
  
-   사용 하는 **데이터 소스** WPF 컨트롤에 관련된 데이터 (즉, 부모-자식 관계의 데이터)를 표시 하는 Visual Studio의 창. 자세한 내용은 참조 [연습: WPF 응용 프로그램의 관련 데이터 표시](../data-tools/display-related-data-in-wpf-applications.md)합니다.  
  
## <a name="see-also"></a>참고 항목
[Visual Studio에서 데이터에에서 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)   
[Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)   
[데이터 바인딩 개요](/dotnet/framework/wpf/data/data-binding-overview)
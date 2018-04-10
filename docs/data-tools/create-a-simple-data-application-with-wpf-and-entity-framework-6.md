---
title: WPF 및 Entity Framework 6 간단한 데이터 응용 프로그램을 만들 | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- CSharp
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 394dbf9aba422f8fbf16857d6980a53b353e931a
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="create-a-simple-data-application-with-wpf-and-entity-framework-6"></a>WPF 및 Entity Framework 6 간단한 데이터 응용 프로그램 만들기

이 연습에서는 Visual Studio에서 SQL Server LocalDB, Northwind 데이터베이스, Entity Framework 6 및 Windows Presentation Foundation으로 기본 "데이터 폼" 응용 프로그램을 만드는 방법을 보여 줍니다. 마스터-세부 정보 보기를 기본 데이터 바인딩 작업을 수행 하는 방법을 보여 줍니다과 함께 사용자 지정 "바인딩 탐색기" "다음 이동"에 대 한 단추를 "이전으로 이동," ", 처음으로 이동" 이동 "을 종료 하려면"에 "업데이트" 및 "삭제" 합니다.  
  
 이 문서는 데이터 도구를 사용 하 여 Visual Studio에서 중점적 하 고 모든 수준에서의 기본 기술에 설명 하려고 하지 않습니다. XAML, Entity Framework 및 SQL에 대 한 기본 지식이 있다고 가정 합니다. 또한이 예제에서는 WPF 응용 프로그램에 대 한 표준 모델-뷰-보기 MVVM (Model) 아키텍처를 보여 주지 않습니다. 그러나 매우 약간만 수정 하 여 MVVM 응용 프로그램에이 코드를 복사할 수 있습니다.  
  
## <a name="install-and-connect-to-northwind"></a>설치 하 고 Northwind로 연결

이 예제에서는 Northwind 샘플 데이터베이스 및 SQL Server Express LocalDB를 사용 합니다. 작동 해야 다른 SQL 데이터베이스 제품과 해당 제품에 대 한 ADO.NET 데이터 공급자는 Entity Framework를 지원 하는 경우.  

1.  SQL Server Express LocalDB가 없는 경우 설치에서 [SQL Server Express 다운로드 페이지](https://www.microsoft.com/sql-server/sql-server-editions-express), 또는 **Visual Studio 설치 관리자**합니다. Visual Studio 설치 관리자 SQL Server Express LocalDB의 일부로 설치할 수 있습니다는 **.NET 데스크톱 개발** 작업 또는 개별 구성 요소입니다.

2.  다음 단계를 수행 하 여 Northwind 샘플 데이터베이스를 설치 합니다.  

    1. Visual Studio에서 열고는 **SQL Server 개체 탐색기** 창. (SQL Server 개체 탐색기의 일부로 설치 되는 **데이터 저장 및 처리** Visual Studio 설치 관리자에서 작업 합니다.) 확장 된 **SQL Server** 노드. LocalDB 인스턴스를 마우스 오른쪽 단추로 클릭 하 고 선택 **새 쿼리 중...** .  

       쿼리 편집기 창이 열립니다.  

    2. 복사는 [Northwind Transact SQL 스크립트](https://github.com/MicrosoftDocs/visualstudio-docs/blob/master/docs/data-tools/samples/northwind.sql?raw=true) 를 클립보드에 복사 합니다. 이 T-SQL 스크립트를 처음부터 Northwind 데이터베이스를 만들고 데이터로 채웁니다.  

    3. 쿼리 편집기에 T-SQL 스크립트를 붙여 넣습니다.를 선택한 후는 **Execute** 단추입니다.  

       짧은 시간 후 쿼리 실행이 완료 되 하 고 Northwind 데이터베이스 생성 됩니다.  
  
3.  [새 연결 추가](../data-tools/add-new-connections.md) Northwind에 대 한 합니다.  
  
## <a name="configure-the-project"></a>프로젝트 구성
  
1.  Visual Studio에서 선택 **파일**, **새로**, **프로젝트...**  한 다음 새 C# WPF 응용 프로그램을 만듭니다.  
  
2.  다음 Entity Framework 6에 대 한 NuGet 패키지를 추가 합니다. 솔루션 탐색기에서 프로젝트 노드를 선택 합니다. 주 메뉴에서 선택 **프로젝트**, **NuGet 패키지 관리...**  
  
     ![메뉴 항목 NuGet 패키지 관리](../data-tools/media/raddata_vs2015_manage_nuget_packages.png "raddata_vs2015_manage_nuget_packages")  
  
3.  NuGet 패키지 관리자에서 클릭 된 **찾아보기** 링크 합니다. Entity Framework 목록에서 최상위 패키지 때문일 수 있습니다. 클릭 **설치** 오른쪽 창에 표시 되는 메시지를 따릅니다. 출력 창은 설치가 완료 되 면 알려를 보여 줍니다.  
  
     ![Entity Framework NuGet 패키지](../data-tools/media/raddata_vs2015_nuget_ef.png "raddata_vs2015_Nuget_EF")  
  
4.  이제 Northwind 데이터베이스 기반 모델을 만들려면 Visual Studio를 사용할 수 있습니다.  
  
## <a name="create-the-model"></a>모델 만들기
  
1.  솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가**, **새 항목...** . C# 노드를 아래 왼쪽된 창에서 선택 **데이터** 가운데 창에서 선택 하 고 **ADO.NET 엔터티 데이터 모델**합니다.  
  
     ![Entity Framework 모델 새 프로젝트 항목](../data-tools/media/raddata-ef-new-project-item.png "raddata EF 새 프로젝트 항목")  

  2.  모델을 호출 `Northwind_model` 확인을 선택 합니다. 그러면는 **엔터티 데이터 모델 마법사**합니다. 선택 **데이터베이스의 EF 디자이너** 클릭 하 고 **다음**합니다.  
  
     ![데이터베이스에서 EF 모델](../data-tools/media/raddata-ef-model-from-database.png "raddata 데이터베이스에서 EF 모델")  
  
3.  다음 화면에서 LocalDB Northwind 연결 및 클릭 선택 **다음**합니다.  
  
4.  마법사의 다음 페이지에서 테이블, 저장된 프로시저 및 Entity Framework 모델에 포함할 다른 데이터베이스 개체 선택 합니다. 트리 뷰에서 dbo 노드를 확장 하 고 고객, 주문 및 주문 세부 정보를 선택 합니다. 기본값이 선택 된 상태로 두고 클릭 **마침**합니다.  
  
     ![모델에 대 한 데이터베이스 개체 선택](../data-tools/media/raddata-choose-ef-objects.png "raddata EF 개체 선택")  
  
5.  Entity Framework 모델을 나타내는 C# 클래스가 생성 됩니다. 다음은 이전 일반 C# 클래스와는 우리는 WPF 사용자 인터페이스에 데이터 바인딩하 합니다. 관계 및 기타 메타 데이터 클래스는 데이터베이스의 개체를 연결 하는.edmx 파일에 설명 합니다.  .Tt 파일은 모델에서 동작 하 고 데이터베이스에 변경 내용을 저장 하는 코드를 생성 하는 T4 템플릿을 합니다. Northwind_model 노드 아래에서 솔루션 탐색기에서 이러한 모든 파일을 확인할 수 있습니다.  

       ![솔루션 탐색기 EF 모델 파일](../data-tools/media/raddata-solution-explorer-ef-model-files.png "raddata 솔루션 탐색기 EF 모델 파일")  
  
     .Edmx 파일에 대 한 디자이너 화면을 사용 하면 일부 속성 및 모델에서 관계를 수정할 수 있습니다. 이 연습에서 디자이너를 사용 하 하지 않을 것입니다.  
  
6.  .Tt 파일은 범용 이며 ObservableCollections를 필요로 하는 WPF 데이터 바인딩 작업 중 하나를 조정 해야 합니다.  솔루션 탐색기에서 Northwind_model.tt 찾을 때까지 Northwind_model 노드를 확장 합니다. (사용자가 있는지 확인 **하지** 에 *입니다. 상황에 맞는.tt 파일은.edmx 파일 바로 아래).  
  
    -   두 개의 항목을 바꿉니다 <xref:System.Collections.ICollection> 와 <xref:System.Collections.ObjectModel.ObservableCollection%601>합니다.  
  
    -   첫 번째 일치 항목을 바꾸려면 <xref:System.Collections.Generic.HashSet%601> 와 <xref:System.Collections.ObjectModel.ObservableCollection%601> 줄 51 합니다. HashSet의 두 번째 항목을 대체 하지 않습니다  
  
    -   유일한 대체할 <xref:System.Collections.Generic> 431 라인) (주위와 <xref:System.Collections.ObjectModel>합니다.  
  
7.  키를 눌러 **Ctrl + Shift + B** 프로젝트를 빌드합니다. 빌드가 완료 되 면 모델 클래스를 사용 하는 데이터 원본 마법사에 표시 됩니다.  
  
이제 보고, 탐색 및 데이터를 수정할 수 있습니다 수 있도록이 모델을 XAML 페이지로 연결 준비가 되었습니다.  
  
## <a name="databind-the-model-to-the-xaml-page"></a>Databind을 XAML 페이지로 모델

사용자 고유의 데이터 바인딩 코드를 작성할 수 있지만 Visual Studio을 대신할 수 있도록 훨씬 쉽습니다.  
  
1.  주 메뉴에서 선택 **프로젝트 > 새 데이터 원본 추가** 불러오는 **데이터 소스 구성 마법사**합니다. 선택 **개체** 모델 클래스에서 데이터베이스로 바인딩하는 것 때문에:  
  
     ![개체 소스와 데이터 소스 구성 마법사](../data-tools/media/raddata-data-source-configuration-wizard-with-object-source.png "raddata 개체 소스와 데이터 소스 구성 마법사")  
  
2.  고객을 선택 합니다.  (주문에 대 한 원본이 자동으로 생성 됨 고객의 주문 탐색 속성에서.)  
  
     ![데이터 원본으로 엔터티 클래스를 추가](../data-tools/media/raddata-add-entity-classes-as-data-sources.png "raddata 엔터티 추가 데이터 원본으로 클래스")  
  
3.  클릭 **마침**  
  
4.  코드 보기에서 MainWindow.xaml을 찾습니다. 이 예제에서는 XAML을 매우 단순하게 유지 하기 위해 하겠습니다. 좀 더 구체적인 MainWindow의 제목을 변경 하 고 지금은 600 x 800 높이 너비를 늘립니다. 하면 항상 나중에 변경할 수 있습니다. 이제 이러한 3 개의 행 정의 주 표에서 고객의 주문을 표시 하는 모눈에 대 한 고객의 세부 정보에 대 한 탐색 단추에 대 한 하나의 행을 추가 합니다.  

    ```xaml  
    <Grid.RowDefinitions>  
            <RowDefinition Height="auto"/>  
            <RowDefinition Height="auto"/>  
            <RowDefinition Height="*"/>  
        </Grid.RowDefinitions>
    ```

5.  이제 디자이너에서 보고 있도록 MainWindow.xaml을 엽니다. 이렇게 하면 데이터 소스 창에 도구 상자 옆의 Visual Studio 창 여백을 옵션으로 표시 합니다. 창을 열고 하거나 다른 키를 눌러 탭을 클릭 **Shift + Alt + D** 선택 또는 **보기 &#124; 다른 창 &#124; 데이터 원본**합니다. 각 속성 자체의 개별 텍스트 상자에 고객 클래스에 표시 하려면 하겠습니다. 먼저 고객 콤보 상자에서 화살표를 클릭 하 고 선택 **세부 정보**합니다. 그런 다음 디자이너 가운데 행에서 이동 하려는 알 수 있도록 디자인 화면의 가운데 부분에 노드를 끕니다.  이 찰 경우 XAML에서 나중에 수동으로 행을 지정할 수 있습니다. 기본적으로 세로 방향으로 눈금 요소에 배치 된 하지만 시점에서 정렬할 수 있습니다는 양식에서 원하는 합니다.  예를 들어 좋을 수 있습니다 이름 텍스트 상자 주소 위에서 위쪽에 넣을 수 있습니다. 필드 다시 정렬 하 고 이러한 두 개의 열으로 다시 정렬 하는이 문서에 대 한 샘플 응용 프로그램입니다.  
  
     ![개별 컨트롤에 고객 데이터 원본 바인딩을](../data-tools/media/raddata-customers-data-source-binding-to-individual-controls.png "을 개별 컨트롤로 raddata 고객 데이터 소스 바인딩")  
  
     코드 보기에서 표시 새 `Grid` 1 행에서 (가운데 행)의 요소는 부모 눈금. 표에 부모는 `DataContext` 참조 하는 CollectionViewSource에 추가 된 특성은 `Windows.Resources` 요소입니다. 해당 데이터 컨텍스트를 지정 하 여 예를 들어 첫 번째 텍스트 상자의 때 "Address" 해당 이름이 스위치에 매핑된는 `Address` 현재에서 속성 `Customer` CollectionViewSource에는 개체입니다.  
  
    ```xaml  
    <Grid DataContext="{StaticResource customerViewSource}">  
    ```  

6.  고객이 창의 상단에 표시 되 면 아래에 있는 고객의 주문을 절반 참조 하려고 합니다. 단일 그리드 뷰 컨트롤에서 주문을 보여줍니다. 예상 대로 작동 하도록 마스터-세부 데이터 바인딩에서 별도 주문 노드로 하지 고객 클래스에 주문 속성에 바인딩할 중요 합니다. 다음 그림에 주의! 디자이너 2 행에 저장 되도록 폼의 아래쪽 절반을 고객 클래스의 순서 속성으로를 끕니다.  
  
     ![주문 클래스 그리드로 끌어](../data-tools/media/raddata-drag-orders-classes-as-grid.png "그리드로 끌어 Orders raddata 클래스")  
  
7.  Visual Studio UI 컨트롤 모델에서 이벤트에 연결 하는 모든 바인딩 코드를 생성 했습니다. 일부 데이터를 확인 하기 위해 수행 해야 하는 모델을 채우는 코드를 작성입니다. 첫 번째 보겠습니다 MainWindow.xaml.cs로 이동 하 고 데이터 컨텍스트에 대 한 MainWindow 클래스 데이터 멤버를 추가 합니다. 이 개체에 생성 되는 역할을 변경 및 모델에 대 한 이벤트를 추적 하는 컨트롤 같이 합니다. 생성자 초기화 논리도 추가 합니다. 클래스의 맨 위에 다음과 같이 표시 됩니다.  
  
     [!code-csharp[MainWindow#1](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#1)]  
     
     추가 `using` System.Data.Entity 부하 확장 메서드를 범위로 가져오기에 대 한 지시문:  
  
     ```csharp
     using System.Data.Entity;  
     ```  

     아래로 스크롤하여 이제 Window_Loaded 이벤트 처리기를 찾습니다. Visual Studio가을 수행해 줍니다 CollectionViewSource 개체를 추가 했습니다 확인 합니다. 모델을 만들 때 선택한 NorthwindEntities 개체를 나타냅니다. 전체 메서드는 이제 다음과 같이 표시 되도록 Window_Loaded에 코드 추가:  

     [!code-csharp[Window_Loaded#2](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#2)]  

8.  **F5**키를 누릅니다. 내용을 CollectionViewSource로 검색 된 첫 번째 고객에 대 한 세부 정보가 표시 됩니다. 또한 고객 주문 데이터 표에 나타납니다. 서식 지정 하겠습니다를 수정 하는 좋은 아닙니다. 또한 다른 레코드를 볼 한 기본적인 CRUD 작업을 수행 하는 방법을 만들어 보겠습니다.  

## <a name="adjust-the-page-design-and-add-grids-for-new-customers-and-orders"></a>페이지 디자인을 조정 하 고 새로운 고객 및 주문에 대 한 표 추가

Visual Studio에서 생성 된 기본 배열을 사용 하면이 응용 프로그램에 적합 하지 않으므로 XAML에 몇 가지 변경을 수동으로 수행 합니다. 또한 일부 "forms" (임 실제로 표) 새 고객 또는 주문과 추가할 사용자를 사용 하도록 설정 해야 합니다. 텍스트 상자에 데이터 바인딩된 되지 않는 별도 집합이 새 고객 및 주문 추가할 수 있도록 필요는 `CollectionViewSource`합니다. 처리기 메서드에서 Visible 속성을 설정 하 여 언제 든 지 사용자에 게는 표를 제어 합니다 우리 합니다. 마지막으로, 개별 주문을 삭제 하려면 사용자 수 있도록 Orders 눈금에서 각 행에 삭제 단추를 추가 합니다.  
  
먼저, MainWindow.xaml의 Windows.Resources 요소에 이러한 스타일을 추가 합니다.  
  
```xaml  
<Style x:Key="Label" TargetType="{x:Type Label}" BasedOn="{x:Null}">  
    <Setter Property="HorizontalAlignment" Value="Left"/>  
    <Setter Property="VerticalAlignment" Value="Center"/>  
    <Setter Property="Margin" Value="3"/>  
    <Setter Property="Height" Value="23"/>  
</Style>  
<Style x:Key="CustTextBox" TargetType="{x:Type TextBox}" BasedOn="{x:Null}">  
    <Setter Property="HorizontalAlignment" Value="Right"/>  
    <Setter Property="VerticalAlignment" Value="Center"/>  
    <Setter Property="Margin" Value="3"/>  
    <Setter Property="Height" Value="26"/>  
    <Setter Property="Width" Value="120"/>  
</Style>  
```  
  
이 태그 외부 모눈을 전체 다음으로 바꿉니다.  
  
```xaml  
<Grid>  
     <Grid.RowDefinitions>  
         <RowDefinition Height="auto"/>  
         <RowDefinition Height="auto"/>  
         <RowDefinition Height="*"/>  
     </Grid.RowDefinitions>   
     <Grid x:Name="existingCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" Margin="5" Visibility="Visible" VerticalAlignment="Top" Background="AntiqueWhite" DataContext="{StaticResource customerViewSource}">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>  
         <TextBox x:Name="customerIDTextBox"  Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Company Name:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="companyNameTextBox"  Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Name:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Title:"  Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>  
         <TextBox x:Name="addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="City:" Grid.Column="1" Grid.Row="0"  Style="{StaticResource Label}"/>  
         <TextBox x:Name="cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>  
         <TextBox x:Name="postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <Grid x:Name="newCustomerGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding RelativeSource={RelativeSource FindAncestor, AncestorType={x:Type Window}}, Path=newCustomer, UpdateSourceTrigger=Explicit}" Visibility="Collapsed" Background="CornflowerBlue">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="Customer ID:" Grid.Row="0" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_customerIDTextBox"  Grid.Row="0"  Style="{StaticResource CustTextBox}"   
                  Text="{Binding CustomerID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Company Name:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_companyNameTextBox"  Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding CompanyName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true }"/>  
         <Label Content="Contact Name:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_contactNameTextBox" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactName, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Contact Title:"  Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_contactTitleTextBox" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ContactTitle, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Address:" Grid.Row="4" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_addressTextBox" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Address, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="City:" Grid.Column="1" Grid.Row="0"  Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_cityTextBox" Grid.Column="1" Grid.Row="0" Style="{StaticResource CustTextBox}"   
                  Text="{Binding City, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Country:" Grid.Column="1" Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_countryTextBox" Grid.Column="1" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Country, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Fax:" Grid.Column="1" Grid.Row="2" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_faxTextBox" Grid.Column="1" Grid.Row="2" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Fax, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Phone:" Grid.Column="1" Grid.Row="3" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_phoneTextBox" Grid.Column="1" Grid.Row="3" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Phone, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Postal Code:" Grid.Column="1" Grid.Row="4" VerticalAlignment="Center" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_postalCodeTextBox" Grid.Column="1" Grid.Row="4" Style="{StaticResource CustTextBox}"   
                  Text="{Binding PostalCode, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Region:" Grid.Column="1" Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_regionTextBox" Grid.Column="1" Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Region, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <Grid x:Name="newOrderGrid" Grid.Row="1" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="5" DataContext="{Binding Path=newOrder, Mode=TwoWay}" Visibility="Collapsed" Background="LightGreen">  
         <Grid.ColumnDefinitions>  
             <ColumnDefinition Width="Auto" MinWidth="233"/>  
             <ColumnDefinition Width="Auto" MinWidth="397"/>  
         </Grid.ColumnDefinitions>  
         <Grid.RowDefinitions>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
             <RowDefinition Height="Auto"/>  
         </Grid.RowDefinitions>  
         <Label Content="New Order Form" FontWeight="Bold"/>  
         <Label Content="Employee ID:"  Grid.Row="1" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_employeeIDTextBox" Grid.Row="1" Style="{StaticResource CustTextBox}"   
                  Text="{Binding EmployeeID, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Order Date:"  Grid.Row="2" Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_orderDatePicker" Grid.Row="2"  HorizontalAlignment="Right" Width="120"  
                 SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Required Date:" Grid.Row="3" Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_requiredDatePicker" Grid.Row="3" HorizontalAlignment="Right" Width="120"  
                  SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Shipped Date:"  Grid.Row="4"  Style="{StaticResource Label}"/>  
         <DatePicker x:Name="add_shippedDatePicker"  Grid.Row="4"  HorizontalAlignment="Right" Width="120"  
                 SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
         <Label Content="Ship Via:"  Grid.Row="5" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_ShipViaTextBox"  Grid.Row="5" Style="{StaticResource CustTextBox}"   
                  Text="{Binding ShipVia, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
         <Label Content="Freight"  Grid.Row="6" Style="{StaticResource Label}"/>  
         <TextBox x:Name="add_freightTextBox" Grid.Row="6" Style="{StaticResource CustTextBox}"   
                  Text="{Binding Freight, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true}"/>  
     </Grid>  
     <DataGrid x:Name="ordersDataGrid" SelectionUnit="Cell" SelectionMode="Single" AutoGenerateColumns="False" CanUserAddRows="false" IsEnabled="True" EnableRowVirtualization="True" Width="auto" ItemsSource="{Binding Source={StaticResource customerOrdersViewSource}}" Margin="10,10,10,10" Grid.Row="2" RowDetailsVisibilityMode="VisibleWhenSelected">  
         <DataGrid.Columns>  
             <DataGridTemplateColumn>  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <Button Content="Delete"  Command="{StaticResource DeleteOrderCommand}" CommandParameter="{Binding}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="customerIDColumn" Binding="{Binding CustomerID}" Header="Customer ID" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="employeeIDColumn" Binding="{Binding EmployeeID}" Header="Employee ID" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="freightColumn" Binding="{Binding Freight}" Header="Freight" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="orderDateColumn" Header="Order Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding OrderDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="orderIDColumn" Binding="{Binding OrderID}" Header="Order ID" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="requiredDateColumn" Header="Required Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding RequiredDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="shipAddressColumn" Binding="{Binding ShipAddress}" Header="Ship Address" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipCityColumn" Binding="{Binding ShipCity}" Header="Ship City" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipCountryColumn" Binding="{Binding ShipCountry}" Header="Ship Country" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipNameColumn" Binding="{Binding ShipName}" Header="Ship Name" Width="SizeToHeader"/>  
             <DataGridTemplateColumn x:Name="shippedDateColumn" Header="Shipped Date" Width="SizeToHeader">  
                 <DataGridTemplateColumn.CellTemplate>  
                     <DataTemplate>  
                         <DatePicker SelectedDate="{Binding ShippedDate, Mode=TwoWay, NotifyOnValidationError=true, ValidatesOnExceptions=true, UpdateSourceTrigger=PropertyChanged}"/>  
                     </DataTemplate>  
                 </DataGridTemplateColumn.CellTemplate>  
             </DataGridTemplateColumn>  
             <DataGridTextColumn x:Name="shipPostalCodeColumn" Binding="{Binding ShipPostalCode}" Header="Ship Postal Code" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipRegionColumn" Binding="{Binding ShipRegion}" Header="Ship Region" Width="SizeToHeader"/>  
             <DataGridTextColumn x:Name="shipViaColumn" Binding="{Binding ShipVia}" Header="Ship Via" Width="SizeToHeader"/>  
         </DataGrid.Columns>  
     </DataGrid>  
 </Grid>  
```  
  
## <a name="add-buttons-to-navigate-add-update-and-delete"></a>단추를 이동, 추가, 업데이트, 삭제 및 추가  

Windows Forms 응용 프로그램에서 데이터베이스의 행을 탐색 및 한 기본적인 CRUD 작업을 수행 하는 데 단추가 포함 된 BindingNavigator 개체를 가져옵니다. WPF는 BindingNavigator 제공 하지는 않지만 쉽게 하나 만듭니다. 에서는 이러한 작업을 수행 가로 StackPanel 내부의 단추와 하 고 뒤에 있는 코드의 메서드에 바인딩되는 명령 단추 연결 합니다.  
  
Fours 명령 논리 부분이 있습니다: (1) 명령, (2)는 바인딩, (3)는 단추 및 (4) 명령 처리기 코드 숨김에서 합니다.  
  
### <a name="add-commands-bindings-and-buttons-in-xaml"></a>XAML에서 명령, 바인딩 및 단추 추가
  
1.  첫째, Windows.Resources 요소 내에서 MainWindow.xaml 파일에서 명령을 추가 해 보겠습니다.  
  
    ```xaml  
    <RoutedUICommand x:Key="FirstCommand" Text="First"/>  
    <RoutedUICommand x:Key="LastCommand" Text="Last"/>  
    <RoutedUICommand x:Key="NextCommand" Text="Next"/>  
    <RoutedUICommand x:Key="PreviousCommand" Text="Previous"/>  
    <RoutedUICommand x:Key="DeleteCustomerCommand" Text="Delete Customer"/>  
    <RoutedUICommand x:Key="DeleteOrderCommand" Text="Delete Order"/>  
    <RoutedUICommand x:Key="UpdateCommand" Text="Update"/>  
    <RoutedUICommand x:Key="AddCommand" Text="Add"/>  
    <RoutedUICommand x:Key="CancelCommand" Text="Cancel"/>  
    ```  
  
2.  CommandBinding RoutedUICommand 이벤트를 뒤에 있는 코드의 메서드에 매핑합니다. 닫는 태그 Windows.Resources 뒤이 CommandBindings 요소를 추가 합니다.  
  
    ```xaml  
    <Window.CommandBindings>  
        <CommandBinding Command="{StaticResource FirstCommand}" Executed="FirstCommandHandler"/>  
        <CommandBinding Command="{StaticResource LastCommand}" Executed="LastCommandHandler"/>  
        <CommandBinding Command="{StaticResource NextCommand}" Executed="NextCommandHandler"/>  
        <CommandBinding Command="{StaticResource PreviousCommand}" Executed="PreviousCommandHandler"/>  
        <CommandBinding Command="{StaticResource DeleteCustomerCommand}" Executed="DeleteCustomerCommandHandler"/>  
        <CommandBinding Command="{StaticResource DeleteOrderCommand}" Executed="DeleteOrderCommandHandler"/>  
        <CommandBinding Command="{StaticResource UpdateCommand}" Executed="UpdateCommandHandler"/>  
        <CommandBinding Command="{StaticResource AddCommand}" Executed="AddCommandHandler"/>  
        <CommandBinding Command="{StaticResource CancelCommand}" Executed="CancelCommandHandler"/>  
    </Window.CommandBindings>  
    ```  
  
3.  이제 보겠습니다 StackPanel 탐색와 추가, 추가, 삭제 및 단추를 업데이트 합니다. 첫째, Windows.Resources를이 스타일을 추가 합니다.  
  
    ```xaml  
    <Style x:Key="NavButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="FontSize" Value="24"/>  
        <Setter Property="FontFamily" Value="Segoe UI Symbol"/>  
        <Setter Property="Margin" Value="2,2,2,0"/>  
        <Setter Property="Width" Value="40"/>  
        <Setter Property="Height" Value="auto"/>  
    </Style>  
    ```  
  
     둘째, RowDefinitions XAML 페이지의 위쪽 외부 표 요소에 대 한 직후이 코드를 붙여 넣습니다.  
  
    ```xaml  
    <StackPanel Orientation="Horizontal" Margin="2,2,2,0" Height="36" VerticalAlignment="Top" Background="Gainsboro" DataContext="{StaticResource customerViewSource}" d:LayoutOverrides="LeftMargin, RightMargin, TopMargin, BottomMargin">  
        <Button Name="btnFirst" Content="|◄" Command="{StaticResource FirstCommand}" Style="{StaticResource NavButton}"  />  
        <Button Name="btnPrev" Content="◄" Command="{StaticResource PreviousCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnNext" Content="►" Command="{StaticResource NextCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnLast" Content="►|" Command="{StaticResource LastCommand}" Style="{StaticResource NavButton}"/>  
        <Button Name="btnDelete" Content="Delete Customer" Command="{StaticResource DeleteCustomerCommand}" FontSize="11" Width="120" Style="{StaticResource NavButton}"/>  
        <Button Name="btnAdd" Content="New Customer" Command="{StaticResource AddCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
        <Button Content="New Order" Name="btnNewOrder" FontSize="11" Width="80" Style="{StaticResource NavButton}" Click="NewOrder_click"/>  
        <Button Name="btnUpdate" Content="Commit" Command="{StaticResource UpdateCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
        <Button Content="Cancel" Name="btnCancel" Command="{StaticResource CancelCommand}" FontSize="11" Width="80" Style="{StaticResource NavButton}"/>  
    </StackPanel>  
    ```  
  
### <a name="add-command-handlers-to-the-mainwindow-class"></a>MainWindow 클래스에 명령 처리기를 추가 합니다.  
  
코드 숨김을 추가 및 삭제 방법을 제외 하 고 최소화 됩니다. 탐색 뷰 속성을 CollectionViewSource에 메서드를 호출 하 여 수행 됩니다. DeleteOrderCommandHandler 한 주문의 하위 삭제를 수행 하는 방법을 보여 줍니다. 그와 관련 된 Order_Details를 먼저 삭제 해야 합니다. UpdateCommandHandler 새 고객 또는 주문과 컬렉션에 추가 합니다. 그렇지 않으면 방금 변경한 사용자 텍스트 상자에는 기존 고객 또는 순서를 업데이트 합니다.  
  
MainWindow.xaml.cs의 MainWindow 클래스에이 처리기 메서드를 추가 합니다. Customers 테이블에 대 한 프로그램 CollectionViewSource 이름이 다른 경우 다음 조정 하면 이러한 각 방법의 이름:  
  
[!code-csharp[CommandHandlers#3](../data-tools/codesnippet/CSharp/CreateWPFDataApp/MainWindow.xaml.cs#3)]  
  
## <a name="run-the-application"></a>응용 프로그램 실행

디버깅을 시작하려면 **F5** 키를 누릅니다. 고객 및 주문 데이터가 표에서 채워진 표시 되어야 하 고 탐색 단추의 예상 대로 작동 해야 합니다. "커밋" 데이터를 입력 한 후 모델에 새 고객 또는 주문과 추가 하려면 클릭 합니다. 새 고객 또는 새 주문 양식 데이터를 저장 하지 않고 취소 하려면 "취소"를 클릭 합니다. 기존 고객과 텍스트 상자에 직접 주문을 편집할 수 하 고 해당 변경 내용이 모델에 자동으로 기록 됩니다.  
  
## <a name="see-also"></a>참고자료

[.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)  
[Entity Framework 설명서](/ef/)
---
title: "연습: 데이터베이스에 데이터 저장(여러 테이블) | Microsoft Docs"
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
  - "데이터[Visual Studio], 저장"
  - "데이터[Visual Studio], 업데이트"
  - "데이터 저장, 연습"
  - "데이터 집합 업데이트, 연습"
ms.assetid: 7ebe03da-ce8c-4cbc-bac0-a2fde4ae4d07
caps.latest.revision: 24
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 데이터베이스에 데이터 저장(여러 테이블)
응용 프로그램 개발에서 가장 일반적인 시나리오는 Windows 응용 프로그램의 폼에 데이터를 표시하고 데이터를 편집한 다음 업데이트된 데이터를 데이터베이스로 다시 보내는 것입니다.  이 연습에서는 두 관련 테이블의 데이터를 표시하는 폼을 만들고, 레코드를 편집한 다음 변경 내용을 데이터베이스에 다시 저장하는 방법을 보여줍니다.  이 예에서는 Northwind 샘플 데이터베이스의 `Customers` 및 `Orders` 테이블을 사용합니다.  
  
 TableAdapter의 `Update` 메서드를 호출하여 응용 프로그램의 데이터를 데이터베이스에 다시 저장할 수 있습니다.  **데이터 소스** 창에서 항목을 끌면 데이터를 저장하는 코드가 폼에 놓은 첫 번째 테이블에 대해 자동으로 추가됩니다.  폼에 테이블을 더 추가할 때마다 데이터를 저장하는 데 필요한 코드를 수동으로 추가해야 합니다.  이 연습에서는 둘 이상의 테이블에서 업데이트를 저장하는 코드를 추가하는 방법을 보여줍니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새 **Windows 응용 프로그램** 프로젝트를 만듭니다.  
  
-   [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 응용 프로그램의 데이터 소스를 만들고 구성합니다.  
  
-   [데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 항목의 컨트롤을 설정합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
-   **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다.  
  
-   데이터 집합의 각 테이블에서 레코드 두 개를 수정합니다.  
  
-   데이터 집합의 업데이트된 데이터를 데이터베이스로 다시 보내도록 코드를 수정합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## Windows 응용 프로그램 만들기  
 첫 번째 단계에서는 **Windows 응용 프로그램**을 만듭니다.  이 단계에서는 프로젝트에 반드시 이름을 할당하지 않아도 됩니다. 그러나 이 연습에서는 프로젝트를 나중에 저장할 예정이므로 이름을 지정합니다.  
  
#### 새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로젝트 이름을 `UpdateMultipleTablesWalkthrough`로 지정합니다.  
  
3.  **Windows 응용 프로그램**을 선택하고 **확인**을 클릭합니다.  자세한 내용은 [클라이언트 응용 프로그램](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md)을 참조하십시오.  
  
     **UpdateMultipleTablesWalkthrough** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## 데이터 소스 만들기  
 이 단계에서는 **데이터 소스 구성 마법사**를 사용하여 Northwind 데이터베이스에서 데이터 소스를 만듭니다.  연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다.  Northwind 샘플 데이터베이스를 설정하는 방법에 대한 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)를 참조하세요.  
  
#### 데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  **데이터 연결 선택** 페이지에서 다음 중 한 가지를 수행합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   **새 연결**을 선택하여 **연결 추가\/수정** 대화 상자를 엽니다.  
  
5.  데이터베이스에 암호가 필요하면 중요한 데이터를 포함하는 옵션을 선택하고 **다음**을 클릭합니다.  
  
6.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.  
  
8.  **Customers** 및 **Orders** 테이블을 선택한 다음 **마침**을 클릭합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 테이블이 **데이터 소스** 창에 나타납니다.  
  
## 만들 컨트롤 설정  
 이 연습에서는 `Customers` 테이블의 데이터를 개별 컨트롤에서 데이터가 표시되는 **Details** 레이아웃에 배치합니다.  `Orders` 테이블의 데이터는 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시되는 **Grid** 레이아웃에 배치됩니다.  
  
#### 데이터 소스 창에서 항목에 대한 삭제 유형을 설정하려면  
  
1.  **데이터 소스** 창에서 **Customers** 노드를 확장합니다.  
  
2.  **Customers** 노드의 컨트롤 목록에서 **Details**를 선택하여 **Customers** 테이블의 컨트롤을 개별 컨트롤로 변경합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
## 데이터 바인딩된 폼 만들기  
 **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다.  
  
#### 폼에서 데이터 바인딩된 컨트롤을 만들려면  
  
1.  주 **Customers** 노드를 **데이터 소스** 창에서 **Form1**로 끌어 옵니다.  
  
     설명 레이블이 있는 데이터 바인딩된 컨트롤이 레코드 탐색을 위한 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>와 함께 폼에 나타납니다.  [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), [CustomersTableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
2.  관련 **Orders** 노드를 **데이터 소스** 창에서 **Form1**로 끌어 옵니다.  
  
    > [!NOTE]
    >  **Fax** 열 아래에 있는 관련 **Orders** 노드는 **Customers** 노드의 자식 노드입니다.  
  
     <xref:System.Windows.Forms.DataGridView> 컨트롤과 레코드 탐색에 사용되는 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>가 폼에 나타납니다.  [OrdersTableAdapter](../data-tools/tableadapter-overview.md) 및 <xref:System.Windows.Forms.BindingSource>가 구성 요소 트레이에 표시됩니다.  
  
## 데이터베이스를 업데이트하는 코드 추가  
 **Customers** 및 **Orders** TableAdapter의 `Update` 메서드를 호출하여 데이터베이스를 업데이트할 수 있습니다.  기본적으로 <xref:System.Windows.Forms.BindingNavigator>의 **저장** 단추에 대한 이벤트 처리기는 데이터베이스에 업데이트를 보내는 폼의 코드에 추가됩니다.  이 절차에서는 참조 무결성 오류 발생 가능성을 없애기 위해 업데이트를 적절한 순서로 보내도록 해당 코드를 수정합니다.  또한 이 코드는 try\-catch 블록에서 업데이트 호출을 래핑하여 오류 처리를 구현합니다.  응용 프로그램의 요구 사항에 맞게 코드를 수정할 수 있습니다.  
  
> [!NOTE]
>  이 연습에서는 명확한 설명을 위해 트랜잭션을 사용하지 않지만 둘 이상의 관련 테이블을 업데이트하는 경우에는 모든 업데이트 논리를 트랜잭션 내에 포함해야 합니다.  트랜잭션은 변경 내용을 커밋하기 전에 데이터베이스에 대한 모든 관련 변경 사항이 정상적으로 수행되었는지를 확인하는 프로세스입니다.  자세한 내용은 [트랜잭션 및 동시성](../Topic/Transactions%20and%20Concurrency.md)을 참조하십시오.  
  
#### 응용 프로그램에 업데이트 논리를 추가하려면  
  
1.  <xref:System.Windows.Forms.BindingNavigator>에서 **저장** 단추를 두 번 클릭하여 `bindingNavigatorSaveItem_Click` 이벤트 처리기에 대해 코드 편집기를 엽니다.  
  
2.  관련 TableAdapter의 `Update` 메서드를 호출하도록 이벤트 처리기의 코드를 바꿉니다.  다음 코드는 먼저 각 <xref:System.Data.DataRowState>\(<xref:System.Data.DataRowState>, <xref:System.Data.DataRowState> 및 <xref:System.Data.DataRowState>\)에 대해 업데이트된 정보를 저장할 3개 임시 데이터 테이블을 만듭니다.  그런 다음 적절한 순서로 업데이트를 수행합니다.  이 코드는 다음과 같습니다.  
  
     [!code-vb[VbRaddataSaving#10](../data-tools/codesnippet/VisualBasic/save-data-to-a-database-multiple-tables_1.vb)]
     [!code-cs[VbRaddataSaving#10](../data-tools/codesnippet/CSharp/save-data-to-a-database-multiple-tables_1.cs)]  
  
## 응용 프로그램 테스트  
  
#### 응용 프로그램을 테스트하려면  
  
1.  F5 키를 누릅니다.  
  
2.  각 테이블에 포함된 레코드 하나 이상의 데이터를 변경해 봅니다.  
  
3.  **저장** 단추를 누릅니다.  
  
4.  데이터베이스의 값을 점검하여 변경 내용이 저장되었는지 확인합니다.  
  
## 다음 단계  
 응용 프로그램 요구 사항에 따라 Windows 응용 프로그램에서 데이터 바인딩된 폼을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다.  이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
-   폼에 검색 기능을 추가합니다.  자세한 내용은 [방법: Windows Forms 응용 프로그램에 매개 변수가 있는 Query 추가](../Topic/How%20to:%20Add%20a%20Parameterized%20Query%20to%20a%20Windows%20Forms%20Application.md)을 참조하십시오.  
  
-   데이터 소스를 편집하여 데이터베이스 개체를 추가하거나 편집합니다.  자세한 내용은 [방법: 데이터 집합 편집](../Topic/How%20to:%20Edit%20a%20Dataset.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
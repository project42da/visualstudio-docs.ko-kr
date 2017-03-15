---
title: "연습: 데이터 검색을 위한 Windows Form 만들기 | Microsoft Docs"
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
  - "데이터[Visual Studio], 쿼리에 매개 변수 사용"
  - "데이터[Visual Studio], 검색"
  - "매개 변수, 필터링된 데이터 표시"
  - "Windows Forms, 데이터 표시"
  - "Windows Forms, 데이터 검색"
ms.assetid: 65ca79a9-7458-466c-af55-978cd24c549e
caps.latest.revision: 28
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 데이터 검색을 위한 Windows Form 만들기
일반적인 응용 프로그램 시나리오에서는 선택한 데이터를 폼에 표시합니다.  특정 고객의 주문이나 특정 주문의 정보를 표시하려는 경우를 예로 들 수 있습니다.  이 시나리오에서는 사용자가 폼에 정보를 입력하면 해당 사용자의 입력을 매개 변수로 사용하여 쿼리가 실행됩니다. 즉 매개 변수가 있는 쿼리를 기준으로 데이터가 선택됩니다.  쿼리는 사용자가 입력한 기준을 만족하는 데이터만 반환합니다.  이 연습에서는 특정 구\/군\/시의 고객을 반환하는 쿼리를 만들고 사용자 인터페이스를 수정하여, 사용자가 구\/군\/시 이름을 입력한 후 단추를 눌러 쿼리를 실행할 수 있도록 하는 방법을 보여줍니다.  
  
 매개 변수가 있는 쿼리를 사용하면 데이터베이스가 레코드를 빠르게 필터링하도록 함으로써 응용 프로그램의 효율성을 높일 수 있습니다.  반면 전체 데이터베이스 테이블을 요청하여 네트워크를 통해 전송한 다음 응용 프로그램 논리를 사용하여 원하는 레코드를 찾는 경우 응용 프로그램의 속도와 효율성이 떨어질 수 있습니다.  
  
 [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)를 사용하면 모든 TableAdapter와 컨트롤에 매개 변수가 있는 쿼리를 추가하여 매개 변수 값을 수락하고 쿼리를 실행하도록 할 수 있습니다.  **데이터** 메뉴 또는 TableAdapter 스마트 태그에서 **쿼리 추가** 명령을 선택하여 대화 상자를 엽니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새 **Windows 응용 프로그램** 프로젝트를 만듭니다.  
  
-   [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 응용 프로그램의 데이터 소스를 만들고 구성합니다.  
  
-   [데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 항목의 삭제 형식을 설정합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
-   **데이터 소스** 창에서 폼으로 항목을 끌어 데이터를 표시하는 컨트롤을 만듭니다.  
  
-   폼에 데이터를 표시하기 위한 컨트롤을 추가합니다.  
  
-   [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)에서 필요한 작업을 완료합니다.  
  
-   폼에 매개 변수를 입력하고 매개 변수가 있는 쿼리를 실행합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## Windows 응용 프로그램 만들기  
 첫 번째 단계에서는 **Windows 응용 프로그램**을 만듭니다.  이 단계에서는 프로젝트에 반드시 이름을 할당하지 않아도 됩니다. 그러나 이 연습에서는 프로젝트를 나중에 저장할 예정이므로 이름을 지정합니다.  
  
#### 새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로젝트 이름을 `WindowsSearchForm`로 지정합니다.  
  
3.  **Windows 응용 프로그램**을 선택하고 **확인**을 클릭합니다.  자세한 내용은 [클라이언트 응용 프로그램](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md)을 참조하십시오.  
  
     **WindowsSearchForm** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## 데이터 소스 만들기  
 이 단계에서는 **데이터 소스 구성 마법사**를 사용하여 데이터베이스에서 데이터 소스를 만듭니다.  연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다.  Northwind 샘플 데이터베이스를 설정하는 방법에 대한 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)를 참조하세요.  
  
#### 데이터 소스를 만들려면  
  
1.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
2.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 선택하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
3.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택하고 **다음**을 클릭합니다.  
  
4.  **데이터 연결 선택** 페이지에서 다음 중 한 가지를 수행합니다.  
  
    -   Northwind 샘플 데이터베이스에 대한 데이터 연결이 드롭다운 목록에 표시되면 해당 연결을 선택합니다.  
  
         또는  
  
    -   **새 연결**을 선택하여 **연결 추가\/수정** 대화 상자를 시작합니다.  
  
5.  데이터베이스에 암호가 필요하면 중요한 데이터를 포함하는 옵션을 선택하고 **다음**을 클릭합니다.  
  
6.  **응용 프로그램 구성 파일에 연결 문자열 저장** 페이지에서 **다음**을 클릭합니다.  
  
7.  **데이터베이스 개체 선택** 페이지에서 **테이블** 노드를 확장합니다.  
  
8.  **Customers** 테이블을 선택하고 **마침**을 클릭합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 **Customers** 테이블이 **데이터 소스** 창에 나타납니다.  
  
## 폼 만들기  
 **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다.  
  
#### 폼에서 데이터 바인딩된 컨트롤을 만들려면  
  
1.  **데이터 소스** 창에서 **Customers** 노드를 확장합니다.  
  
2.  **Customers** 노드를 **데이터 소스** 창에서 폼으로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.DataGridView>와 레코드 탐색에 사용되는 도구 스트립\(<xref:System.Windows.Forms.BindingNavigator>\)이 폼에 나타납니다.  [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), [CustomersTableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
## 쿼리에 매개 변수화\(검색 기능\) 추가  
 [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)를 사용하여 원래 쿼리에 WHERE 절을 추가할 수 있습니다.  
  
#### 매개 변수가 있는 쿼리와 컨트롤을 만들어 매개 변수를 입력하려면  
  
1.  <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택하고 **데이터** 메뉴에서 **쿼리 추가**를 선택합니다.  
  
2.  [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)의 **새 쿼리 이름** 영역에 `FillByCity`를 입력합니다.  
  
3.  쿼리의 **쿼리 텍스트** 영역에 `WHERE City = @City`를 추가합니다.  
  
     이 쿼리는 다음과 같아야 합니다.  
  
     `SELECT CustomerID, CompanyName, ContactName, ContactTitle, Address, City, Region, PostalCode, Country, Phone, Fax`  
  
     `FROM Customers`  
  
     `WHERE City = @City`  
  
    > [!NOTE]
    >  Access 및 OleDb 데이터 소스는 물음표 '?'를 사용하여 매개 변수를 표기하므로 WHERE 절은 `WHERE City = ?`와 같습니다.  
  
4.  **확인**을 클릭하여 **검색 조건 작성기** 대화 상자를 닫습니다.  
  
     **FillByCityToolStrip**이 폼에 추가됩니다.  
  
## 응용 프로그램 테스트  
 응용 프로그램을 실행하면 매개 변수를 입력으로 사용할 수 있는 폼이 열립니다.  
  
#### 응용 프로그램을 테스트하려면  
  
1.  F5 키를 눌러 응용 프로그램을 실행합니다.  
  
2.  **City** 텍스트 상자에 London을 입력하고 **FillByCity**를 클릭합니다.  
  
     데이터 표가 매개 변수화 기준을 충족하는 고객으로 채워집니다.  이 예에서 데이터 표에는 **City** 열의 값이 **London**인 고객만 표시됩니다.  
  
## 다음 단계  
 응용 프로그램 요구 사항에 따라 매개 변수가 있는 폼을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다.  이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
-   관련 데이터를 표시하는 컨트롤을 추가합니다.  자세한 내용은 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)을 참조하십시오.  
  
-   데이터 집합을 편집하여 데이터베이스 개체를 추가하거나 편집합니다.  자세한 내용은 [방법: 데이터 집합 편집](../Topic/How%20to:%20Edit%20a%20Dataset.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [BindingSource 구성 요소 개요](../Topic/BindingSource%20Component%20Overview.md)   
 [BindingNavigator 컨트롤 개요](../Topic/BindingNavigator%20Control%20Overview%20\(Windows%20Forms\).md)
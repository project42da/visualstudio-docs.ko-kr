---
title: "연습: 데이터 집합 디자이너를 사용하여 데이터 집합 만들기 | Microsoft Docs"
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
  - "데이터[Visual Studio], 데이터 집합 디자이너"
  - "데이터 집합 디자이너, 연습"
  - "데이터 집합[Visual Basic], 만들기"
  - "데이터 집합[Visual Basic], 연습"
  - "XML 스키마, 데이터 집합 만들기"
ms.assetid: 12360f54-db6c-45d2-a91f-fee43214b555
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 연습: 데이터 집합 디자이너를 사용하여 데이터 집합 만들기
이 연습에서는 **데이터 집합 디자이너**를 사용하여 데이터 집합을 만듭니다.  새 프로젝트를 만들고 여기에 새로운 **데이터 집합** 항목을 추가하는 방법을 단계별로 안내합니다.  마법사를 사용하지 않고 데이터베이스의 테이블을 기반으로 하여 테이블을 만드는 방법을 배웁니다.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   새 **Windows 응용 프로그램** 프로젝트를 만듭니다.  
  
-   프로젝트에 빈 **데이터 집합** 항목을 추가합니다.  
  
-   **데이터 집합 디자이너**로 데이터 집합을 만들어서 응용 프로그램에 데이터 소스를 만들고 구성합니다.  
  
-   **서버 탐색기**에서 Northwind 데이터베이스에 대한 연결을 만듭니다.  
  
-   데이터베이스의 테이블을 기반으로 데이터 집합에 TableAdapter가 있는 테이블을 만듭니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   Northwind 샘플 데이터베이스\(SQL Server 또는 Access 버전\)에 대한 액세스.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## 새로운 Windows 응용 프로그램 프로젝트 만들기  
  
#### 새로운 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  **프로젝트 형식** 창에서 프로그래밍 언어를 선택합니다.  
  
3.  **템플릿** 창에서 **Windows 응용 프로그램**을 클릭합니다.  
  
4.  프로젝트의 이름을 `DatasetDesignerWalkthrough`로 지정한 다음 **확인**을 클릭합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 **솔루션 탐색기**에 프로젝트가 추가되고 디자이너에 새 폼이 표시됩니다.  
  
## 응용 프로그램에 새 데이터 집합 추가  
  
#### 프로젝트에 새 데이터 집합 항목을 추가하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
     **새 항목 추가** 대화 상자가 나타납니다.  
  
2.  **새 항목 추가** 대화 상자의 **템플릿** 상자에서 **데이터 집합**을 클릭합니다.  
  
3.  데이터 집합의 이름을 `NorthwindDataset`로 지정한 다음 **추가**를 클릭합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 **NorthwindDataset.xsd**라는 이름의 파일이 프로젝트에 추가되고 이 파일이 **데이터 집합 디자이너**에 열립니다.  
  
## 서버 탐색기에서 데이터 연결 만들기  
  
#### Northwind 데이터베이스에 대한 연결을 만들려면  
  
1.  **보기** 메뉴에서 **서버 탐색기**를 클릭합니다.  
  
2.  **서버 탐색기**에서 **데이터베이스에 연결** 단추를 클릭합니다.  
  
3.  Northwind 샘플 데이터베이스에 대한 연결을 만듭니다.  
  
    > [!NOTE]
    >  이 연습에서는 SQL Server 또는 Access 버전의 Northwind에 연결할 수 있습니다.  
  
## 데이터 집합에 테이블 만들기  
 이 단원에서는 데이터 집합에 테이블을 추가하는 방법을 설명합니다.  
  
#### Customers 테이블을 만들려면  
  
1.  **서버 탐색기**에서 만든 데이터 연결을 확장한 다음 **테이블** 노드를 확장합니다.  
  
2.  **Customers** 테이블을 **서버 탐색기**에서 **데이터 집합 디자이너**로 끌어서 놓습니다.  
  
     데이터 집합에 **Customers** 데이터 테이블 및 **CustomersTableAdapter**가 추가됩니다.  
  
#### Orders 테이블을 만들려면  
  
-   **Orders** 테이블을 **서버 탐색기**에서 **데이터 집합 디자이너**로 끌어서 놓습니다.  
  
     **Orders** 데이터 테이블, **OrdersTableAdapter** 및 **Customers**와 **Orders** 테이블 간의 데이터 연결이 데이터 집합에 추가됩니다.  
  
#### OrderDetails 테이블을 만들려면  
  
-   **Order Details** 테이블을 **서버 탐색기**에서 **데이터 집합 디자이너**로 끌어서 놓습니다.  
  
     **Order Details** 데이터 테이블, **Order DetailsTableAdapter** 및 **Orders**와 **Order Details** 테이블 간의 데이터 연결이 데이터 집합에 추가됩니다.  
  
## 다음 단계  
  
### 응용 프로그램에 기능을 추가하려면  
  
-   데이터 집합을 저장합니다.  
  
-   **데이터 소스** 창에서 항목을 선택하여 폼으로 끌어 옵니다.  자세한 내용은 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)을 참조하십시오.  
  
-   TableAdapter에 쿼리를 더 추가합니다.  자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)을 참조하십시오.  
  
-   데이터 집합에 있는 데이터 테이블의 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트에 유효성 검사 논리를 추가합니다.  자세한 내용은 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
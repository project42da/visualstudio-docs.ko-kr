---
title: "연습: Windows Form에 데이터 표시 | Microsoft Docs"
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
  - "데이터[Visual Studio], Windows Forms에 표시"
  - "데이터 바인딩, Windows Forms"
  - "폼에 데이터 표시, 연습"
  - "폼, 데이터 표시"
  - "Windows 응용 프로그램, 데이터 표시"
  - "Windows Forms, 데이터 표시"
ms.assetid: f6e08c2c-c792-43de-adf3-3e52c0100225
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 연습: Windows Form에 데이터 표시
응용 프로그램 개발에서 가장 일반적인 시나리오 중 하나는 Windows 기반 응용 프로그램의 폼에 데이터를 표시하는 것입니다.  [데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 폼으로 항목을 끌어 폼에 데이터를 표시할 수 있습니다.  이 연습에서는 여러 개별 컨트롤에서 단일 테이블의 데이터를 표시하는 단순 폼을 만듭니다.  이 예에서는 Northwind 샘플 데이터베이스의 `Customers` 테이블을 사용합니다.  
  
 이 연습에서 설명하는 작업은 다음과 같습니다.  
  
-   새 **Windows 응용 프로그램** 프로젝트를 만듭니다.  
  
-   [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 데이터 집합을 만들고 구성합니다.  
  
-   **데이터 소스** 창에서 항목을 끌어오는 경우 폼에 만들어질 컨트롤을 선택합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
-   **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## Windows 응용 프로그램 만들기  
 첫 번째 단계에서는 **Windows 응용 프로그램** 프로젝트를 만듭니다.  
  
#### 새 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  프로젝트 이름을 `DisplayingDataonaWindowsForm`으로 지정합니다.  
  
3.  **Windows 응용 프로그램**을 선택하고 **확인**을 클릭합니다.  자세한 내용은 [클라이언트 응용 프로그램](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md)을 참조하십시오.  
  
     **DisplayingDataonaWindowsForm** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## 데이터 소스 만들기  
 이 단계에서는 **데이터 소스 구성 마법사**를 사용하여 Northwind 샘플 데이터베이스의 `Customers` 테이블을 기반으로 하는 데이터 소스를 만듭니다.  연결을 만들려면 Northwind 샘플 데이터베이스에 액세스해야 합니다.  Northwind 샘플 데이터베이스를 설정하는 방법에 대한 자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)를 참조하세요.  
  
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
  
## 만들 컨트롤 설정  
 이 연습에서는 데이터를 **Details** 레이아웃에 배치하여 개별 컨트롤에서 데이터를 표시합니다.  데이터가 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시되는 기본 **Grid** 레이아웃을 사용할 수도 있습니다.  
  
#### 데이터 소스 창에서 항목에 대한 삭제 유형을 설정하려면  
  
1.  **데이터 소스** 창에서 **Customers** 노드를 확장합니다.  
  
2.  **Customers** 노드의 드롭다운 목록에서 **Details**를 선택하여**Customers** 테이블의 삭제 유형을 **Details**로 변경합니다.  자세한 내용은 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)을 참조하십시오.  
  
3.  **CustomerID** 노드의 컨트롤 목록에서 **Label**을 선택하여 **CustomerID** 열의 삭제 유형을 레이블로 변경합니다.  
  
## 폼 만들기  
 **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만듭니다.  
  
#### 폼에서 데이터 바인딩된 컨트롤을 만들려면  
  
-   주 **Customers** 노드를 **데이터 소스** 창에서 폼으로 끌어서 놓습니다.  
  
     설명 레이블이 있는 데이터 바인딩된 컨트롤이 레코드 탐색을 위한 도구 모음인 <xref:System.Windows.Forms.BindingNavigator>와 함께 폼에 나타납니다.  [NorthwindDataSet](../data-tools/dataset-tools-in-visual-studio.md), [CustomersTableAdapter](../data-tools/tableadapter-overview.md), <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>가 구성 요소 트레이에 나타납니다.  
  
## 응용 프로그램 테스트  
  
#### 응용 프로그램을 실행하려면  
  
-   F5 키를 누릅니다.  
  
-   <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 사용하여 레코드를 탐색합니다.  
  
## 다음 단계  
 응용 프로그램 요구 사항에 따라 데이터 바인딩된 Windows Form을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다.  이 연습에서 보완할 수 있는 사항은 다음과 같습니다.  
  
-   폼에 검색 기능을 추가합니다.  자세한 내용은 [방법: Windows Forms 응용 프로그램에 매개 변수가 있는 Query 추가](../Topic/How%20to:%20Add%20a%20Parameterized%20Query%20to%20a%20Windows%20Forms%20Application.md)을 참조하십시오.  
  
-   업데이트를 데이터베이스로 다시 보내는 기능을 추가합니다.  자세한 내용은 [연습: 데이터베이스에 데이터 저장\(단일 테이블\)](../Topic/Walkthrough:%20Saving%20Data%20to%20a%20Database%20\(Single%20Table\).md)을 참조하십시오.  
  
-   **데이터 소스** 창에서 **마법사로 데이터 집합 구성**을 선택하여 `Orders` 테이블을 데이터 집합에 추가합니다.  그런 후에 **Orders** 노드\(**Customers** 테이블 내의 **Fax** 열 아래에 있는 노드\)를 폼으로 끌어 관련 데이터를 표시하는 컨트롤을 추가할 수 있습니다.  자세한 내용은 [방법: Windows Forms 응용 프로그램에서 관련 데이터 표시](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)
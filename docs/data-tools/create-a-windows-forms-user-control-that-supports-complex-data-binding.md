---
title: "연습: 복합 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기 | Microsoft Docs"
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
  - "데이터 바인딩, 대규모"
  - "데이터 바인딩, 사용자 정의 컨트롤"
  - "사용자 정의 컨트롤[Visual Studio], 복합 데이터 바인딩"
ms.assetid: c8f29c2b-b49b-4618-88aa-33b6105880b5
caps.latest.revision: 13
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: 복합 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기
Windows 응용 프로그램에서 폼에 데이터를 표시할 때는 **도구 상자**에서 기존 컨트롤을 선택할 수도 있고, 표준 컨트롤에서는 제공되지 않는 기능이 응용 프로그램에 필요한 경우에는 사용자 지정 컨트롤을 작성할 수도 있습니다.  이 연습에서는 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>를 구현하는 컨트롤을 만드는 방법을 보여줍니다.  <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>를 구현하는 컨트롤은 데이터에 바인딩할 수 있는 `DataSource` 및 `DataMember` 속성을 포함합니다.  이러한 컨트롤은 <xref:System.Windows.Forms.DataGridView> 또는 <xref:System.Windows.Forms.ListBox>와 비슷합니다.  
  
 컨트롤 작성에 대한 자세한 내용은 [디자인할 때 Windows Forms 컨트롤 개발](../Topic/Developing%20Windows%20Forms%20Controls%20at%20Design%20Time.md)을 참조하세요.  
  
 데이터 바인딩 시나리오에 사용할 컨트롤을 작성할 때는 다음 데이터 바인딩 특성 중 하나를 구현해야 합니다.  
  
|데이터 바인딩 특성 사용법|  
|--------------------|  
|단일 데이터 열이나 속성을 표시하는 <xref:System.Windows.Forms.TextBox> 등의 단순 컨트롤에 대해 <xref:System.ComponentModel.DefaultBindingPropertyAttribute>를 구현합니다.  자세한 내용은 [연습: 단순 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)을 참조하십시오.|  
|데이터 목록 또는 테이블을 표시하는 <xref:System.Windows.Forms.DataGridView> 등의 컨트롤에 대해 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>를 구현합니다.  이 연습 페이지에서 해당 프로세스에 대해 설명합니다.|  
|데이터 목록 또는 테이블을 표시하는 동시에 단일 열이나 속성도 제공해야 하는 <xref:System.Windows.Forms.ComboBox> 등의 컨트롤에 대해 <xref:System.ComponentModel.LookupBindingPropertiesAttribute>를 구현합니다.  자세한 내용은 [연습: 조회 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)을 참조하십시오.|  
  
 이 연습에서는 테이블의 데이터 행을 표시하는 복합 컨트롤을 만듭니다.  이 예에서는 Northwind 샘플 데이터베이스의 `Customers` 테이블을 사용합니다.  복합 사용자 컨트롤은 사용자 지정 컨트롤의 <xref:System.Windows.Forms.DataGridView>에 Customers 테이블을 표시합니다.  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   새 **Windows 응용 프로그램**을 만듭니다.  
  
-   프로젝트에 새 **사용자 컨트롤**을 추가합니다.  
  
-   사용자 컨트롤을 시각적으로 디자인합니다.  
  
-   `ComplexBindingProperty` 특성을 구현합니다.  
  
-   [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 데이터 집합을 만듭니다.  
  
-   새 복합 컨트롤을 사용하도록 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)의 **Customers** 테이블을 설정합니다.  
  
-   새 컨트롤을 **데이터 소스 창**에서 **Form1**로 끌어 추가합니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 대한 액세스.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../data-tools/how-to-install-sample-databases.md)을 참조하십시오.  
  
## Windows 응용 프로그램 만들기  
 첫 번째 단계에서는 **Windows 응용 프로그램**을 만듭니다.  
  
#### 새 Windows 프로젝트를 만들려면  
  
1.  Visual Studio의 **파일** 메뉴에서 새 **프로젝트**를 만듭니다.  
  
2.  프로젝트 이름을 ComplexControlWalkthrough로 지정합니다.  
  
3.  **Windows 응용 프로그램**을 선택하고 **확인**을 클릭합니다.  자세한 내용은 [클라이언트 응용 프로그램](../Topic/Developing%20Client%20Applications%20with%20the%20.NET%20Framework.md)을 참조하십시오.  
  
     **ComplexControlWalkthrough** 프로젝트가 만들어져 **솔루션 탐색기**에 추가됩니다.  
  
## 프로젝트에 사용자 컨트롤 추가  
 이 연습에서는 **사용자 컨트롤**에서 데이터 바인딩 가능한 복합 컨트롤을 만들 것이므로 **사용자 컨트롤** 항목을 프로젝트에 추가해야 합니다.  
  
#### 프로젝트에 사용자 컨트롤을 추가하려면  
  
1.  **프로젝트** 메뉴에서 **사용자 컨트롤 추가**를 선택합니다.  
  
2.  **이름** 영역에 ComplexDataGridView를 입력하고 **추가**를 클릭합니다.  
  
     **ComplexDataGridView** 컨트롤이 **솔루션 탐색기**에 추가되고 디자이너에서 열립니다.  
  
## ComplexDataGridView 컨트롤 디자인  
 이 단계에서는 사용자 컨트롤에 <xref:System.Windows.Forms.DataGridView>를 추가합니다.  
  
#### ComplexDataGridView 컨트롤을 디자인하려면  
  
-   **도구 상자**에서 사용자 컨트롤의 디자인 화면으로 <xref:System.Windows.Forms.DataGridView>를 끌어 옵니다.  
  
## 필수 데이터 바인딩 특성 추가  
 데이터 바인딩을 지원하는 복합 컨트롤에 대해 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>를 구현할 수 있습니다.  
  
#### ComplexBindingProperties 특성을 구현하려면  
  
1.  **ComplexDataGridView** 컨트롤을 코드 보기로 전환합니다.  이렇게 하려면 **보기** 메뉴에서 **코드**를 선택합니다.  
  
2.  `ComplexDataGridView`의 코드를 다음 코드로 바꿉니다.  
  
     [!code-cs[VbRaddataDisplaying#4](../data-tools/codesnippet/CSharp/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.cs)]
     [!code-vb[VbRaddataDisplaying#4](../data-tools/codesnippet/VisualBasic/create-a-windows-forms-user-control-that-supports-complex-data-binding_1.vb)]  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.  
  
## 데이터베이스에서 데이터 소스 만들기  
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
  
8.  `Customers` 테이블을 선택하고 **마침**을 클릭합니다.  
  
     **NorthwindDataSet**가 프로젝트에 추가되고 `Customers` 테이블이 **데이터 소스** 창에 나타납니다.  
  
## ComplexDataGridView 컨트롤을 사용하도록 Customers 테이블 설정  
 **데이터 소스** 창 내에서 항목을 폼으로 끌기 전에 만들 컨트롤을 설정할 수 있습니다.  
  
#### ComplexDataGridView 컨트롤에 바인딩되도록 Customers 테이블을 설정하려면  
  
1.  디자이너에서 **Form1**을 엽니다.  
  
2.  **데이터 소스** 창에서 **Customers** 노드를 확장합니다.  
  
3.  **Customers** 노드에서 드롭다운 화살표를 클릭하고 **Customize**를 선택합니다.  
  
4.  **데이터 UI 사용자 지정 옵션** 대화 상자의 **연결된 컨트롤** 목록에서 **ComplexDataGridView**를 선택합니다.  
  
5.  `Customers` 테이블에서 드롭다운 화살표를 클릭하고 컨트롤 목록에서 **ComplexDataGridView**를 선택합니다.  
  
## 폼에 컨트롤 추가  
 **데이터 소스** 창에서 폼으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다.  
  
#### 폼에서 데이터 바인딩된 컨트롤을 만들려면  
  
-   **데이터 소스** 창의 주 **Customers** 노드를 폼으로 끌고 테이블의 데이터를 표시하는 데 **ComplexDataGridView** 컨트롤이 사용되는지 확인합니다.  
  
## 응용 프로그램 실행  
  
#### 응용 프로그램을 실행하려면  
  
-   F5 키를 눌러 응용 프로그램을 실행합니다.  
  
## 다음 단계  
 응용 프로그램 요구 사항에 따라 데이터 바인딩을 지원하는 컨트롤을 만든 후 몇 단계를 더 수행해야 할 수도 있습니다.  일반적으로 수행하는 몇 가지 단계는 다음과 같습니다.  
  
-   다른 응용 프로그램에서 다시 사용할 수 있도록 컨트롤 라이브러리에 사용자 지정 컨트롤을 배치합니다.  
  
-   조회 시나리오를 지원하는 컨트롤을 만듭니다.  자세한 내용은 [연습: 조회 데이터 바인딩을 지원하는 Windows Forms 사용자 정의 컨트롤 만들기](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)을 참조하십시오.  
  
## 참고 항목  
 [데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)   
 [Windows Forms 컨트롤](../Topic/Windows%20Forms%20Controls.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
---
title: "방법: TableAdapter의 기능 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
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
  - "데이터[Visual Studio], TableAdapter 확장"
  - "데이터[Visual Studio], TableAdapter"
  - "TableAdapter, 기능 추가"
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: TableAdapter의 기능 확장
TableAdapter의 partial 클래스 파일에 코드를 추가하여 TableAdapter의 기능을 확장할 수 있습니다.  
  
 TableAdapter를 정의하는 코드는 **데이터 집합 디자이너**에서 TableAdapter를 변경하거나 TableAdapter의 구성을 수정하는 마법사를 실행하는 동안 변경될 때 다시 생성됩니다.  TableAdapter를 다시 생성하는 동안 코드가 삭제되지 않도록 하려면 TableAdapter의 partial 클래스 파일에 코드를 추가합니다.  
  
 partial 클래스를 사용하면 특정 클래스의 코드를 여러 실제 파일에서 나눌 수 있습니다.  자세한 내용은 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial) 또는 [부분\(형식\)](/dotnet/csharp/language-reference/keywords/partial-type)을 참조하십시오.  
  
## 코드에서 TableAdapter 찾기  
 TableAdapter는 **데이터 집합 디자이너**를 사용하여 디자인되지만 생성되는 TableAdapter 클래스는 <xref:System.Data.DataSet>의 중첩 클래스로 생성되지 않고  TableAdapter는 TableAdapter의 연관 데이터 집합 이름을 따르는 네임스페이스에 있습니다.  예를 들어, 응용 프로그램에 `HRDataSet`이라는 데이터 집합이 있는 경우 TableAdapter는 `HRDataSetTableAdapters` 네임스페이스에 있습니다.  해당 명명 규칙은 *DatasetName* \+ `TableAdapters` 패턴을 따릅니다.  
  
 다음 예제에서는 `CustomersTableAdapter`라는 TableAdapter가 `NorthwindDataSet`이 있는 프로젝트에 있는 것으로 가정합니다.  
  
#### TableAdapter에 대한 partial 클래스를 만들려면  
  
1.  **프로젝트** 메뉴에서 **클래스 추가**를 선택하여 프로젝트에 새 클래스를 추가합니다.  
  
2.  `CustomersTableAdapterExtended` 클래스의 이름을 지정합니다.  
  
3.  **추가**를 클릭합니다.  
  
4.  코드를 프로젝트의 올바른 네임스페이스 및 partial 클래스 이름으로 바꿉니다.  예를 들면 다음과 같습니다.  
  
     [!code-cs[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]  
  
## 참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)   
 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)   
 [방법: 데이터 집합의 기능 확장](../Topic/How%20to:%20Extend%20the%20Functionality%20of%20a%20Dataset.md)   
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
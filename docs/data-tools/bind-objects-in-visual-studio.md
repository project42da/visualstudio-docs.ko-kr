---
title: "Visual Studio에서 개체 바인딩 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "바인딩, 개체"
  - "데이터[Visual Studio], 개체에 바인딩"
  - "데이터[Visual Studio], 개체 바인딩"
  - "개체 바인딩"
ms.assetid: ed743ce6-73af-45e5-a8ff-045eddaccc86
caps.latest.revision: 20
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual Studio에서 개체 바인딩
Visual Studio에서는 응용 프로그램의 데이터 소스로 사용자 지정 개체\(엔터티, 데이터 집합과 서비스 등의 다른 데이터 소스와 반대의 의미\)와 함께 사용할 수 있는 디자인 타임 도구를 제공합니다.  
  
## 개체 요구 사항  
 사용자 지정 개체를 Visual Studio의 데이터 디자인 도구와 함께 사용하려면 해당 개체에 하나 이상의 public 속성이 있어야 합니다.  
  
 일반적으로 사용자 지정 개체가 응용 프로그램의 데이터 소스로 작동하기 위해 특정 인터페이스, 생성자 또는 특성이 필요하지는 않습니다.  그러나 **데이터 소스** 창의 개체를 디자인 화면으로 끌어 데이터 바인딩된 컨트롤을 만들려는 경우 해당 개체가 <xref:System.ComponentModel.ITypedList> 또는 <xref:System.ComponentModel.IListSource> 인터페이스를 구현하지 않으면 이 개체에는 기본 생성자, 즉 매개 변수 없는 생성자가 있어야 합니다.  그렇지 않으면 Visual Studio에서 데이터 소스 개체를 인스턴스화할 수 없고, 사용자가 디자인 화면으로 항목을 끌어 올 때 오류가 표시됩니다.  
  
## 사용자 지정 개체를 데이터 소스로 사용하는 예  
 개체를 데이터 소스로 사용할 때 응용 프로그램 논리를 구현하는 방법은 매우 많지만, Visual Studio에서 생성된 [TableAdapter](../data-tools/tableadapter-overview.md) 개체를 사용하여 단순화할 수 있는 표준 작업이 몇 가지 있습니다.  이 페이지에서는 TableAdapter를 사용하여 이러한 표준 프로세스를 구현하는 방법을 설명합니다. 이 방법은 사용자 지정 개체를 만들기 위한 지침은 아닙니다.  예를 들어, 개체의 특정 구현이나 응용 프로그램의 논리에 관계없이 다음 표준 작업을 수행하게 됩니다.  
  
-   개체에 데이터 로드\(보통 데이터베이스로부터\)  
  
-   개체의 형식화된 컬렉션 만들기  
  
-   컬렉션에 개체 추가 및 컬렉션에서 개체 제거  
  
-   폼에서 사용자에게 개체 데이터 표시  
  
-   개체의 데이터 변경\/편집  
  
-   개체의 데이터를 다시 데이터베이스로 저장  
  
> [!NOTE]
>  사용자의 이해를 돕고 이 페이지의 예제에 대한 컨텍스트를 제공하기 위해 다음 연습을 완료하는 것이 좋습니다. [연습: 개체의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md) 이 연습에서는 이 도움말 페이지에 설명되어 있는 개체를 만듭니다.  
  
### 개체에 데이터 로드  
 이 예제에서는 TableAdapter를 사용하여 개체에 데이터를 로드합니다.  기본적으로 TableAdapter는 데이터베이스에서 데이터를 페치하고 데이터 테이블을 채우는 두 종류의 메서드로 만들어집니다.  
  
-   `TableAdapter.Fill` 메서드는 기존 데이터 테이블을 반환된 데이터로 채웁니다.  
  
-   `TableAdapter.GetData` 메서드는 데이터로 채워진 새 데이터 테이블을 반환합니다.  
  
 데이터가 있는 사용자 지정 개체를 로드하는 가장 쉬운 방법은 `TableAdapter.GetData` 메서드를 호출하고 반환된 데이터 테이블의 행 컬렉션을 순환 검색한 다음 각 개체를 각 행의 값으로 채우는 것입니다.  TableAdapter에 추가된 쿼리에 대해 채워진 데이터 테이블을 반환하는 `GetData` 메서드를 만들 수 있습니다.  
  
> [!NOTE]
>  Visual Studio는 TableAdapter 쿼리의 이름을 기본적으로 `Fill`과 `GetData`로 지정합니다. 그러나 이러한 이름은 임의의 유효한 메서드 이름으로 변경할 수 있습니다.  
  
 다음 예제에서는 데이터 테이블의 행을 순환 검색하고 개체를 데이터로 채우는 방법을 보여 줍니다.  
  
 자세한 코드 예제는 [연습: 개체의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md)을 참조하십시오.  
  
 [!code-cs[VbRaddataConnecting#4](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_1.cs)]
 [!code-vb[VbRaddataConnecting#4](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_1.vb)]  
  
### 개체의 형식화된 컬렉션 만들기  
 개체에 대해 컬렉션 클래스를 만들거나 [BindingSource 구성 요소](../Topic/BindingSource%20Component.md)에 자동으로 제공되는 형식화된 컬렉션을 사용할 수 있습니다.  
  
 개체에 대해 사용자 지정 컬렉션 클래스를 만드는 경우 <xref:System.ComponentModel.BindingList%601>에서 상속하는 것이 좋습니다.  이 일반적인 클래스는 컬렉션을 관리하는 기능뿐 아니라 Windows Forms의 데이터 바인딩 인프라에 알림을 보내는 이벤트를 발생시키는 기능을 제공합니다.  
  
 <xref:System.Windows.Forms.BindingSource>의 자동으로 생성된 컬렉션은 해당 형식화된 컬렉션에 <xref:System.ComponentModel.BindingList%601>을 사용합니다.  응용 프로그램에 추가 기능이 필요하지 않는 경우 <xref:System.Windows.Forms.BindingSource> 내에서 컬렉션을 유지할 수 있습니다.  자세한 내용은 <xref:System.Windows.Forms.BindingSource> 클래스의 <xref:System.Windows.Forms.BindingSource.List%2A> 속성을 참조하십시오.  
  
> [!NOTE]
>  컬렉션에 <xref:System.ComponentModel.BindingList%601>의 기본 구현으로 제공되지 않는 기능이 필요한 경우 사용자 지정 컬렉션을 만들어야 필요한 경우 클래스에 추가할 수 있습니다.  
  
 다음 코드에서는 `Order` 개체의 강력한 형식의 컬렉션에 대한 클래스를 만드는 방법을 보여 줍니다.  
  
 [!code-cs[VbRaddataConnecting#8](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_2.cs)]
 [!code-vb[VbRaddataConnecting#8](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_2.vb)]  
  
### 컬렉션에 개체 추가  
 사용자 지정 컬렉션 클래스 또는 <xref:System.Windows.Forms.BindingSource>의 `Add` 메서드를 호출하여 컬렉션에 개체를 추가합니다.  
  
 <xref:System.Windows.Forms.BindingSource>를 사용하여 컬렉션에 추가하는 방법의 예제를 보려면 [연습: 개체의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md)의 `LoadCustomers` 메서드를 참조하십시오.  
  
 사용자 지정 컬렉션에 개체를 추가하는 방법의 예제를 보려면 [연습: 개체의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md)의 `LoadOrders` 메서드를 참조하십시오.  
  
> [!NOTE]
>  `Add` 메서드는 <xref:System.ComponentModel.BindingList%601>에서 상속할 때 사용자 지정 컬렉션에 자동으로 제공됩니다.  
  
 다음 코드에서는 <xref:System.Windows.Forms.BindingSource>의 형식화된 컬렉션에 개체를 추가하는 방법을 보여 줍니다.  
  
 [!code-cs[VbRaddataConnecting#5](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_3.cs)]
 [!code-vb[VbRaddataConnecting#5](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_3.vb)]  
  
 다음 코드에서는 <xref:System.ComponentModel.BindingList%601>에서 상속한 형식화된 컬렉션에 개체를 추가하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 예제에서 `Orders` 컬렉션은 `Customer` 개체의 속성입니다.  
  
 [!code-cs[VbRaddataConnecting#6](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_4.cs)]
 [!code-vb[VbRaddataConnecting#6](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_4.vb)]  
  
### 컬렉션에서 개체 제거  
 사용자 지정 컬렉션 클래스 또는 <xref:System.Windows.Forms.BindingSource>의 `Remove` 또는 `RemoveAt` 메서드를 호출하여 컬렉션에서 개체를 제거합니다.  
  
> [!NOTE]
>  `Remove` 및 `RemoveAt` 메서드는 <xref:System.ComponentModel.BindingList%601>에서 상속할 때 사용자 지정 컬렉션에 자동으로 제공됩니다.  
  
 다음 코드에서는 <xref:System.Windows.Forms.BindingSource.RemoveAt%2A> 메서드가 있는 <xref:System.Windows.Forms.BindingSource>의 형식화된 컬렉션에서 개체를 찾고 제거하는 방법을 보여 줍니다.  
  
 [!code-cs[VbRaddataConnecting#7](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_5.cs)]
 [!code-vb[VbRaddataConnecting#7](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_5.vb)]  
  
### 사용자에게 개체 데이터 표시  
 개체의 데이터를 사용자에게 표시하려면 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 사용하여 개체 데이터 소스를 만든 다음 **데이터 소스** 창에서 전체 개체 또는 개별 속성을 폼으로 끌어 놓습니다.  
  
 개체 데이터 소스 만들기에 대한 자세한 내용은 [방법: 개체의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20Objects.md)을 참조하십시오.  
  
 Windows Forms에서 개체의 데이터 표시에 대한 자세한 내용은 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)를 참조하십시오.  
  
### 개체에서 데이터 수정  
 Windows Forms 컨트롤에 데이터 바인딩된 사용자 지정 개체의 데이터를 편집하려면 바인딩된 컨트롤\(또는 해당 개체의 속성에서 직접\)에서 데이터를 간단히 편집하십시오.  데이터 바인딩 아키텍처가 개체의 데이터를 업데이트합니다.  
  
 응용 프로그램에서 변경 내용을 추적하고 제안된 변경 내용을 해당 원래 값으로 롤백해야 하는 경우 개체 모형에서 이 기능을 구현해야 합니다.  데이터 테이블에서 제안된 변경 내용을 추적하는 방법에 대한 예제를 보려면 <xref:System.Data.DataRowState>, <xref:System.Data.DataSet.HasChanges%2A> 및 <xref:System.Data.DataTable.GetChanges%2A>를 참조하십시오.  
  
### 개체의 데이터를 다시 데이터베이스로 저장  
 개체에서 TableAdapter의 DBDirect 메서드로 값을 전달하여 데이터를 다시 데이터베이스로 저장합니다.  
  
 Visual Studio에서는 데이터베이스에 대해 직접 실행할 수 있는 DBDirect 메서드를 만듭니다.  이러한 메서드에는 DataSet 또는 DataTable 개체가 필요하지 않습니다.  
  
|TableAdapter DBDirect 메서드|설명|  
|-------------------------------|--------|  
|`TableAdapter.Insert`|데이터베이스에 새 레코드를 추가하여 개별 열 값을 메서드 매개 변수로 전달할 수 있습니다.|  
|`TableAdapter.Update`|데이터베이스의 기존 레코드를 업데이트합니다.  Update 메서드는 원래 열 값과 새 열 값을 메서드 매개 변수로 사용합니다.  원래 값은 원래 레코드를 찾는 데 사용되고 새 값은 해당 레코드를 업데이트하는 데 사용됩니다.<br /><br /> 또한 `TableAdapter.Update` 메서드를 사용하면 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, <xref:System.Data.DataRow> 또는 <xref:System.Data.DataRow>의 배열을 메서드 매개 변수로 사용하여 데이터 집합의 변경 내용을 다시 데이터베이스에 적용할 수도 있습니다.|  
|`TableAdapter.Delete`|매서드 매개 변수로 전달된 원래 열 값을 기반으로 데이터베이스에서 기존 레코드를 삭제합니다.|  
  
 개체 컬렉션의 데이터를 저장하려면 개체 컬렉션을 순환 검색하고\(예: for\-next 루프 사용\) TableAdapter의 DBDirect 메서드를 사용하여 각 개체의 값을 데이터베이스로 보냅니다.  
  
 다음 예제에서는 `TableAdapter.Insert` DBDirect 메서드를 사용하여 새 고객을 데이터베이스에 직접 추가하는 방법을 보여 줍니다.  
  
 [!code-cs[VbRaddataSaving#23](../data-tools/codesnippet/CSharp/bind-objects-in-visual-studio_6.cs)]
 [!code-vb[VbRaddataSaving#23](../data-tools/codesnippet/VisualBasic/bind-objects-in-visual-studio_6.vb)]  
  
## 참고 항목  
 [방법: 개체의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20Objects.md)   
 [연습: 개체의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20Objects%20\(Windows%20Forms\).md)   
 [방법: 개체에서 데이터베이스로 데이터 저장](../data-tools/save-data-from-an-object-to-a-database.md)   
 [방법: TableAdapter를 사용하여 데이터베이스에 직접 액세스](../data-tools/directly-access-the-database-with-a-tableadapter.md)   
 [연습: TableAdapter DBDirect 메서드를 사용하여 데이터 저장](../data-tools/save-data-with-the-tableadapter-dbdirect-methods.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [TableAdapter](../Topic/TableAdapters.md)   
 [데이터 저장](../data-tools/saving-data.md)
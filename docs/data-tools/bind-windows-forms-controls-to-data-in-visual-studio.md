---
title: "Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩 | Microsoft Docs"
ms.custom: 
ms.date: 11/03/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], data sources
- Windows Forms, data binding
- Windows Forms, displaying data
- displaying data on forms
- forms, displaying data
- data sources, displaying data
- displaying data, Windows Forms
- data [Windows Forms], displaying
ms.assetid: 243338ef-41af-4cc5-aff7-1e830236f0ec
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 5936edd6096bd708dda1b03f60f94cea3d6c1e5b
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="bind-windows-forms-controls-to-data-in-visual-studio"></a>Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩
Windows Forms에 데이터를 바인딩하여 응용 프로그램의 사용자에 게 데이터를 표시할 수 있습니다. 이러한 데이터 바인딩된 컨트롤을 만들려면에서 항목을 이동할 수는 **데이터 소스** Visual Studio에서 Windows Forms 디자이너 창.
  
![데이터 원본으로 작업을 끌어](../data-tools/media/raddata-data-source-drag-operation.png "raddata 데이터 소스 끌기 작업")

항목을 끌어 오기 전에 컨트롤에 바인딩할의 형식을 설정할 수 있습니다. 자체 또는 개별 열 테이블을 선택 하는지 여부에 따라 다른 값이 표시 됩니다.  사용자 지정 값을 설정할 수 있습니다. 테이블의 경우 "Details"는 각 열을 별도 컨트롤에 바인딩되어 있음을 의미 합니다.  

![DataGridView에 데이터 소스를 바인딩](../data-tools/media/raddata-bind-data-source-to-datagridview.png "raddata DataGridView에 데이터 원본 바인드")  
  
## <a name="bindingsource-and-bindingnavigator-controls"></a>BindingSource와 BindingNavigator 컨트롤
<xref:System.Windows.Forms.BindingSource> 구성 요소는 두가지 용도로 사용됩니다. 첫째, 데이터에 컨트롤에 바인딩할 때 추상화 계층을 제공 합니다. 폼에서 컨트롤에 바인딩된는 <xref:System.Windows.Forms.BindingSource> 데이터 원본에 직접 대신 구성 요소입니다. 둘째, 개체의 컬렉션을 관리할 수 있습니다. 에 형식을 추가 하면는 <xref:System.Windows.Forms.BindingSource> 해당 형식의 목록을 만듭니다.  
  
에 대 한 자세한 내용은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 참조 하세요.  
  
-   [BindingSource 구성 요소](/dotnet/framework/winforms/controls/bindingsource-component)  
  
-   [BindingSource 구성 요소 개요](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
-   [BindingSource 구성 요소 아키텍처](/dotnet/framework/winforms/controls/bindingsource-component-architecture)  
  
[BindingNavigator 컨트롤](/dotnet/framework/winforms/controls/bindingnavigator-control-windows-forms) Windows 응용 프로그램에 의해 표시 되는 데이터를 탐색 하기 위한 사용자 인터페이스를 제공 합니다.

## <a name="bind-to-data-in-a-datagridview-control"></a>DataGridView 컨트롤의 데이터에 바인딩  
에 대 한는 [DataGridView 컨트롤](/dotnet/framework/winforms/controls/datagridview-control-overview-windows-forms), 전체 테이블이 단일 해당 컨트롤에 바인딩됩니다. 레코드 탐색에 도구 스트립 DataGridView를 폼으로 끌어서 놓으면 (<xref:System.Windows.Forms.BindingNavigator>)도 나타납니다. A [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다. 다음 그림에서 TableAdapterManager Customers 테이블의 Orders 테이블에는 관계 때문에 추가 됩니다. 이러한 변수는 선언 된 모든 자동 생성 된 코드에 폼 클래스에서 private 멤버로. DataGridView를 채우기 위한 자동 생성 된 코드는 form_load 이벤트 처리기에 있습니다. 데이터베이스를 업데이트 하 여 데이터를 저장 하는 것에 대 한 코드는 BindingNavigator에 대 한 저장 이벤트 처리기에 있습니다. 이동 하거나 필요에 따라이 코드를 수정할 수 있습니다.  
  
![BindingNavigator이 있는 GridView](../data-tools/media/raddata-gridview-with-bindingnavigator.png "raddata BindingNavigator이 있는 GridView")  
  
각각의 오른쪽 위 모서리에 있는 스마트 태그를 클릭 하 여 DataGridView 및 BindingNavigator의 동작을 사용자 지정할 수 있습니다.  
  
![DataGridView 및 탐색기 바인딩 스마트 태그](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png "raddata DataGridView 및 탐색기 바인딩 스마트 태그")  
  
컨트롤은 응용 프로그램 필요 없는 경우 내에서 사용할 수는 **데이터 소스** 창 컨트롤을 추가할 수 있습니다. 자세한 내용은 참조 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.  
  
항목을 끌 수도 있습니다는 **데이터 소스** 창으로 데이터에 컨트롤을 바인딩할 수 있는 폼에 이미 있는 컨트롤입니다. 이미 데이터에 바인딩되는 컨트롤에 가장 최근에 끌어 항목에 바인딩됩니다. 유효한 놓기 대상 되도록 컨트롤 수 있어야에서으로 끌어 온 항목의 기본 데이터 형식 표시는 **데이터 소스** 창. 예를 들어, 유효 하지 않은의 데이터 형식이 지정 된 항목을 끌기 <xref:System.DateTime> 에 <xref:System.Windows.Forms.CheckBox>때문에 <xref:System.Windows.Forms.CheckBox> 가 날짜를 표시할 수 없습니다.  
  
## <a name="bind-to-data-in-individual-controls"></a>개별 컨트롤에 데이터에 바인딩  
"자세히" 데이터 소스에 바인딩하는 경우 데이터 집합의 각 열은 별도 컨트롤에 바인딩됩니다.  
  
![세부 정보를 데이터 소스를 바인딩할](../data-tools/media/raddata-bind-data-source-to-details.png "raddata 세부 정보를 데이터 원본 바인드")  
  
> [!IMPORTANT]
> 앞의 그림에서를 Orders 테이블에서가 아니라 Customers 테이블의 주문 속성에서 끕니다. Customer.Orders 속성에 바인딩하여 DataGridView에서 수행 하는 탐색 명령 세부 정보 컨트롤에 즉시 반영 됩니다. Orders 테이블에서 끌어 놓은 경우 컨트롤은 데이터 집합에 바인딩될 여전히 있지만 하지 DataGridView와은 하지 동기화 합니다.  
  
다음 그림에서는 기본 "Details" Customers 테이블에 주문 속성이 바인딩된 후 폼에 추가 된 데이터 바인딩 컨트롤의 **데이터 소스** 창.  
  
![Orders 테이블 세부 정보에 바인딩된](../data-tools/media/raddata-orders-table-bound-to-details.png "raddata Orders 테이블 세부 정보에 연결")  
  
각 컨트롤에 있는 스마트 태그는 또한 note 합니다. 이 태그에만 해당 컨트롤에 적용 되는 사용자 지정 수 있습니다.
  
## <a name="see-also"></a>참고 항목
[Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)  
[Windows Forms (.NET Framework)의 데이터 바인딩](/dotnet/framework/winforms/windows-forms-data-binding)
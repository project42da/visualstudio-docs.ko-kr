---
redirect_url: /visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio
ms.openlocfilehash: 5ba8ada294275a99aab27ff9c249d6c3d8e17da3
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
제목: "에서 데이터 바인딩 Windows Forms 컨트롤 | Microsoft Docs "ms.custom:" "ms.date:" 11/04/2016 "ms.reviewer:" "ms.suite:" "ms.tgt_pltfrm:" "ms.topic: helpviewer_keywords" 문서": 
  - "Windows Forms 컨트롤 데이터를 표시"
  - "Windows Forms에서 데이터를 표시 합니다."
  - "데이터 원본", 표시
  - "데이터 [Windows Forms], 표시" ms.assetid: 0163a34a-38cb-40b9-8f38-3058a90caf21 caps.latest.revision: 28 작성자: "gewarren" ms.author: "gewarren" 관리자: ghogen ms.technology: "vs 데이터 도구"
---
# <a name="bind-windows-forms-controls-to-data"></a>데이터에 Windows Forms 컨트롤 바인딩
개체를 끌어 데이터 소스 컨트롤에 바인딩할 수 있습니다는 **데이터 소스** 창에서 Windows Form으로 사용 하거나 폼에서 기존 컨트롤로 합니다. 항목을 끌어 오기 전에 컨트롤에 바인딩할의 형식을 설정할 수 있습니다. 자체 또는 개별 열 테이블을 선택 하는지 여부에 따라 다른 값이 표시 됩니다.  사용자 지정 값을 설정할 수 있습니다. 테이블의 경우 "Details"는 각 열을 별도 컨트롤에 바인딩되어 있음을 의미 합니다.  

![DataGridView에 데이터 소스를 바인딩](../data-tools/media/raddata-bind-data-source-to-datagridview.png "raddata DataGridView에 데이터 원본 바인드")  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="bind-to--data-in-a-datagridview-control"></a>DataGridView 컨트롤의 데이터에 바인딩  
을 DataGridView에 대 한 전체 테이블이 단일 해당 컨트롤에 바인딩됩니다. 레코드 탐색에 도구 스트립 DataGridView를 폼으로 끌어서 놓으면 (<xref:System.Windows.Forms.BindingNavigator>)도 나타납니다. A [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, 및 <xref:System.Windows.Forms.BindingNavigator> 구성 요소 트레이에 나타납니다. 다음 그림에서 TableAdapterManager Customers 테이블의 Orders 테이블에는 관계 때문에 추가 됩니다. 이러한 변수는 선언 된 모든 자동 생성 된 코드에 폼 클래스에서 private 멤버로. DataGridView를 채우기 위한 자동 생성 된 코드는 form_load 이벤트 처리기에 있습니다. 데이터베이스를 업데이트 하 여 데이터를 저장 하는 것에 대 한 코드는 BindingNavigator에 대 한 저장 이벤트 처리기에 있습니다. 이동 하거나 필요에 따라이 코드를 수정할 수 있습니다.  
  
 ![BindingNavigator이 있는 GridView](../data-tools/media/raddata-gridview-with-bindingnavigator.png "raddata BindingNavigator이 있는 GridView")  
  
 각각의 오른쪽 위 모서리에 있는 스마트 태그를 클릭 하 여 DataGridView 및 BindingNavigator의 동작을 사용자 지정할 수 있습니다.  
  
 ![DataGridView 및 탐색기 바인딩 스마트 태그](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png "raddata DataGridView 및 탐색기 바인딩 스마트 태그")  
  
 컨트롤은 응용 프로그램 필요 없는 경우 내에서 사용할 수는 **데이터 소스** 창 컨트롤을 추가할 수 있습니다. 자세한 내용은 참조 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.  
  
 항목을 끌 수도 있습니다는 **데이터 소스** 창으로 데이터에 컨트롤을 바인딩할 수 있는 폼에 이미 있는 컨트롤입니다. 이미 데이터에 바인딩되는 컨트롤에 가장 최근에 끌어 항목에 바인딩됩니다. 유효한 놓기 대상 되도록 컨트롤 수 있어야에서으로 끌어 온 항목의 기본 데이터 형식 표시는 **데이터 소스** 창. 예를 들어, 유효 하지 않은의 데이터 형식이 지정 된 항목을 끌기 <xref:System.DateTime> 에 <xref:System.Windows.Forms.CheckBox>때문에 <xref:System.Windows.Forms.CheckBox> 가 날짜를 표시할 수 없습니다.  
  
## <a name="bind-to--data-in-individual-controls"></a>개별 컨트롤에 데이터에 바인딩  
 "자세히" 데이터 소스에 바인딩하는 경우 데이터 집합의 각 열은 별도 컨트롤에 바인딩됩니다.  
  
 ![세부 정보를 데이터 소스를 바인딩할](../data-tools/media/raddata-bind-data-source-to-details.png "raddata 세부 정보를 데이터 원본 바인드")  
  
> [!IMPORTANT]
>  앞의 그림에서를 Orders 테이블에서가 아니라 Customers 테이블의 주문 속성에서 끕니다. Customer.Orders 속성에 바인딩하여 DataGridView에서 수행 하는 탐색 명령 세부 정보 컨트롤에 즉시 반영 됩니다. Orders 테이블에서 끌어 놓은 경우 컨트롤은 데이터 집합에 바인딩될 여전히 있지만 하지 DataGridView와은 하지 동기화 합니다.  
  
 다음 그림에서는 기본 "Details" Customers 테이블에 주문 속성이 바인딩된 후 폼에 추가 된 데이터 바인딩 컨트롤의 **데이터 소스** 창.  
  
 ![Orders 테이블 세부 정보에 바인딩된](../data-tools/media/raddata-orders-table-bound-to-details.png "raddata Orders 테이블 세부 정보에 연결")  
  
 각 컨트롤에 있는 스마트 태그는 또한 note 합니다. 이 태그에만 해당 컨트롤에 적용 되는 사용자 지정 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
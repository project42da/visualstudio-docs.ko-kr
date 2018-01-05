---
title: "WPF 응용 프로그램에서 조회 테이블 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [WPF], displaying
- WPF, data binding in Visual Studio
- WPF data binding [Visual Studio]
- displaying data, WPF
- WPF [WPF], data
- WPF Designer, data binding
- data binding, WPF
ms.assetid: 56a1fbff-c7e8-4187-a1c1-ffd17024bc1b
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 4b403d3bbe2e42ee74af7a2f7babe8b2700dd0d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="create-lookup-tables-in-wpf-applications"></a>WPF 응용 프로그램에서 조회 테이블 만들기
용어 *조회 테이블* (라고도 *조회 바인딩*) 다른 테이블의 외래 키 필드의 값에 따라 하나 이상의 데이터 테이블의에서 정보를 표시 하는 컨트롤에 설명 합니다. 부모 테이블의 기본 노드 드래그 하 여 조회 테이블을 만들 수도 있고 개체는 **데이터 소스** 창으로 열 이나 속성 관련된 자식 테이블에 이미 바인딩되어 있는 컨트롤입니다.  
  
예를 들어 테이블이 있다고 가정할 `Orders` 판매 데이터베이스에서 합니다. 각 레코드는 `Orders` 테이블에는 `CustomerID` 는 주문을 한 고객을 나타내는입니다. `CustomerID` 에서 고객 레코드를 가리키는 외래 키의 `Customers` 테이블입니다. 주문 목록을 표시 하는 경우는 `Orders` 아닌 실제 고객 이름을 표시 하려는 테이블을는 `CustomerID`합니다. 고객 이름은 이므로 `Customers` 고객 이름을 표시 하는 조회 테이블을 만들어야 할 테이블입니다. 조회 테이블 사용에서 `CustomerID` 값에 `Orders` 관계를 탐색 하 기록 하 고 고객 이름을 반환 합니다.  
  
## <a name="to-create-a-lookup-table"></a>조회 테이블을 만들려면  
  
1.  다음과 같은 유형의 관련된 데이터와 데이터 원본 중 하나를 프로젝트에 추가 합니다.  
  
    -   데이터 집합 또는 엔터티 데이터 모델입니다. 
  
    -   WCF 데이터 서비스를 WCF 서비스 또는 웹 서비스입니다. 자세한 내용은 참조 [하는 방법: 데이터 서비스에 연결할](../data-tools/how-to-connect-to-data-in-a-service.md)합니다.  
  
    -   개체입니다. 자세한 내용은 참조 [Visual Studio에서 개체를 바인딩할](bind-objects-in-visual-studio.md)합니다.  
  
    > [!NOTE]
    >  조회 테이블을 만들 수 있습니다, 전에 프로젝트에 대 한 데이터 원본으로 두 개의 관련된 테이블 나 개체가 존재 해야 합니다.  
  
2.  열기는 **WPF 디자이너**, 디자이너에 컨테이너의 항목에 대 한 유효한 놓기 대상에 포함 되어 있는지 확인 하 고는 **데이터 소스** 창.  
  
     유효한 놓기 대상에 대 한 자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤을 바인딩하는 WPF](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)합니다.  
  
3.  에 **데이터** 메뉴를 클릭 **데이터 소스 표시** 열려는 **데이터 소스** 창.  
  
4.  노드를 확장 하 고는 **데이터 소스** 부모 테이블 또는 개체와 관련된 자식 테이블 또는 개체를 볼 수 있습니다 될 때까지 창.  
  
    > [!NOTE]
    >  관련된 자식 테이블 또는 개체는 부모 테이블이 나 개체에서 확장 가능한 자식 노드로 표시 되는 노드입니다.  
  
5.  자식 노드에 대 한 드롭다운 메뉴를 클릭 하 고 선택 **세부 정보**합니다.  
  
6.  자식 노드를 확장 합니다.  
  
7.  자식 노드 아래에서 자식 테이블과 부모 데이터를 연결 하는 항목에 대 한 드롭다운 메뉴를 클릭 합니다. (이 앞의 예제에는 **CustomerID** 노드.) 조회 바인딩을 지 원하는 컨트롤의 다음 유형 중 하나를 선택 합니다.  
  
    -   **ComboBox**  
  
    -   **ListBox**  
  
    -   **ListView**  
  
        > [!NOTE]
        >  경우는 **ListBox** 또는 **ListView** 컨트롤이 없으면 목록에 목록에 이러한 컨트롤을 추가할 수 있습니다. 자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.  
  
    -   파생 된 모든 사용자 지정 컨트롤 <xref:System.Windows.Controls.Primitives.Selector>합니다.  
  
        > [!NOTE]
        >  항목에 대 한 사용자 지정 컨트롤의 컨트롤 목록에 추가 하는 방법에 대 한 정보를 선택할 수에 대 한는 **데이터 원본** 창 참조 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.  
  
8.  자식 노드를 끌어는 **데이터 소스** 창으로 WPF designer의 컨테이너입니다. (자식 노드는 앞의 예제는 **Orders** 노드.)  
  
     Visual Studio의 각 끌면 항목에 대 한 새 데이터 바인딩된 컨트롤을 만듭니다는 XAML을 생성 합니다. XAML도 새 추가 <xref:System.Windows.Data.CollectionViewSource> 자식 테이블이 나 놓기 대상의 리소스에는 개체에 대 한 합니다. 일부 데이터 원본에 대 한 Visual Studio 테이블 또는 개체 데이터를 로드 하는 코드를 생성 합니다. 자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤을 바인딩하는 WPF](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)합니다.  
  
9. 부모 노드를 끌어는 **데이터 소스** 앞에서 만든 조회 바인딩 컨트롤로 창. (부모 노드는 앞의 예제에는 **고객** 노드).  
  
     Visual Studio 조회 바인딩을 구성 하는 컨트롤에서 일부 속성을 설정 합니다. 다음 표에서 Visual Studio를 수정 하는 속성을 나열 합니다. 필요에 따라 변경할 수 있습니다 또는 XAML에서 이러한 속성은 **속성** 창.  
  
    |속성|설정 설명|  
    |--------------|----------------------------|  
    |<xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>|이 속성에는 컬렉션 또는 컨트롤에 표시 되는 데이터를 가져오는 데 사용 되는 바인딩을 지정 합니다. 이 속성을 설정 하는 visual Studio는 <xref:System.Windows.Data.CollectionViewSource> 컨트롤을 끌어 부모 데이터에 대 한 합니다.|  
    |<xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A>|이 속성은 컨트롤에 표시 되는 데이터 항목의 경로 지정 합니다. Visual Studio를 사용 하면 첫 번째 열 또는 부모 데이터에서 속성에이 속성을 설정 하는 문자열 데이터 형식이 지정 된 기본 키 다음 합니다.<br /><br /> 부모 데이터에 다른 열 이나 속성을 표시 하려는 경우이 속성을 다른 속성의 경로를 변경 합니다.|  
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>|Visual Studio 디자이너에 끌어 자식 데이터의 열 또는 변수에이 속성에 바인딩합니다. 부모 데이터에 외래 키입니다.|  
    |<xref:System.Windows.Controls.Primitives.Selector.SelectedValuePath%2A>|Visual Studio 열의 경로 또는 영역을 부모 데이터 외래 키가 자식 데이터의 속성에이 속성을 설정 합니다.|  
  
## <a name="see-also"></a>참고 항목
[Visual Studio에서 데이터에에서 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)   
[WPF 응용 프로그램에서 관련된 데이터 표시](../data-tools/display-related-data-in-wpf-applications.md)   
[연습: WPF 응용 프로그램에서 관련 데이터 표시](../data-tools/display-related-data-in-wpf-applications.md)
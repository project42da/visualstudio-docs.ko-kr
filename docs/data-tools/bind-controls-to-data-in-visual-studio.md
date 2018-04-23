---
title: Visual Studio에서 데이터에 컨트롤 바인딩
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data, displaying
- data sources, displaying data
- Data Sources window
- dislaying data
ms.assetid: be8b6623-86a6-493e-ab7a-050de4661fd6
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: acb050ebdbbce84eb47e27883c55117a83ddb0c2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="bind-controls-to-data-in-visual-studio"></a>Visual Studio에서 데이터에 컨트롤 바인딩
데이터를 컨트롤에 바인딩하여 응용 프로그램 사용자에게 데이터를 표시할 수 있습니다. 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다는 **데이터 소스** 창 디자인 화면 또는 Visual Studio에서 화면에 컨트롤에 있습니다.

 이 항목에서는 데이터 바인딩된 컨트롤을 만드는 데 사용할 수 있는 데이터 소스에 대해 설명합니다. 또한 데이터 바인딩과 관련된 일반적인 작업에 대해서도 설명합니다. 데이터 바인딩된 컨트롤을 만드는 방법에 대 한 보다 구체적인 세부 정보를 참조 하십시오. [Visual Studio에서 데이터를 바인딩할 Windows Forms 컨트롤](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md) 및 [Visual Studio에서 데이터에 컨트롤을 바인딩하는 WPF](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)합니다.

## <a name="data-sources"></a>데이터 원본
 데이터 원본 데이터 바인딩의 컨텍스트에서 사용자 인터페이스에 바인딩될 수 있는 메모리에 데이터를 나타냅니다. 실질적으로 데이터 소스는 Entity Framework 클래스, 데이터 집합,.NET 프록시 개체, LINQ to SQL 클래스 또는 모든.NET 개체 또는 컬렉션에 캡슐화 되어 있는 서비스 끝점을 수 있습니다. 일부 데이터 원본 사용으로 항목을 끌어 데이터 바인딩된 컨트롤을 만들 수는 **데이터 소스** 창 하지만 다른 데이터 소스는 그렇지 않습니다. 다음 표에서는 어떠한 데이터 소스가 지원되는지 보여 줍니다.

|데이터 원본|끌어서 놓기 지원 **Windows Forms 디자이너**|끌어서 놓기 지원 **WPF 디자이너**|끌어서 놓기 지원 **Silverlight 디자이너**|
|-----------------|---------------------------------------------------------------|-----------------------------------------------------|-------------------------------------------------------------|
|데이터 집합|예|예|아니요|
|엔터티 데이터 모델|예<sup>1</sup>|예|예|
|LINQ to SQL 클래스|더<sup>2</sup>|더<sup>2</sup>|더<sup>2</sup>|
|서비스 (포함 하 여 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], WCF 서비스 및 웹 서비스)|예|예|예|
|Object|예|예|예|
|SharePoint|예|예|예|

 1. 사용 하 여 모델 생성은 **엔터티 데이터 모델** 마법사, 다음 해당 개체를 디자이너로 끌어 합니다.

 2. LINQ to SQL 클래스에 표시 되지 않습니다는 **데이터 소스** 창. 그러나 LINQ to SQL 클래스에 기반하는 개체 데이터 소스를 새로 만든 다음 해당 개체를 디자이너로 끌어 와 데이터 바인딩된 컨트롤을 만들 수는 있습니다. 자세한 내용은 참조 [연습: 만들기 LINQ to SQL 클래스 (O R 디자이너)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)합니다.

## <a name="data-sources-window"></a>데이터 소스 창
 에 항목으로 데이터 소스는 프로젝트에서 사용할 수는 **데이터 소스** 창. 이 창 표시 또는에서 액세스할 수는 **보기** 양식 디자인 화면이 프로젝트의 활성 창 메뉴. 기본 데이터에 바인딩되는 컨트롤을 만들려면이 창에서 항목을 끌어 하 고 마우스 오른쪽 단추로 클릭 하 여 데이터 소스를 구성할 수도 있습니다.

 ![데이터 소스 창](../data-tools/media/raddata-data-sources-window.png "raddata 데이터 소스 창")

 에 표시 되는 각 데이터 형식에는 **데이터 원본** 창 디자이너로 항목을 끌면 기본 컨트롤을 만들 된다 합니다. 항목을 끌어 오기 전에 **데이터 소스** 창 생성 되는 컨트롤을 변경할 수 있습니다. 자세한 내용은 참조 [데이터 소스 창에서 끌어 올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)합니다.

## <a name="tasks-involved-in-binding-controls-to-data"></a>데이터에 컨트롤 바인딩에 관련 된 작업
 다음 표에서 데이터에 컨트롤을 바인딩하는 가장 일반적인 작업 중 수행 합니다.

|작업|추가 정보|
|----------|----------------------|
|열기는 **데이터 소스** 창.|편집기에서 디자인 화면을 열고 선택 **보기** > **데이터 소스**합니다.|
|데이터 원본을 프로젝트에 추가 합니다.|[새 데이터 소스 추가](../data-tools/add-new-data-sources.md)|
|항목을 끌 때 만들어지는 컨트롤 설정는 **데이터 소스** 창에서 디자이너로 합니다.|[데이터 소스 창에서 끌어올 때 만들 컨트롤 설정](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)|
|항목과 연결 되는 컨트롤 목록을 수정 하는 **데이터 소스** 창.|[데이터 소스 창에 사용자 지정 컨트롤 추가](../data-tools/add-custom-controls-to-the-data-sources-window.md)|
|데이터 바인딩된 컨트롤을 만듭니다.|[Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)<br /><br /> [Visual Studio에서 데이터에 WPF 컨트롤 바인딩](../data-tools/bind-wpf-controls-to-data-in-visual-studio.md)|
|개체 또는 컬렉션에 바인딩하십시오.|[Visual Studio에서 개체 바인딩](../data-tools/bind-objects-in-visual-studio.md)|
|UI에 표시 되는 데이터를 필터링 합니다.|[Windows Forms 응용 프로그램에서 데이터 필터링 및 정렬](../data-tools/filter-and-sort-data-in-a-windows-forms-application.md)|
|컨트롤에 대 한 캡션을 사용자 지정 합니다.|[Visual Studio에서 데이터 바인딩된 컨트롤에 대한 캡션을 만드는 방식 사용자 지정](../data-tools/customize-how-visual-studio-creates-captions-for-data-bound-controls.md)|

## <a name="see-also"></a>참고 항목

- [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)
- [Windows Forms 데이터 바인딩](/dotnet/framework/winforms/windows-forms-data-binding)
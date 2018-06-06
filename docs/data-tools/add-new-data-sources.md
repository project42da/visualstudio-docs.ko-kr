---
title: 새 데이터 원본 추가
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.datasource.datasourcefieldspicker
helpviewer_keywords:
- data [Visual Studio], data sources
- data sources
ms.assetid: ed28c625-bb89-4037-bfde-cfa435d182a2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d88ba8b5648135d361a145dbc98a82dee6836e50
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745596"
---
# <a name="add-new-data-sources"></a>새 데이터 원본 추가
Visual Studio에서.NET 데이터 도구의 컨텍스트에서 용어 *데이터 소스* 는 데이터 저장소에 연결 하 고.NET 응용 프로그램에 데이터를 노출 하는.NET 개체를 나타냅니다. Visual Studio 디자이너에서 데이터베이스 개체를 끌어서 폼에 데이터를 바인딩하는 상용구 코드를 생성 하는 데이터 원본의 출력을 사용할 수는 **데이터 소스** 창. 이 종류의 데이터 원본이 될 수 있습니다.

-   데이터베이스의 몇 가지 종류와 연결 된 Entity Framework 모델에서 사용 되는 클래스입니다.

-   데이터베이스의 몇 가지 종류와 연결 된 데이터 집합입니다.

-   Windows Communication Foundation (WCF) 데이터 서비스 또는 REST 서비스와 같은 네트워크 서비스를 나타내는 클래스입니다.

-   SharePoint 서비스를 나타내는 클래스입니다.

-   클래스 또는 솔루션의 컬렉션입니다.

> [!NOTE]
>  데이터 바인딩 기능을 사용 하지 않는 데이터 집합, Entity Framework에서는 LINQ to SQL, WCF, 또는 SharePoint에서 "데이터 원본"의 개념 적용 되지 않습니다. SQLCommand 개체를 사용 하 여 데이터베이스에 직접 연결 하 고 데이터베이스와 직접 통신 합니다.

 만들고 사용 하 여 데이터 원본 편집는 **데이터 소스 구성 마법사** Windows Forms 또는 Windows Presentation Foundation 응용 프로그램에서 합니다. Entity Framework에 대 한 먼저 엔터티 클래스를 만들고 다음을 선택 하 여 마법사를 시작 **프로젝트** > **새 데이터 소스 추가** (이 문서의 뒷부분에 보다 자세히 설명).

 ![데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)

 데이터 원본을 만든 후에 저장 되는 **데이터 원본** 도구 창 (Shift + Alt + D 또는 **보기** > **다른 창**  >  **데이터 소스**). 데이터 소스를 끌 수는 **데이터 소스** 창 컨트롤 또는 양식 디자인 화면으로 합니다. 이 인해 상용구 코드를 생성-사용자에 게 데이터 저장소에서 발생 하는 데이터를 표시 하는 코드입니다. 다음 그림에서는 Windows form으로 삭제 된 데이터 집합을 보여 줍니다. 응용 프로그램에서 f5 키를 선택한 경우 기본 데이터베이스의 데이터 폼의 컨트롤에 나타납니다.

 ![데이터 원본 끌기 작업](../data-tools/media/raddata-data-source-drag-operation.png)

## <a name="data-source-for-a-database-or-a-database-file"></a>데이터베이스 또는 데이터베이스 파일에 대 한 데이터 원본

### <a name="dataset"></a>데이터 집합
 실행 데이터 원본으로 데이터 집합을 만들려면는 **데이터 소스 구성 마법사** (**프로젝트** > **새 데이터 소스 추가**) 선택 하 고는  **데이터베이스** 데이터 원본 유형입니다. 지시에 따라 기존 또는 새 데이터베이스 연결 또는 데이터베이스 파일을 지정 합니다.

### <a name="entity-classes"></a>엔터티 클래스
 데이터 원본으로는 Entity Framework 모델을 만들려면 먼저 실행 하는 **엔터티 데이터 모델 마법사** 엔터티 클래스를 만드는 (**프로젝트** > **새 항목 추가**  >  **ADO.NET 엔터티 데이터 모델**).

 ![새 Entity Framework 모델 프로젝트 항목](../data-tools/media/raddata-new-entity-framework-model-project-item.png)

 모델을 생성 하려는 방법을 선택 합니다.

 ![엔터티 데이터 모델 마법사](../data-tools/media/raddata-entity-data-model-wizard.png)

 데이터 원본으로 모델을 추가 합니다. 에 생성 된 클래스가 표시는 **데이터 소스 구성 마법사** 선택 하는 경우는 **개체** 범주입니다.

 ![엔터티 클래스와 데이터 소스 구성 마법사](../data-tools/media/raddata-data-source-configuration-wizard-with-entity-classes.png)

## <a name="data-source-for-a-service"></a>서비스에 대 한 데이터 원본
 실행 서비스에서 데이터 원본을 만들려면는 **데이터 소스 구성 마법사** 선택 하 고는 **서비스** 데이터 원본 유형입니다. 이 실제로에 바로 가기는 **서비스 참조 추가** 대화 상자에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 액세스할 수도 있습니다를 **솔루션 탐색기** 선택 하 고 **서비스 참조 추가** .

 서비스에서 데이터 소스를 만들 때 Visual Studio 프로젝트에 대 한 서비스 참조를 추가 합니다. 또한 visual Studio 서비스에서 반환 하는 개체에 해당 하는 프록시 개체를 만듭니다. 예를 들어 데이터 집합을 반환 하는 서비스는 데이터 집합;로 프로젝트에 표시 됩니다. 반환 형식으로 프로젝트에 표시 되는 특정 형식 반환 하는 서비스입니다.

 데이터 소스는 다음 유형의 서비스를 만들 수 있습니다.

-   WCF Data Services. 자세한 내용은 참조 [개요](/dotnet/framework/data/wcf/wcf-data-services-overview)합니다.

-   WCF 서비스. 자세한 내용은 참조 [Windows Communication Foundation 서비스 및 Visual Studio에서 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)합니다.

-   웹 서비스입니다.

    > [!NOTE]
    >  에 표시 되는 항목의 **데이터 소스** 창 서비스에서 반환 되는 데이터에 따라 달라 집니다. 일부 서비스의 수에 대 한 충분 한 정보를 제공 하지는 **데이터 소스 구성 마법사** 바인딩 가능한 개체를 만들 수 있습니다. 예를 들어 서비스가 형식화 되지 않은 데이터 집합을 반환 하는 경우 항목이에 나타납니다는 **데이터 소스** 창 마법사를 완료 합니다. 형식화 되지 않은 데이터 집합은 스키마를 제공 하지 않으며 따라서 마법사에 없는 데이터 소스를 만드는 데 충분 한 정보 때문입니다.

## <a name="data-source-for-an-object"></a>개체에 대 한 데이터 원본
 실행 하 여 하나 이상의 공용 속성을 노출 하는 모든 개체에서 데이터 소스를 만들 수 있습니다는 **데이터 소스 구성 마법사** 다음를 선택 하 고는 **개체** 데이터 원본 유형입니다. 개체의 모든 public 속성에 표시 됩니다는 **데이터 소스** 창.   Entity Framework를 사용 하는 모델을 생성 하는 경우 응용 프로그램에 대 한 데이터 원본 수 있는 엔터티 클래스를 찾을 위치입니다.

 에 **데이터 개체 선택** 페이지에 바인딩할 수 있는 개체를 찾으려면 트리 뷰에서 노드를 확장 합니다. 트리 보기에는 프로젝트 및 어셈블리와 프로젝트에서 참조 되는 다른 프로젝트에 대 한 노드가 포함 됩니다.

 어셈블리 또는 트리 뷰에 표시 되지 않는 프로젝트에 있는 개체에 바인딩할 경우 클릭 **참조 추가** 사용 하는 **참조 추가 대화 상자** 어셈블리 또는 프로젝트에 대 한 참조를 추가 하려면. 참조를 추가한 후에 어셈블리 또는 프로젝트가 트리 뷰에 추가 됩니다.

> [!NOTE]
>  개체가 포함 된 개체 트리 보기에 표시 하는 프로젝트를 빌드해야 할 수 있습니다.

> [!NOTE]
>  끌어서 놓기 데이터 바인딩 구현 하는 개체를 지원 하려면는 <xref:System.ComponentModel.ITypedList> 또는 <xref:System.ComponentModel.IListSource> 인터페이스에는 기본 생성자가 있어야 합니다. 그렇지 않으면 Visual Studio에서 데이터 소스 개체를 인스턴스화할 수 없습니다 및 디자인 화면으로 항목을 끌 때 오류가 표시 됩니다.

## <a name="data-source-for-a-sharepoint-list"></a>SharePoint 목록에 대 한 데이터 원본
 실행 하 여 SharePoint 목록에서 데이터 원본을 만들 수 있습니다는 **데이터 소스 구성 마법사** 선택 하 고는 **SharePoint** 데이터 원본 유형입니다. SharePoint를 통해 데이터를 노출 [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)], SharePoint 데이터 원본 만들기는 서비스에서 데이터 원본을 만드는 것과 동일 합니다. 선택 하 고 **SharePoint** 항목에 **데이터 소스 구성 마법사** 열립니다는 **서비스 참조 추가** 대화 상자에서 SharePoint 데이터 서비스에 연결 SharePoint 서버에 알려 합니다.  SharePoint SDK 필요합니다.

## <a name="see-also"></a>참고 항목

- [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)
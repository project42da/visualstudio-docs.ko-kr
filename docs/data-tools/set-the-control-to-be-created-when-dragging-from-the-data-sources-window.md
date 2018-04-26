---
title: 데이터 소스 창에서 끌어올 때 만들 컨트롤 설정
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Data Sources Window, select controls
- Windows Forms, displaying data
- data [Visual Studio], displaying on Windows Forms
- data [Visual Studio], Data Sources window
ms.assetid: 20597ff8-0c98-43ec-8fb1-05376804ba48
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5b1701b95f86f3645ea7d54a47f8b3c7b36b3fd4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="set-the-control-to-be-created-when-dragging-from-the-data-sources-window"></a>데이터 소스 창에서 끌어올 때 만들 컨트롤 설정
항목을 끌어 데이터 바인딩된 컨트롤을 만들 수 있습니다는 **데이터 소스** 창에서 WPF 디자이너 또는 Windows Forms 디자이너입니다. 각 항목에는 **데이터 소스** 창을 디자이너로 끌어옵니다 때 만들어지는 기본 컨트롤이 있습니다. 그러나 다른 컨트롤을 만들 수 있습니다.

## <a name="set-the-controls-to-be-created-for-data-tables-or-objects"></a>데이터 테이블 또는 개체에 대해 만들 컨트롤 설정
데이터 테이블 또는 개체를 나타내는 항목을 끌어 오기 전에 **데이터 소스** 창 한 컨트롤에 있는 모든 데이터를 표시 하거나 별도 컨트롤에서 각 열 또는 속성을 표시 하도록 선택할 수 있습니다.

이 컨텍스트에서 용어 *개체* 사용자 지정 비즈니스 개체, (엔터티 데이터 모델에서), 엔터티 또는 서비스에서 반환 된 개체를 가리킵니다.

### <a name="to-set-the-controls-to-be-created-for-data-tables-or-objects"></a>데이터 테이블 또는 개체에 대해 생성 될 컨트롤을 설정 하려면

1.  WPF 디자이너 또는 Windows Forms 디자이너가 열려 있는지 확인 합니다.

2.  에 **데이터 소스** 창 데이터 테이블을 나타내는 항목을 선택 또는 설정할 개체입니다.

3.  항목에 대 한 드롭다운 메뉴를 클릭 하 고 메뉴에서 다음 항목 중 하나를 클릭 합니다.

    -   별도 컨트롤에서 각 데이터 필드를 표시 하려면 **세부 정보**합니다. 디자이너에 데이터 항목을 끌면이 작업은 각 열 또는 상위 데이터 테이블 또는 각 컨트롤에는 레이블이 개체의 속성에 대 한 서로 다른 데이터 바인딩된 컨트롤을 생성 됩니다.

    -   모든 데이터를 단일 컨트롤에 표시 하려면 다른 컨트롤 선택 목록에서와 같은 **DataGrid** 또는 **목록** WPF 응용 프로그램에서 또는 **DataGridView** Windows Forms에서 응용 프로그램입니다.

    사용 가능한 컨트롤 목록 종속 되는 디자이너에 열려 있는,.NET Framework 버전을 프로젝트의 대상으로 하 고 해당 지원에 데이터 바인딩 제어 여부 추가한 사용자 지정은 **도구 상자**합니다. 만들 컨트롤을 사용할 수 있는 컨트롤의 목록에 없는 경우에 목록에 컨트롤을 추가할 수 있습니다. 자세한 내용은 참조 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.

    데이터 테이블 또는 개체에 대 한 컨트롤의 목록에 추가할 수 있는 사용자 지정 Windows Forms 컨트롤을 만드는 방법을 알아보려면는 **데이터 원본** 창 참조 [복잡 한 데이터를 지 원하는 Windows Forms 사용자 정의 컨트롤 만들기 바인딩](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)합니다.

## <a name="set-the-controls-to-be-created-for-data-columns-or-properties"></a>데이터 열 또는 속성에 대해 만들 컨트롤 설정
열 또는 개체의 속성을 나타내는 항목을 끌어 오기 전에 **데이터 소스** 창에서 디자이너로, 만들 컨트롤을 설정할 수 있습니다.

#### <a name="to-set-the-controls-to-be-created-for-columns-or-properties"></a>열 또는 속성에 대해 생성 될 컨트롤을 설정 하려면

1.  WPF 디자이너 또는 Windows Forms 디자이너가 열려 있는지 확인 합니다.

2.  에 **데이터 소스** 창 원하는 테이블을 확장 하거나 개체의 열 이나 속성을 표시 합니다.

3.  만들 컨트롤 설정 하려는 각 열 또는 속성을 선택 합니다.

4.  열 또는 속성에 대 한 드롭다운 메뉴를 클릭 하 고 디자이너에는 항목을 끌 때 만들 컨트롤을 선택 합니다.

     사용 가능한 컨트롤 목록 종속 되는 디자이너에 열려 있는,.NET Framework 버전을 프로젝트의 대상으로 하 고 어떤 사용자 지정 바인딩의 경우 데이터에 추가한을 지 원하는 컨트롤의 **도구 상자**합니다. 만들 컨트롤을 사용할 수 있는 컨트롤의 목록에 있으면 목록에 컨트롤을 추가할 수 있습니다. 자세한 내용은 참조 [데이터 소스 창에 사용자 지정 컨트롤을 추가할](../data-tools/add-custom-controls-to-the-data-sources-window.md)합니다.

     데이터 열 또는 속성에 대 한 컨트롤의 목록에 추가할 수 있는 사용자 지정 컨트롤을 만드는 방법을 알아보려면는 **데이터 원본** 창 참조 [단순데이터바인딩을지원하는WindowsForms사용자정의컨트롤만들기](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).

     선택 열 이나 속성에 대 한 컨트롤을 만드는 않으려면 **None** 드롭 다운 메뉴에서 합니다. 부모 테이블이 나 개체를 디자이너로 끌어 하려고 하지만 특정 열 이나 속성을 포함 하지 않을 경우에 유용 합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)
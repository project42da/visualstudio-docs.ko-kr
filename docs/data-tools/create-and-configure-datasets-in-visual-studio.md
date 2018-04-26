---
title: 만들기 및 Visual Studio에서 데이터 집합 구성
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- typed datasets, creating
- datasets, creating
- datasets, configuring
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 8cbe95887e9a29fa98932a18c240bc558201fc43
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="create-and-configure-datasets-in-visual-studio"></a>만들기 및 Visual Studio에서 데이터 집합 구성

A *데이터 집합* 는 메모리는 데이터베이스에서 데이터를에서 저장 하 고 사용할 수 있도록 변경 내용 추적을 지원 하는 개체의 집합 만들기, 읽기, 업데이트 및 삭제 (CRUD) 작업 항상 데이터베이스에 연결 되어 필요 없이 해당 데이터에 있습니다. 데이터 집합은 단순 용으로 설계 된 *데이터 폼* 비즈니스 응용 프로그램입니다. 새 응용 프로그램에 대 한 Entity Framework를 사용 하 여 저장 하 고 메모리에서 데이터를 모델링 하는 것이 좋습니다. 데이터 집합을 사용 하려면 데이터베이스 개념에 대 한 기본 지식이 있어야 합니다.

형식화 된 만들면 <xref:System.Data.DataSet> 를 사용 하 여 디자인 타임에 Visual Studio에서 클래스는 **데이터 소스 구성 마법사**합니다. 프로그래밍 방식으로 데이터 집합을 만드는 방법에 대 한 정보를 참조 하십시오. [(ADO.NET)는 데이터 집합을 만드는](/dotnet/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset)합니다.

## <a name="create-a-new-dataset-by-using-the-data-source-configuration-wizard"></a>데이터 소스 구성 마법사를 사용 하 여 새 데이터 집합 만들기

1.  에 **프로젝트** 메뉴를 클릭 하 여 **새 데이터 소스 추가** 시작 하는 **데이터 소스 구성 마법사**합니다.

2.  에 연결 하는 데이터 원본의 유형을 선택 합니다.

     ![데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png "데이터 소스 구성 마법사")

3.  데이터베이스의 경우 데이터베이스 또는 데이터 집합에 대 한 데이터 원본이 될 데이터베이스를 선택 합니다.

     ![데이터 원본 연결을 선택](../data-tools/media/data-source-choose-a-connection.png "데이터 원본 연결 선택")

4.  테이블 (또는 개별 열)을 저장 프로시저, 함수 및 데이터 집합으로 표현할 수를 데이터베이스에서 뷰를 선택 합니다.

     ![데이터베이스 개체 선택](../data-tools/media/raddata-chose-objects.png "raddata 선택한 개체")

5.  **마침**을 클릭합니다.

6.  데이터 집합에 노드로 나타납니다 **솔루션 탐색기**:

     ![솔루션 탐색기에서 데이터 집합](../data-tools/media/dataset-in-solution-explorer.png "솔루션 탐색기에서 데이터 집합")

     해당 노드를 클릭 하 고 데이터 집합에 표시 된 **데이터 집합 디자이너**합니다. 데이터 집합의 각 테이블에는 맨 아래에 표시 하는 연결 된 TableAdapter 개체를 참고 합니다. 테이블 어댑터는 데이터 집합 및 데이터베이스에 명령을 보낼 필요에 따라 사용 됩니다.

     ![데이터 집합 디자이너](../data-tools/media/dataset-designer.png "데이터 집합 디자이너")

7.  데이터베이스에 정의 된 대로 테이블을 연결 하는 관계 선이 테이블 관계를 나타냅니다. 기본적으로는 데이터베이스의 외래 키 제약 조건이 업데이트 관계 용 으로만으로 표현 됩니다 및 none으로 설정 하는 규칙을 삭제 합니다. 일반적으로 원하는 작업입니다. 그러나 줄을 (를) 실행을 클릭 수는 **관계** 대화 상자에서 계층적 업데이트의 동작을 변경할 수 있습니다. 자세한 내용은 참조 [데이터 집합의 관계](../data-tools/relationships-in-datasets.md) 및 [계층적 업데이트](../data-tools/hierarchical-update.md)합니다.

     ![데이터 집합 관계 대화](../data-tools/media/raddata-relation-dialog.png "raddata 관계 대화 상자")

8.  테이블, 테이블 어댑터 또는 테이블의 열 이름에서 해당 속성을 보려면 클릭는 **속성** 창. 여기에서 값 중 일부를 수정할 수 있습니다. 원본 데이터베이스가 아니라 데이터 집합을 수정 하 기억 하십시오.

     ![데이터 집합 열 속성](../data-tools/media/dataset-column-properties.png "데이터 집합 열 속성")

9. 데이터 집합에 새 테이블이 나 테이블 어댑터를 추가 하거나 기존 테이블 어댑터에 대 한 새 쿼리 추가 하거나 해당 항목을 끌어 테이블 간에 새 관계를 지정할 수 있습니다는 **도구 상자** 탭 합니다. 이 탭을 표시 하는 경우는 **데이터 집합 디자이너** 으로 이동 합니다.

     ![데이터 집합 도구 상자](../data-tools/media/raddata-dataset-toolbox.png "raddata 데이터 집합 도구 상자")

10. 다음으로를 싶을를 데이터 집합을 채우는 방법을 지정 합니다. 이 위해 사용 하 여 **TableAdapter 구성 마법사**합니다. 자세한 내용은 참조 [Tableadapter를 사용 하 여 데이터 집합을 채울](../data-tools/fill-datasets-by-using-tableadapters.md)합니다.

## <a name="add-a-database-table-or-other-object-to-an-existing-dataset"></a>기존 데이터 집합에는 데이터베이스 테이블 또는 다른 개체를 추가

이 절차를 먼저 데이터 집합을 만드는 데 사용 하는 동일한 데이터베이스에서 테이블을 추가 하는 방법을 보여 줍니다.

1.  데이터 집합 노드를 클릭 하 여 **솔루션 탐색기** 데이터 집합 디자이너에 포커스를 맞출입니다.

2.  클릭는 **데이터 원본** Visual Studio의 왼쪽된 여백에 탭 또는 입력 `Data Sources` 에 **빠른 실행**합니다.

3.  데이터 집합 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **마법사로 데이터 소스 구성**합니다.

     ![데이터 원본 상황에 맞는 메뉴](../data-tools/media/data-source-context-menu.png "데이터 원본의 상황에 맞는 메뉴")

4.  마법사를 사용 하는 추가 테이블 또는 저장된 프로시저 또는 다른 데이터베이스 개체를 데이터 집합에 추가 하려면 지정 합니다.

## <a name="add-a-stand-alone-data-table-to-a-dataset"></a>데이터 집합에 독립 실행형 데이터 테이블을 추가 합니다.

1.  데이터 집합을 열고는 **데이터 집합 디자이너**합니다.

2.  끌어서는 <xref:System.Data.DataTable> 에서 클래스는 **DataSet** 탭은 **도구 상자** 에 **데이터 집합 디자이너**합니다.

3.  데이터 테이블에 데이터를 정의 하는 열을 추가 합니다. 테이블을 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 > 열**합니다. 사용 하 여는 **속성** 필요한 경우 열 및 키의 데이터 형식을 설정 하는 창입니다.

4.  독립 실행형 테이블 구현 해야 할 `Fill` 독립 실행형 테이블에서 논리를 데이터로 채울 수 있도록 합니다. 독립 실행형 데이터 테이블을 채우는 대 한 자세한 내용은 참조 [DataAdapter에서 DataSet 채우기](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter)합니다.

## <a name="see-also"></a>참고자료

- [Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)
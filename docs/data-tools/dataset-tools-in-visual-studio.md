---
title: "Visual Studio의 데이터 집합 도구 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.data.DataSet
helpviewer_keywords:
- untyped datasets
- datasets [Visual Basic], extended properties
- typed datasets
- current record in dataset
- XML [Visual Basic], datasets
- DataSet class, about datasets
- unique constraints (datasets)
- data relationships
- parent records in datasets
- extended properties, in typed datasets
- datasets [Visual Basic]
- schemas [Visual Basic], datasets
- datasets [Visual Basic], msprop
- master-detail tables, datasets
- databases [Visual Basic], updating
- msprop
- foreign keys, datasets
- DataSet class
- datasets [Visual Basic], filling
- case sensitivity, datasets
- constraints [Visual Basic], datasets
- child records
- related tables, datasets
- updating datasets, about dataset updates
- data caching, datasets
- DataRelation object, datasets
- untyped datasets, compared to typed datasets
- cache [Visual Studio], datasets
- datasets [Visual Basic], relationships
- related tables
- XML schemas, about XML schemas and datasets
- relationships, datasets
- typed datasets, compared to untyped datasets
- datasets [Visual Basic], populating
- datasets [Visual Basic], namespace
- data adapters, populating datasets
ms.assetid: ee57f4f6-9fe1-4e0a-be9a-955c486ff427
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a8c8660fbc489dd8c4926bb09b8b42006da0897a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="dataset-tools-in-visual-studio"></a>Visual Studio의 데이터 집합 도구
> [!NOTE]
>  데이터 집합 및 관련된 클래스는 응용 프로그램이 응용 프로그램은 데이터베이스에서 연결이 끊어진 동안 메모리에서 데이터를 사용할 수 있도록 하는 초기 2000s에서 레거시.NET 기술입니다. 사용자가 데이터를 수정 하 고 다시 데이터베이스에 변경 내용을 유지할 수 있도록 하는 응용 프로그램에 특히 유용 합니다. 하지만 데이터 집합이 매우 성공적 기술 것으로 입증, 새로운.NET 응용 프로그램 Entity Framework를 사용 하는 것이 좋습니다. Entity Framework 개체 모델로 테이블 형식 데이터로 작업을 더 자연 스러운 숨기 있으며 보다 간단한 프로그래밍 인터페이스입니다.  
  
 DataSet 개체는 프로그램 메모리에 개체는 기본적으로 최소 데이터베이스입니다. 저장 하 고 열려 있는 연결을 유지 하기 위해 필요 없이 하나 이상의 데이터베이스에서 데이터를 수정할 수 있는 DataTable, DataColumn, 및 DataRow 개체를 포함 합니다. 데이터 집합 업데이트를 추적 하 고 응용 프로그램에 다시 연결 되는 경우 데이터베이스에 다시 보낼 수 있도록 해당 데이터에 대 한 변경에 대 한 정보를 유지 합니다.  
  
 데이터 집합 및 관련된 클래스는.NET Framework 클래스 라이브러리에서 System.Data 네임 스페이스에 정의 됩니다. 만들 하 고 코드에서 동적으로 데이터 집합을 수정할 수 있습니다. 작업을 수행 하는 방법에 대 한 자세한 내용은 ADO.NET을 참조 하십시오. 이 섹션의 설명서에는 Visual Studio 디자이너를 사용 하 여 데이터 집합을 사용 하는 방법을 보여 줍니다. 한 가지 알아야: 반면 DataAdapter 개체를 사용 하 여 프로그래밍 방식으로 만들어진 데이터 집합 디자이너를 통해 데이터 집합은 데이터베이스와 상호 작용할 수 TableAdapter 개체를 사용 합니다. 데이터 집합을 프로그래밍 방식으로 만드는 방법은 참조 [Dataadapter 및 Datareader](/dotnet/framework/data/adonet/dataadapters-and-datareaders)합니다.  
  
 데이터베이스에서 데이터 읽기 및 업데이트를 수행 하지 해야 하 고, 추가 하거나 삭제 하는 응용 프로그램, 경우에 일반적으로 제네릭 목록 개체 나 다른 컬렉션 개체에 데이터를 검색 하는 DataReader 개체를 사용 하 여 더 나은 성능을 얻을 수 있습니다. 데이터를 표시 하는 경우 데이터에 바인딩할 있습니다 사용자 인터페이스를 컬렉션에 있습니다.  
  
## <a name="dataset-workflow"></a>데이터 집합 워크플로  
 Visual Studio는 많은 데이터 집합으로 작업을 단순화 하는 도구를 제공 합니다. 기본 종단 간 워크플로.  
  
-   사용 하 여는 **데이터 원본** 창 하나 이상의 데이터 원본에서 새 데이터 집합 만들기. 사용 하 여는 **데이터 집합 디자이너** 를 데이터 집합을 구성 하 여 해당 속성을 설정 합니다. 예를 들어, 각 테이블에서 열과 테이블을 포함 하려면 데이터 원본에서 지정 해야 합니다. 데이터 집합 해야 하는 메모리를 절약 하기 위해 신중 하 게 선택 합니다. 자세한 내용은 [데이터 집합 만들기 및 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)을 참조하세요.  
  
-   외래 키를 올바르게 처리할 수 있도록 테이블 간의 관계를 지정 합니다. 자세한 내용은 참조 [Tableadapter를 사용 하 여 데이터 집합을 채울](../data-tools/fill-datasets-by-using-tableadapters.md)합니다.  
  
-   사용 하 여는 **TableAdapter 구성 마법사** 쿼리 또는 데이터 집합을 채울 저장된 프로시저를 지정할 수 및 데이터베이스 작업 (업데이트, 삭제 및 등)을 구현 합니다. 자세한 내용은 다음 항목을 참조하세요.  
  
    -   [TableAdapter를 사용하여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)  
  
    -   [데이터 집합의 데이터 편집](../data-tools/edit-data-in-datasets.md)  
  
    -   [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)  
  
    -   [데이터를 다시 데이터베이스에 저장](../data-tools/save-data-back-to-the-database.md)  
  
-   쿼리 및 데이터 집합의 데이터를 검색 합니다. 자세한 내용은 참조 [데이터 집합 쿼리](../data-tools/query-datasets.md)합니다. [!INCLUDE[linq_dataset](../data-tools/includes/linq_dataset_md.md)]수 있도록 [LINQ (Language-Integrated Query)](/dotnet/csharp/linq/) 데이터에 대해 한 <xref:System.Data.DataSet> 개체입니다. 자세한 내용은 [LINQ to DataSet](/dotnet/framework/data/adonet/linq-to-dataset)를 참조하세요.  
  
-   사용 하 여는 **데이터 소스** 창 사용자 인터페이스 컨트롤 데이터 집합 또는 해당 개별 열을 바인딩할 하 고 사용자가 편집 가능한 되는 열을 지정할 수 있습니다. 자세한 내용은 참조 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)합니다.  
  
## <a name="datasets-and-n-tier-architecture"></a>데이터 집합 및 N 계층 아키텍처  
 N 계층 응용 프로그램에서 데이터 집합에 대 한 정보를 참조 하십시오. [n 계층 응용 프로그램에서 데이터 집합을 사용할](../data-tools/work-with-datasets-in-n-tier-applications.md)합니다.  
  
## <a name="datasets-and-xml"></a>데이터 집합 및 XML  
 XML에서 데이터 집합을 변환 하는 방법에 대 한 정보를 참조 하십시오. [읽기 XML 데이터를 데이터 집합에](../data-tools/read-xml-data-into-a-dataset.md) 및 [데이터 집합을 XML로 저장](../data-tools/save-a-dataset-as-xml.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET용 Visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)
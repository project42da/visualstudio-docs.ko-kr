---
title: "형식화된 데이터 집합 만들기 및 편집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Designer_Microsoft.VSDesigner.DataSource.Designer.DataSourceRootDesigner"
  - "vs.data.adddataset"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 데이터 집합 디자이너(Dataset Designer)"
  - "데이터 집합 디자이너(Dataset Designer)"
  - "데이터 집합[Visual Basic], 비주얼 디자이너"
ms.assetid: cd0dbe93-be9b-41e4-bc39-e9300678c1f2
caps.latest.revision: 26
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 형식화된 데이터 집합 만들기 및 편집
**데이터 집합 디자이너** 는 데이터 집합과 데이터 집합을 구성하는 개별 항목을 만들고 편집하는데 사용되는 시각적 도구의 집합입니다.  
  
 **데이터 집합 디자이너**에서는 형식화된 데이터 집합에 포함된 개체를 시각적으로 표현합니다.  **데이터 집합 디자이너**를 사용하여 [TableAdapters](../data-tools/tableadapter-overview.md), [TableAdapter 쿼리](../data-tools/how-to-create-tableadapter-queries.md), <xref:System.Data.DataTable>, <xref:System.Data.DataColumn> 및 <xref:System.Data.DataRelation>을 만들고 수정할 수 있습니다.  
  
 **데이터 집합 디자이너**를 열려면 **솔루션 탐색기**에서 데이터 집합을 두 번 클릭하거나 **데이터 소스** 창에서 데이터 집합을 마우스 오른쪽 단추로 클릭하고 **디자이너로 데이터 집합 편집**을 클릭합니다.  자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)을 참조하십시오.  **새 항목 추가** 대화 상자를 사용하여 새 <xref:System.Data.DataSet>을 추가하면 편집할 빈 데이터 집합이 있는 상태로 **데이터 집합 디자이너**가 열립니다.  
  
> [!NOTE]
>  **데이터 집합 디자이너**를 사용하여 데이터 집합의 기능을 확장할 수 있습니다.  디자인 화면을 두 번 클릭하거나, 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택하여 partial 클래스 파일을 만듭니다. partial 클래스 파일에서는 디자이너에 의해 변경되거나 삭제되지 않는 코드를 데이터 집합에 추가할 수 있습니다.  TableAdapter의 기능을 확장하는 방법에 대한 자세한 내용은 [방법: TableAdapter의 기능 확장](../data-tools/extend-the-functionality-of-a-tableadapter.md)을 참조하십시오.  
  
 다음 표에서는 **데이터 집합 디자이너**를 사용하여 수행할 수 있는 일반적인 작업을 보여 줍니다.  
  
|To|참조|  
|--------|--------|  
|TableAdapter 만들기|[방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)|  
|TableAdapter 편집|[방법: TableAdapter 편집](../Topic/How%20to:%20Edit%20TableAdapters.md)|  
|TableAdapter 쿼리 만들기|[방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)|  
|TableAdapter 쿼리 편집|[방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)|  
|<xref:System.Data.DataTable> 만들기|[방법: 데이터 테이블 만들기](../data-tools/how-to-create-data-tables.md)|  
|<xref:System.Data.DataTable> 편집|[DataTable 디자인](../data-tools/designing-datatables.md)|  
|<xref:System.Data.DataColumn> 만들기|[방법: DataTable에 열 추가](../Topic/How%20to:%20Add%20Columns%20to%20a%20DataTable.md)|  
|두 <xref:System.Data.DataTable> 사이에 관계 만들기|[방법: 데이터 집합 디자이너를 사용하여 DataRelation 만들기](../Topic/How%20to:%20Create%20DataRelations%20with%20the%20Dataset%20Designer.md)|  
|데이터 집합의 기능 확장|[방법: 데이터 집합의 기능 확장](../Topic/How%20to:%20Extend%20the%20Functionality%20of%20a%20Dataset.md)|  
|데이터 테이블의 <xref:System.Data.DataTable.ColumnChanging> 이벤트에 유효성 검사 추가|[방법: 열 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Column%20Changes.md)|  
|데이터 테이블의 <xref:System.Data.DataTable.RowChanging> 이벤트에 유효성 검사 추가|[방법: 행 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Row%20Changes.md)|  
  
## 디자인 화면에 개체 만들기  
 데이터 집합을 구성하는 개별 개체를 추가하거나 편집하여 데이터 집합을 만들 수 있습니다.  다음 표에서는 **도구 상자**의 **데이터 집합** 탭에서 디자인 화면으로 끌어 올 수 있는 다양한 개체에 대해 설명합니다.  
  
|개체|설명|  
|--------|--------|  
|TableAdapter|기본 데이터베이스와 통신하고 데이터 테이블을 채우는 데 사용되는 데이터 연결과 데이터 명령의 컬렉션이 들어 있습니다.  자세한 내용은 [TableAdapter 개요](../data-tools/tableadapter-overview.md) 및 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)를 참조하십시오.|  
|쿼리|TableAdapter 쿼리는 SQL 문과 저장 프로시저를 실행하는 강력한 형식의 메서드입니다.  TableAdapter 쿼리를 실행하면 데이터 테이블이 데이터로 채워지거나 다른 데이터베이스 작업이 수행됩니다.  자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)을 참조하십시오.  쿼리를 테이블로 끌어 오면 테이블에 쿼리가 추가되지만 쿼리를 **데이터 집합 디자이너**의 빈 영역으로 끌어 오면 전역 쿼리가 만들어집니다.  자세한 내용은 [방법: 데이터 집합에 전역 쿼리 추가](../data-tools/how-to-add-global-queries-to-a-tableadapter.md)을 참조하십시오.|  
|<xref:System.Data.DataTable>|데이터베이스에서 반환되는 행의 메모리 내 컬렉션을 나타냅니다.|  
|관계\(<xref:System.Data.DataRelation>\)|두 <xref:System.Data.DataTable> 사이의 부모\/자식 관계를 나타냅니다.  자세한 내용은 [DataRelation 개체 소개](../Topic/Introduction%20to%20DataRelation%20Objects.md) 및 [연습: 데이터 테이블 간의 관계 만들기](../Topic/Walkthrough:%20Creating%20a%20Relationship%20between%20Data%20Tables.md)를 참조하십시오.|  
  
> [!NOTE]
>  **데이터 집합 디자이너** 는 데이터 집합이 만들어졌을 때만 내부 데이터베이스에 연결합니다. 디자이너는 차후의 데이터베이스 변경을 자동으로 감지하지 않습니다.  **구성 마법사** 를 재 실행하여 기존 .xsd를 새로 고침합니다.  테이블 관계가 변경되는 경우, 해당 테이블을 제거하고 .xsd에 관련 테이블을 재 추가합니다.  
  
## LINQ to Dataset  
 [!INCLUDE[linq_dataset](../data-tools/includes/linq_dataset_md.md)]을 사용하면 <xref:System.Data.DataSet> 개체의 데이터에 대해 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)를 수행할 수 있습니다.  자세한 내용은 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)을 참조하십시오.  
  
## 참고 항목  
 [연습: 데이터 집합 디자이너를 사용하여 데이터 집합 만들기](../data-tools/walkthrough-creating-a-dataset-with-the-dataset-designer.md)   
 [연습: 여러 개의 쿼리가 있는 TableAdapter 만들기](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)   
 [연습: 데이터 집합 디자이너에서 DataTable 만들기](../data-tools/walkthrough-creating-a-datatable-in-the-dataset-designer.md)   
 [연습: 데이터 테이블 간의 관계 만들기](../Topic/Walkthrough:%20Creating%20a%20Relationship%20between%20Data%20Tables.md)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)   
 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
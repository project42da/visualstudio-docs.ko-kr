---
title: "Visual Studio에서 데이터 집합 작업 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.data.DataSet"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "캐시[Visual Studio], 데이터 집합"
  - "대/소문자 구분, 데이터 집합"
  - "자식 레코드"
  - "제약 조건[Visual Basic], 데이터 집합"
  - "데이터 집합의 현재 레코드"
  - "데이터 어댑터, 데이터 집합 채우기"
  - "데이터 캐싱, 데이터 집합"
  - "데이터 관계"
  - "데이터베이스[Visual Basic], 업데이트"
  - "DataRelation 개체, 데이터 집합"
  - "DataSet 클래스"
  - "DataSet 클래스, 데이터 집합 정보"
  - "데이터 집합[Visual Basic]"
  - "데이터 집합[Visual Basic], 확장 속성"
  - "데이터 집합[Visual Basic], 채우기"
  - "데이터 집합[Visual Basic], msprop"
  - "데이터 집합[Visual Basic], namespace"
  - "데이터 집합[Visual Basic], 채우기"
  - "데이터 집합[Visual Basic], 관계"
  - "확장 속성, 형식화된 데이터 집합"
  - "외래 키, 데이터 집합"
  - "마스터-세부 테이블, 데이터 집합"
  - "msprop"
  - "데이터 집합의 부모 레코드"
  - "관계 테이블"
  - "관계 테이블, 데이터 집합"
  - "관계, 데이터 집합"
  - "스키마[Visual Basic], 데이터 집합"
  - "형식화된 데이터 집합"
  - "형식화된 데이터 집합, 형식화되지 않은 데이터 집합과 비교"
  - "unique 제약 조건(데이터 집합)"
  - "형식화되지 않은 데이터 집합"
  - "형식화되지 않은 데이터 집합, 형식화된 데이터 집합과 비교"
  - "데이터 집합 업데이트, 데이터 집합 업데이트 정보"
  - "XML[Visual Basic], 데이터 집합"
  - "XML 스키마, XML 스키마 및 데이터 집합 정보"
ms.assetid: ee57f4f6-9fe1-4e0a-be9a-955c486ff427
caps.latest.revision: 49
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual Studio에서 데이터 집합 작업
데이터 집합은 응용 프로그램에서 사용할 데이터를 임시로 저장할 수 있는 데이터 테이블이 들어 있는 개체입니다.  응용 프로그램에서 데이터 관련 작업을 수행해야 하는 경우 데이터 집합으로 데이터를 로드하여 사용할 데이터의 로컬 메모리 내 캐시를 응용 프로그램에 제공할 수 있습니다.  데이터 집합에서는 응용 프로그램이 데이터베이스와의 연결이 끊어져도 데이터 관련 작업을 수행할 수 있습니다.  데이터 집합에는 데이터에 대한 변경 내용이 유지되므로 응용 프로그램이 다시 연결되면 업데이트를 추적하여 데이터베이스에 다시 보낼 수 있습니다.  
  
 다음 항목에서는 Visual Studio에서 데이터 집합을 사용하는 데 대한 세부 정보를 제공합니다.  
  
|항목|설명|  
|--------|--------|  
|[형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)|데이터 집합을 만드는 데 사용되는 디자인 타임 도구에 대해 설명합니다.|  
|[방법: 형식화된 데이터 집합 만들기](../data-tools/create-and-configure-datasets-in-visual-studio.md)|[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 디자인 도구를 사용하여 형식화된 데이터 집합을 만드는 방법을 설명합니다.|  
|[방법: 데이터 집합의 기능 확장](../Topic/How%20to:%20Extend%20the%20Functionality%20of%20a%20Dataset.md)|디자이너에서 생성된 코드 이외의 다른 코드를 추가할 수 있는 데이터 집합의 partial 클래스를 만드는 단계를 제공합니다.|  
|[방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)|**솔루션 탐색기** 및 **데이터 소스** 창에서 데이터 집합을 여는 방법에 대해 설명합니다.|  
|[방법: 데이터 집합 편집](../Topic/How%20to:%20Edit%20a%20Dataset.md)|**데이터 집합 디자이너**를 사용하여 데이터 집합의 개체를 편집하는 방법에 대해 설명합니다.|  
|[연습: 데이터 집합 디자이너를 사용하여 데이터 집합 만들기](../data-tools/walkthrough-creating-a-dataset-with-the-dataset-designer.md)|**데이터 소스 구성 마법사**를 사용하지 않고 형식화된 데이터 집합을 만드는 방법을 단계별로 설명합니다.|  
|[DataTable 디자인](../data-tools/designing-datatables.md)|디자인 타임 도구를 사용하여 데이터 테이블을 만들고 편집하는 방법을 설명하는 항목에 대한 링크를 제공합니다.|  
|[데이터 집합에서의 관계](../data-tools/relationships-in-datasets.md)|디자인 타임 도구를 사용하여 데이터 관계를 만들고 편집하는 방법을 설명하는 항목에 대한 링크를 제공합니다.|  
|[TableAdapter](../Topic/TableAdapters.md)|디자인 타임 도구를 사용하여 TableAdapter를 만들고 편집하는 방법을 설명하는 항목에 대한 링크를 제공합니다.|  
|[N 계층 응용 프로그램에서 데이터 집합 작업 작업](../data-tools/work-with-datasets-in-n-tier-applications.md)|N 계층 응용 프로그램에 대해 설명하고 N 계층 응용 프로그램에서 데이터 집합을 다루는 데 사용 가능한 기능에 대해 설명합니다.|  
  
 <xref:System.Data.DataSet>의 구조는 관계형 데이터베이스 구조와 유사하며 테이블, 행, 열, 제약 조건 및 관계로 구성된 계층적 개체 모델을 취합니다.  
  
 데이터 집합에는 형식화된 데이터 집합 및 형식화되지 않은 데이터 집합의 두 가지 종류가 있습니다.  자세한 내용은 아래의 "형식화된 데이터 집합과 형식화되지 않은 데이터 집합" 단원을 참조하십시오. 형식화된 데이터 집합은 .xsd 파일에서 해당 스키마\(테이블 및 열 구조\)를 파생시키므로 프로그래밍하기 쉽습니다.  응용 프로그램에서는 형식화된 데이터 집합이나 형식화되지 않은 데이터 집합 중 어느 것을 사용해도 되지만  Visual Studio에는 형식화된 데이터 집합을 지원하는 도구가 더 많으므로 형식화된 데이터 집합을 사용하면 프로그래밍 작업이 더욱 쉬워지고 오류도 줄어듭니다.  
  
 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 실행하거나 **프로젝트** 메뉴의 **새 항목 추가** 명령을 통해 **데이터 집합** 항목을 추가하여 형식화된 데이터 집합을 만들 수 있습니다.  자세한 내용은 [방법: 형식화된 데이터 집합 만들기](../data-tools/create-and-configure-datasets-in-visual-studio.md)를 참조하십시오.  
  
 **데이터 집합** 항목을 **도구 상자**에서 [Windows Forms Designer](http://msdn.microsoft.com/ko-kr/3c3d61f8-f36c-4d41-b9c3-398376fabb15) 또는 [Component Designer](../Topic/Component%20Designer.md)로 끌어 와 형식화되지 않은 데이터 집합을 만들 수 있습니다.  
  
 데이터 집합을 만든 후에는 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)에서 편집합니다.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 네임스페이스의 다음 부분을 사용하여 형식화된 데이터 집합과 형식화되지 않은 데이터 집합을 만들고 이에 대한 작업을 수행할 수 있습니다.  
  
 ![시스템 데이터 데이터 집합 네임스페이스](../data-tools/media/vbdatasetnamspace.png "vbDataSetNamspace")  
데이터 집합은 System.Data 네임스페이스에 있습니다.  
  
 사용자는 속성 및 컬렉션 같은 표준 프로그래밍 구문을 통해 데이터 집합의 개체를 볼 수 있습니다.  예를 들면 다음과 같습니다.  
  
-   <xref:System.Data.DataSet> 클래스에는 데이터 테이블로 이루어진 <xref:System.Data.DataTableCollection> 컬렉션과 <xref:System.Data.DataRelation> 개체로 이루어진 <xref:System.Data.DataRelationCollection> 컬렉션이 포함됩니다.  
  
-   <xref:System.Data.DataTable> 클래스에는 테이블 행으로 이루어진 <xref:System.Data.DataRowCollection> 컬렉션, 데이터 열로 이루어진 <xref:System.Data.DataColumnCollection> 컬렉션 및 데이터 관계로 이루어진 <xref:System.Data.DataTable.ChildRelations%2A>과 <xref:System.Data.DataTable.ParentRelations%2A> 컬렉션이 포함됩니다.  
  
-   <xref:System.Data.DataRow> 클래스에는 <xref:System.Data.DataRow.RowState%2A> 속성이 포함됩니다. 이 속성 값은 데이터 테이블이 데이터베이스로부터 처음 로드된 후 행이 변경되었는지 여부와 어떻게 변경되었는지를 나타냅니다.  <xref:System.Data.DataRow.RowState%2A> 속성 값은 <xref:System.Data.DataRowState>, <xref:System.Data.DataRowState>, <xref:System.Data.DataRowState> 또는 <xref:System.Data.DataRowState>가 될 수 있습니다.  
  
## 데이터로 데이터 집합 채우기  
 데이터 집합에는 기본적으로 실제 데이터가 포함되어 있지 않습니다.  데이터 집합을 데이터로 채운다는 것은 실제로 데이터 집합을 구성하는 개별 <xref:System.Data.DataTable> 개체에 데이터를 로드하는 것을 말합니다.  데이터 테이블은 TableAdapter 쿼리를 실행하거나 데이터 어댑터\(예: <xref:System.Data.SqlClient.SqlDataAdapter>\) 명령을 실행하여 채웁니다.  데이터 집합을 데이터로 채울 때 다양한 이벤트가 발생하고 제약 조건이 검사되는 등 여러 작업이 이루어집니다.  데이터 집합에 데이터를 로드하는 것에 대한 자세한 내용은 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)를 참조하십시오.  
  
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)에서 Windows 응용 프로그램의 폼으로 항목을 끌면 데이터 집합을 채우는 코드가 폼 로드 이벤트 처리기에 자동으로 추가됩니다.  자세한 내용을 보려면 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md) 연습을 완료하십시오.  
  
 TableAdapter로 데이터 집합을 채우는 예제:  
  
 [!code-cs[VbRaddataDatasets#1](../data-tools/codesnippet/CSharp/dataset-tools-in-visual-studio_1.cs)]
 [!code-vb[VbRaddataDatasets#1](../data-tools/codesnippet/VisualBasic/dataset-tools-in-visual-studio_1.vb)]  
  
 다음과 같은 다양한 방법으로 데이터 집합을 채울 수 있습니다.  
  
-   데이터 마법사 중 하나와 같은 디자인 타임 도구를 사용하여 데이터 집합을 만든 경우 TableAdapter의 `Fill` 메서드를 호출합니다.  TableAdapter는 기본 `Fill` 메서드로 만듭니다. 이 메서드의 이름은 사용자가 변경할 수 있으므로 실제 이름은 이와 다를 수 있습니다. 자세한 내용은 [방법: 데이터 집합을 데이터로 채우기](../data-tools/how-to-fill-a-dataset-with-data.md)의 "TableAdapter를 사용하여 데이터 집합 채우기" 단원을 참조하십시오.  
  
-   <xref:System.Data.Common.DataAdapter>의 `Fill` 메서드를 호출합니다.  자세한 내용은 [DataAdapter에서 DataSet 채우기](../Topic/Populating%20a%20DataSet%20from%20a%20DataAdapter.md)를 참조하십시오.  
  
-   <xref:System.Data.DataRow> 개체를 만들고 이 개체들을 테이블의 <xref:System.Data.DataRowCollection> 컬렉션에 추가하여 데이터 집합의 테이블을 직접 채웁니다.  이 작업은 런타임에만 가능하며 디자인 타임에는 <xref:System.Data.DataRowCollection> 컬렉션을 설정할 수 없습니다. 자세한 내용은 [DataTable에 데이터 추가](../Topic/Adding%20Data%20to%20a%20DataTable.md)를 참조하십시오.  
  
-   XML 문서나 스트림을 데이터 집합으로 읽을 수도 있습니다.  자세한 내용은 <xref:System.Data.DataSet.ReadXml%2A> 메서드를 참조하십시오.  예제를 보려면 [연습: XML 데이터를 데이터 집합으로 읽어 오기](../data-tools/read-xml-data-into-a-dataset.md)를 참조하십시오.  
  
-   한 데이터 집합의 내용을 다른 데이터 집합의 내용과 병합\(복사\)합니다.  응용 프로그램이 다양한 XML Web services 같은 여러 개의 소스에서 데이터 집합을 가져와서 단일 데이터 집합으로 통합하는 경우 이 방법이 유용합니다.  자세한 내용은 [DataSet 내용 병합](../Topic/Merging%20DataSet%20Contents.md)을 참조하십시오.  
  
-   한 <xref:System.Data.DataTable>의 내용을 다른 데이터 테이블의 내용과 병합\(복사\)합니다.  
  
## 데이터베이스에 데이터 집합의 데이터 다시 저장  
 데이터 집합에서 레코드가 변경되면 해당 변경 내용을 데이터베이스에 다시 써야 합니다.  데이터 집합과 해당 데이터베이스 사이에 통신하는 TableAdapter 또는 <xref:System.Data.Common.DataAdapter>의 `Update` 메서드를 호출하면 데이터 집합의 변경 내용을 데이터베이스에 쓸 수 있습니다.  
  
 Visual Studio의 데이터 디자인 도구를 사용하는 경우 TableAdapter의 Update 메서드를 호출하여 저장할 데이터 테이블에 전달하여 데이터를 데이터베이스에 다시 보냅니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[VbRaddataDatasets#2](../data-tools/codesnippet/CSharp/dataset-tools-in-visual-studio_2.cs)]
 [!code-vb[VbRaddataDatasets#2](../data-tools/codesnippet/VisualBasic/dataset-tools-in-visual-studio_2.vb)]  
  
 업데이트 프로세스를 보다 세밀하게 제어하려는 경우 각 데이터 행의 개별 값에 전달할 수 있는 TableAdapter DBDirect 메서드 중 하나를 호출합니다.  자세한 내용은 [방법: TableAdapter를 사용하여 데이터 업데이트](../data-tools/update-data-by-using-a-tableadapter.md) 및 [연습: TableAdapter DBDirect 메서드를 사용하여 데이터 저장](../data-tools/save-data-with-the-tableadapter-dbdirect-methods.md)을 참조하십시오.  
  
 개별 레코드 조작에 사용되는 <xref:System.Data.DataRow> 클래스에는 <xref:System.Data.DataRow.RowState%2A> 속성이 포함됩니다. 이 속성 값은 데이터 테이블이 데이터베이스로부터 처음 로드된 후 행이 변경되었는지 여부와 어떻게 변경되었는지를 나타냅니다.  이 속성 값은 <xref:System.Data.DataRowState>, <xref:System.Data.DataRowState>, <xref:System.Data.DataRowState> 또는 <xref:System.Data.DataRowState>가 될 수 있습니다.  TableAdapter와 <xref:System.Data.Common.DataAdapter>의 `Update` 메서드는 <xref:System.Data.DataRow.RowState%2A> 속성의 값을 검사하여 데이터베이스에 써야 하는 레코드와 호출해야 하는 특정 데이터베이스 명령\(`InsertCommand`, `UpdateCommand` 및 `DeleteCommand`\)을 결정합니다.  
  
 데이터 업데이트에 대한 자세한 내용은 [데이터 저장](../data-tools/saving-data.md)을 참조하십시오.  
  
## 데이터 집합의 레코드 탐색  
 데이터 집합은 연결이 완전히 끊어진 데이터 컨테이너이므로 ADO 레코드 집합과는 달리 현재 레코드라는 개념을 지원하지 않습니다.  그러나 데이터 집합에서는 모든 레코드를 언제든지 사용할 수 있습니다.  
  
 현재 레코드가 없으므로 현재 레코드를 가리키는 특정 속성이 없으며 한 레코드에서 다른 레코드로 이동하기 위한 메서드나 속성도 없습니다\(아래의 참고 참조\).  데이터 집합에 있는 각각의 테이블에는 개체로 액세스할 수 있으며 각 테이블에는 행 컬렉션이 포함되어 있습니다.  컬렉션의 인덱스를 통해 행에 액세스하거나 사용하는 프로그래밍 언어에서 컬렉션 관련 문을 사용하여 행에 액세스하는 것처럼, 각 테이블에 대해서는 컬렉션에 대해 작업하듯이 할 수 있습니다.  
  
 예를 들어, 다음 코드를 사용하여 `Customers` 테이블의 넷째 행을 가져올 수 있습니다.  
  
 [!code-cs[VbRaddataDatasets#3](../data-tools/codesnippet/CSharp/dataset-tools-in-visual-studio_3.cs)]
 [!code-vb[VbRaddataDatasets#3](../data-tools/codesnippet/VisualBasic/dataset-tools-in-visual-studio_3.vb)]  
  
> [!NOTE]
>  폼의 컨트롤을 데이터 집합에 바인딩할 경우 <xref:System.Windows.Forms.BindingNavigator> 구성 요소를 사용하여 개별 레코드에 대한 액세스를 단순화할 수 있습니다.  자세한 내용은 [방법: Windows Forms에서 데이터 탐색](../Topic/How%20to:%20Navigate%20Data%20in%20Windows%20Forms.md)을 참조하십시오.  
  
## LINQ to Dataset  
 [!INCLUDE[linq_dataset](../data-tools/includes/linq_dataset_md.md)]을 사용하면 <xref:System.Data.DataSet> 개체의 데이터에 대해 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)를 수행할 수 있습니다.  자세한 내용은 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)을 참조하십시오.  
  
## 데이터 집합 및 XML  
 데이터 집합은 XML로 나타낼 수 있는 데이터의 관계형 뷰입니다.  데이터 집합과 XML 사이의 이러한 관계를 통해 데이터 집합의 다음 기능을 사용할 수 있습니다.  
  
-   테이블, 열, 관계, 제약 조건 등 데이터 집합의 구조는 XML 스키마에 정의할 수 있습니다.  데이터 집합에서는 <xref:System.Data.DataSet.ReadXmlSchema%2A> 및 <xref:System.Data.DataSet.WriteXmlSchema%2A> 메서드를 사용하여 구조적 정보를 저장하는 스키마를 읽고 쓸 수 있습니다.  사용할 스키마가 없는 경우 데이터 집합에서는 <xref:System.Data.DataSet.InferXmlSchema%2A> 메서드를 통해 관계형으로 구조화된 XML 문서의 데이터에서 스키마를 추론할 수 있습니다.  XML 스키마에 대한 자세한 내용은 [XML 스키마 빌드](../Topic/Building%20XML%20Schemas.md)를 참조하십시오.  
  
-   스키마 정보를 통합하여 데이터 구조를 정의하는 데이터 집합 클래스를 생성할 수 있습니다.  이것을 *형식화된* 데이터 집합이라고 합니다.  형식화된 데이터 집합 만들기에 대한 자세한 내용은 [방법: 형식화된 데이터 집합 만들기](../data-tools/create-and-configure-datasets-in-visual-studio.md)를 참조하십시오.  
  
-   데이터 집합의 <xref:System.Data.DataSet.ReadXml%2A> 메서드를 사용하면 XML 문서나 스트림을 데이터 집합으로 읽어 올 수 있으며 <xref:System.Data.DataSet.WriteXml%2A> 메서드를 사용하면 데이터 집합을 XML로 쓸 수 있습니다.  XML은 서로 다른 응용 프로그램 간의 데이터 표준 교환 형식이므로 다른 응용 프로그램에서 XML 형식의 정보가 들어 있는 데이터 집합을 전송해 와도 해당 데이터 집합을 로드할 수 있습니다.  이와 마찬가지로 데이터 집합은 데이터를 XML 스트림 또는 문서로 쓸 수 있으며 이를 다른 응용 프로그램과 공유할 수도 있고 표준 형식으로 저장만 해 둘 수도 있습니다.  
  
-   데이터 집합 또는 데이터 테이블의 내용에 대한 XML 뷰\(<xref:System.Xml.XmlDataDocument> 개체\)를 만든 후 데이터 집합을 사용하는 관계형 메서드 또는 XML 메서드를 사용하여 데이터를 보고 조작할 수 있습니다.  두 개의 뷰는 변경될 때마다 자동으로 동기화됩니다.  
  
## 형식화된 데이터 집합과 형식화되지 않은 데이터 집합  
 형식화된 데이터 집합은 기본 <xref:System.Data.DataSet> 클래스에서 파생되며 .xsd 파일에 저장되는 **데이터 집합 디자이너**의 정보를 사용하여 강력한 형식의 새 데이터 집합 클래스를 생성합니다.  테이블, 열 등의 스키마 정보가 생성되면 첫 번째 클래스 개체 및 속성 집합으로서 이 새로운 데이터 집합 클래스에 컴파일됩니다.  형식화된 데이터 집합은 기본 <xref:System.Data.DataSet> 클래스에서 상속되므로 형식화된 클래스는 <xref:System.Data.DataSet> 클래스의 모든 기능을 그대로 가져오며 <xref:System.Data.DataSet> 클래스의 인스턴스를 매개 변수로 받는 메서드와 함께 사용할 수 있습니다.  
  
 이와 달리 형식화되지 않은 데이터 집합에는 내장 스키마가 없습니다.  형식화된 데이터 집합과 마찬가지로 형식화되지 않은 데이터 집합에도 테이블, 열 등이 들어 있지만 이들 요소는 컬렉션으로만 표시됩니다.  그러나 형식화되지 않은 데이터 집합에서 테이블 및 기타 데이터 요소를 직접 만든 후에는 데이터 집합의 <xref:System.Data.DataSet.WriteXmlSchema%2A> 메서드를 사용하여 데이터 집합의 구조를 스키마로 내보낼 수 있습니다.  
  
### 형식화된 데이터 집합 및 형식화되지 않은 데이터 집합에서의 데이터 액세스 비교  
 형식화된 데이터 집합의 클래스에는 해당 속성이 테이블과 열의 실제 이름을 사용하는 개체 모델이 있습니다.  예를 들어, 형식화된 데이터 집합으로 작업하는 경우 다음과 같은 코드를 사용하여 열을 참조할 수 있습니다.  
  
 [!code-cs[VbRaddataDatasets#4](../data-tools/codesnippet/CSharp/dataset-tools-in-visual-studio_4.cs)]
 [!code-vb[VbRaddataDatasets#4](../data-tools/codesnippet/VisualBasic/dataset-tools-in-visual-studio_4.vb)]  
  
 이와는 반대로 형식화되지 않은 데이터 집합으로 작업하는 경우 다음과 같은 코드를 사용합니다.  
  
 [!code-cs[VbRaddataDatasets#5](../data-tools/codesnippet/CSharp/dataset-tools-in-visual-studio_5.cs)]
 [!code-vb[VbRaddataDatasets#5](../data-tools/codesnippet/VisualBasic/dataset-tools-in-visual-studio_5.vb)]  
  
 형식화된 액세스는 읽기가 더 쉬울 뿐만 아니라 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **코드 편집기**에서 IntelliSense가 완벽하게 지원됩니다.  작업하기 쉽다는 이점 이외에 형식화된 데이터 집합에 대한 구문에서는 컴파일 타임에 형식을 검사하므로 데이터 집합 멤버에 값을 할당할 때 오류가 발생할 가능성이 크게 줄어듭니다.  <xref:System.Data.DataSet>에서 열 이름을 변경하고 응용 프로그램을 컴파일하면 빌드 오류가 발생합니다.  **작업 목록**에서 빌드 오류를 두 번 클릭하면 이전 열 이름을 참조하는 코드 줄로 직접 이동할 수 있습니다.  또한, 액세스가 런타임에 컬렉션을 통해 결정되지 않고 컴파일 타임에 결정되므로 형식화된 데이터 집합의 테이블과 열에 대한 액세스는 런타임에 약간 더 빠릅니다.  
  
 형식화된 데이터 집합에 장점이 많지만 형식화되지 않은 데이터 집합을 사용하는 것이 유용한 경우도 많이 있습니다.  데이터 집합에 스키마가 없는 경우가 이에 해당됩니다.  예를 들어, 응용 프로그램이 데이터 집합을 반환하는 구성 요소와 상호 작용할 때 반환되는 데이터 집합의 구조를 미리 알지 못하는 경우 이런 상황이 발생할 수 있습니다.  이와 마찬가지로, 정적이지 않거나 예측할 수 없는 구조의 데이터로 작업하는 경우 데이터 집합을 사용하면 데이터 구조가 변경될 때마다 형식화된 데이터 집합 클래스를 다시 생성해야 하므로 비현실적입니다.  
  
 보다 일반적으로, 사용 가능한 스키마가 없는 상태에서 데이터 집합을 동적으로 만들어야 하는 경우가 많이 있습니다.  이 경우, 데이터가 관계형으로 표현되는 한 데이터 집합은 정보를 편리하게 보관할 수 있는 구조입니다.  이와 동시에 정보를 serialize하여 다른 프로세스로 전달해 주거나 XML 파일을 기록하는 등 데이터 집합의 기능을 사용할 수 있습니다.  
  
## 데이터 집합의 대\/소문자 구분  
 데이터 집합 내에서 테이블 및 열 이름은 기본적으로 대\/소문자를 구분하지 않습니다. 즉, "Customers"라는 데이터 집합의 테이블은 "customers"로도 참조될 수 있습니다. 이러한 사항은 대\/소문자만으로는 데이터 요소의 이름을 구별할 수 없는 SQL Server의 기본 동작을 비롯한 여러 데이터베이스에서 사용되는 명명 규칙과 같습니다.  
  
> [!NOTE]
>  데이터 집합과 달리 XML 문서는 대\/소문자를 구분합니다. 따라서, 스키마에 정의된 데이터 요소의 이름은 대\/소문자를 구분합니다.  예를 들어, 스키마에서 스키마 프로토콜을 통해 "Customers"라는 테이블과 "customers"라는 테이블을 서로 다른 테이블로 정의할 수 있습니다. 이렇게 하면 대\/소문자만 다른 요소가 포함된 스키마를 사용하여 데이터 집합 클래스를 만들 경우 이름이 충돌할 수 있습니다.  
  
 그러나 대\/소문자 구분은 데이터 집합 내에서 데이터가 해석되는 방식을 결정하는 한 요인이 될 수 있습니다.  예를 들어, 데이터 집합 테이블에 포함된 데이터를 필터링하는 경우 대\/소문자 구분 여부에 따라 검색 조건이 다른 결과를 반환할 수 있습니다.  데이터 집합의 <xref:System.Data.DataSet.CaseSensitive%2A> 속성을 설정하면 필터링, 검색 및 정렬 시 대\/소문자를 구분할지 여부를 제어할 수 있습니다.  데이터 집합의 모든 테이블은 기본적으로 이 속성 값을 상속합니다.  테이블의 <xref:System.Data.DataTable.CaseSensitive%2A> 속성을 설정하면 각 개별 테이블에 대해 이 속성을 재정의할 수 있습니다.  
  
## 관련 테이블 및 DataRelation 개체  
 데이터 집합에 테이블이 여러 개 있는 경우 테이블 내의 정보를 서로 관련시킬 수 있습니다.  데이터 집합에서는 기본적으로 이런 관계를 인식하지 못하므로 관련 테이블의 데이터로 작업하려면 데이터 집합에 속한 테이블 간의 관계를 설명하는 <xref:System.Data.DataRelation> 개체를 만들어야 합니다.  자세한 내용은 [방법: 관련 DataTable의 레코드에 액세스](../Topic/How%20to:%20Access%20Records%20in%20Related%20DataTables.md)를 참조하십시오.  <xref:System.Data.DataRelation> 개체를 사용하여 프로그래밍 방식으로 부모 레코드에 대해 자식 레코드를 페치하고 반대로 자식 레코드에 대해 부모 레코드를 페치할 수도 있습니다.  자세한 내용은 [데이터 집합에서의 관계](../data-tools/relationships-in-datasets.md)를 참조하십시오.  데이터베이스에 둘 이상의 테이블 간의 관계가 포함된 경우 디자인 도구에서 자동으로 <xref:System.Data.DataRelation> 개체를 만듭니다.  
  
 예를 들어, Northwind 데이터베이스 같은 고객 및 주문 데이터가 있다고 할 때  `Customers` 테이블에는 다음과 같은 레코드가 포함될 수 있습니다.  
  
```  
CustomerID   CompanyName               City  
ALFKI        Alfreds Futterkiste       Berlin  
ANTON        Antonio Moreno Taquerias  Mexico D.F.  
AROUT        Around the Horn           London  
```  
  
 데이터 집합에는 또한 주문 정보가 들어 있는 다른 테이블이 포함될 수 있습니다.  `Orders` 테이블에는 고객 ID가 외래 키 열로 들어 있습니다.  `Orders` 테이블의 일부 열은 다음과 같습니다.  
  
```  
OrderId    CustomerID    OrderDate  
10692      ALFKI         10/03/1997  
10702      ALFKI         10/13/1997  
10365      ANTON         11/27/1996  
10507      ANTON         4/15/1997  
```  
  
 고객 한 명이 주문을 여러 번 할 수 있으므로 고객과 주문은 일대다 관계입니다.  예를 들어, 위의 테이블에서 고객 ALFKI는 주문을 두 번 했습니다.  
  
 <xref:System.Data.DataRelation> 개체를 사용하여 자식 또는 부모 테이블에서 관련 레코드를 가져올 수 있습니다.  예를 들어, 고객 ANTON에 관한 레코드로 작업하는 경우 이 고객의 주문에 대한 레코드 컬렉션을 불러올 수 있습니다.  자세한 내용은 <xref:System.Data.DataRow.GetChildRows%2A>를 참조하십시오.  마찬가지로 OrderId 10507에 관한 레코드로 작업하는 경우 관계 개체를 탐색하여 부모 ANTON에 대한 레코드를 가져올 수 있습니다.  자세한 내용은 <xref:System.Data.DataRow.GetParentRow%2A>를 참조하십시오.  
  
## 제약 조건  
 대부분의 데이터베이스와 같이 데이터 집합에서는 데이터의 무결성을 보장하기 위한 방법의 하나로 제약 조건을 지원합니다.  제약 조건은 테이블에서 행을 추가, 업데이트 또는 삭제할 때 적용되는 규칙입니다.  다음과 같이 두 종류의 제약 조건을 정의할 수 있습니다.  
  
-   *UNIQUE* 제약 조건. 이 제약 조건은 열의 새 값이 테이블에서 고유한지 검사합니다.  
  
-   *외래 키* 제약 조건. 이 제약 조건은 마스터 테이블의 레코드가 업데이트되거나 삭제되는 경우 관련된 자식 레코드가 업데이트되는 방법에 관한 규칙을 정의합니다.  예를 들어, 외래 키 제약 조건은 자식 레코드를 만들도록 허용하기 전에 부모 레코드가 있는지 확인합니다.  
  
 데이터 집합에서 제약 조건은 개별 테이블\(외래 키 제약 조건\) 또는 열\(해당 열의 값이 고유하다는 것을 보장하는 UNIQUE 제약 조건\)과 관련됩니다.  제약 조건은 <xref:System.Data.UniqueConstraint> 또는 <xref:System.Data.ForeignKeyConstraint> 형식의 개체로 구현된 후  <xref:System.Data.DataTable>의 <xref:System.Data.DataTable.Constraints%2A> 컬렉션에 추가됩니다.  UNIQUE 제약 조건은 단순히 <xref:System.Data.DataColumn>의 <xref:System.Data.DataColumn.Unique%2A> 속성을 `true`로 설정하여 지정할 수도 있습니다.  
  
 데이터 집합에서는 제약 조건의 적용 여부를 지정하는 부울 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성을 지원합니다.  기본적으로 이 속성은 `true`로 설정되어 있습니다.  그러나 제약 조건을 일시적으로 해제하는 것이 유용한 경우가 있습니다.  레코드를 변경함으로 인해 일시적으로 잘못된 상태가 유발될 때가 바로 그러한 경우입니다.  변경 작업을 완료하여 유효한 상태로 돌아간 후에는 제약 조건을 다시 활성화할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 데이터 집합을 정의할 때 암시적으로 제약 조건을 만듭니다.  기본 키를 데이터 집합에 추가하면 기본 키 열에 대한 UNIQUE 제약 조건이 암시적으로 만들어집니다.  <xref:System.Data.DataColumn.Unique%2A> 속성을 `true`로 설정하면 다른 열에 대해서도 UNIQUE 제약 조건을 지정할 수 있습니다.  
  
 데이터 집합에서 <xref:System.Data.DataRelation> 개체를 만들면 외래 키 제약 조건이 만들어집니다.  <xref:System.Data.DataRelation> 개체를 사용하면 관련 레코드에 대한 정보를 프로그래밍 방식으로 가져올 수 있을 뿐만 아니라 외래 키 제약 조건 규칙도 정의할 수 있습니다.  
  
## 데이터 집합 확장 속성  
 확장 속성은 .xsd 파일로부터 데이터 집합을 생성하는 과정에서 이름 충돌 문제가 발생할 경우 이름 매핑을 제공합니다.  .xsd 파일의 식별자가 데이터 집합 생성기에서 만든 컴퓨터 이름과 다르면 `msprop` 네임스페이스의 데이터 집합에 확장 속성이 추가됩니다.  다음 표에서는 생성 가능한 확장 속성을 보여 줍니다.  
  
|개체|확장 속성|  
|--------|-----------|  
|<xref:System.Data.DataSet>|msprop:Generator\_UserDSName|  
||msprop:Generator\_DataSetName|  
|<xref:System.Data.DataTable>|msprop:Generator\_UserTableName|  
||msprop:Generator\_TablePropName|  
||msprop:Generator\_TableVarName|  
||msprop:Generator\_TableClassName|  
||msprop:Generator\_RowClassName|  
||msprop:Generator\_RowEvHandlerName|  
||msprop:Generator\_RowEvArgName|  
|<xref:System.Data.DataColumn>|msprop:Generator\_UserColumnName|  
||msprop:Generator\_ColumnPropNameInTable|  
||msprop:Generator\_ColumnVarNameInTable|  
||msprop:Generator\_ColumnPropNameInRow|  
  
## 참고 항목  
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
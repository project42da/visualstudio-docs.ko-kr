---
title: "데이터 집합의 데이터 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataTable.ColumnChanging"
  - "System.Data.DataTable.ColumnChanging"
  - "System.Data.DataTable.RowChanging"
  - "DataTable.RowChanging"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터 유효성 검사"
  - "데이터 유효성 검사, 데이터 집합"
  - "데이터 집합 업데이트, 데이터 유효성 검사"
  - "데이터 유효성 검사, 데이터 집합"
ms.assetid: 79500596-1e4d-478e-a991-a636fd73a622
caps.latest.revision: 24
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 집합의 데이터 유효성 검사
데이터 유효성 검사는 데이터 개체에 입력할 값이 응용 프로그램에 설정된 규칙 및 데이터 집합의 스키마 제약 조건을 따르는지 확인하는 과정입니다.  업데이트를 내부 데이터베이스에 보내기 전에 데이터의 유효성을 검사하면 응용 프로그램과 데이터베이스 간에 발생할 수 있는 잠재적인 라운드트립 횟수와 오류를 줄일 수 있습니다.  데이터 집합 자체에 유효성 검사 기능을 빌드하여 데이터 집합에 기록되고 있는 데이터가 유효한지 확인할 수 있습니다.  구성 요소 내에서 폼의 컨트롤을 직접 사용하여 업데이트하거나 다른 방식으로 업데이트할 수 있으며, 업데이트 방법에 상관없이 데이터 집합에서 데이터를 검사할 수 있습니다.  데이터 집합은 응용 프로그램의 일부이므로 응용 프로그램 관련 유효성 검사를 빌드하기에 적합한 논리적 위치입니다. 이는 동일한 검사를 데이터베이스 백엔드에 빌드할 때와는 다릅니다.  
  
 응용 프로그램에 유효성 검사를 추가할 때는 데이터 집합의 partial 클래스 파일에 추가하는 것이 좋습니다.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]에서 **데이터 집합 디자이너**를 열고 유효성 검사를 만들 테이블이나 열을 두 번 클릭합니다.  이렇게 하면 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트 처리기가 자동으로 만들어집니다.  자세한 내용은 [방법: 열 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Column%20Changes.md) 또는 [방법: 행 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Row%20Changes.md)를 참조하십시오.  전체 예제는 [연습: 데이터 집합에 유효성 검사 추가](../Topic/Walkthrough:%20Adding%20Validation%20to%20a%20Dataset.md)를 참조하십시오.  
  
## 데이터 유효성 검사  
 데이터 집합 내에서 유효성 검사는 다음과 같이 수행할 수 있습니다.  
  
-   개별 데이터 열의 값이 변경되는 동안 데이터를 검사할 수 있는 응용 프로그램 관련 유효성 검사를 직접 만듭니다.  자세한 내용은 [방법: 열 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Column%20Changes.md)를 참조하십시오.  
  
-   전체 데이터 행이 변경되는 동안 값이 변경될 때 데이터를 검사할 수 있는 응용 프로그램 관련 유효성 검사를 직접 만듭니다.  자세한 내용은 [방법: 행 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Row%20Changes.md)를 참조하십시오.  
  
-   키와 UNIQUE 제약 조건 등을 데이터 집합의 실제 스키마 정의의 일부로 만듭니다.  스키마 정의에 유효성 검사를 통합 하는 방법에 대 한 자세한 내용은 참조 하십시오. [DataColumn이 고유한 값을 가지도록 제한](../Topic/How%20to:%20Add%20Columns%20to%20a%20DataTable.md#SpecifyUniqueConstraint).  
  
-   <xref:System.Data.DataColumn.MaxLength%2A>, <xref:System.Data.DataColumn.AllowDBNull%2A>, <xref:System.Data.DataColumn.Unique%2A>와 같은 <xref:System.Data.DataColumn> 개체의 속성을 설정합니다.  
  
 한 레코드에서 변경이 발생하면 <xref:System.Data.DataTable> 개체에서 여러 개의 이벤트를 발생시킵니다.  
  
-   개별 열에 대해 각 변경이 이루어지는 동안 및 이루어진 후 <xref:System.Data.DataTable.ColumnChanging>과 <xref:System.Data.DataTable.ColumnChanged> 이벤트가 발생합니다.  특정 열의 변경 내용에 대해 유효성을 검사할 경우에는 <xref:System.Data.DataTable.ColumnChanging> 이벤트가 유용합니다.  제안된 변경에 대한 정보가 이벤트의 인수로 전달됩니다.  자세한 내용은 [방법: 열 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Column%20Changes.md)를 참조하십시오.  
  
-   행에서 각 변경이 이루어지는 동안 및 이루어진 후 <xref:System.Data.DataTable.RowChanging>과 <xref:System.Data.DataTable.RowChanged> 이벤트가 발생합니다.  <xref:System.Data.DataTable.RowChanging> 이벤트는 행의 어느 곳에선가 변경이 이루어지고 있다는 것만 표시하므로 좀 더 일반적이지만 어떤 열이 변경되었는지는 알 수 없습니다.  자세한 내용은 [방법: 행 변경 중 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20During%20Row%20Changes.md)를 참조하십시오.  
  
 기본적으로 열에서 변경이 이루어질 때마다 네 개의 이벤트가 발생합니다. 먼저 변경되고 있는 특정 열에 대해 <xref:System.Data.DataTable.ColumnChanging> 및 <xref:System.Data.DataTable.ColumnChanged> 이벤트가 발생하고 그 다음에는 <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowChanged> 이벤트가 발생합니다.  해당 행에서 여러 내용을 변경하는 경우 변경이 이루어질 때마다 이벤트가 발생합니다.  
  
> [!NOTE]
>  데이터 행의 <xref:System.Data.DataRow.BeginEdit%2A> 메서드는 열에 대한 각 변경이 이루어진 후에 <xref:System.Data.DataTable.RowChanging>과 <xref:System.Data.DataTable.RowChanged> 이벤트를 해제합니다.  이 경우 <xref:System.Data.DataRow.EndEdit%2A> 메서드가 호출될 때까지는 이러한 이벤트가 발생하지 않습니다. 따라서 <xref:System.Data.DataTable.RowChanging>과 <xref:System.Data.DataTable.RowChanged> 이벤트는 한 번만 발생합니다.  자세한 내용은 [방법: 데이터 집합을 채우는 동안 제약 조건 해제](../data-tools/turn-off-constraints-while-filling-a-dataset.md)를 참조하십시오.  
  
 이벤트의 선택은 유효성 검사의 복잡성에 따라 달라집니다.  열이 변경되었을 때 오류를 즉시 catch하는 것이 중요한 경우 <xref:System.Data.DataTable.ColumnChanging> 이벤트를 사용하여 유효성 검사를 빌드해야 합니다.  그렇지 않은 경우에는 한번에 여러 오류를 catch하는 <xref:System.Data.DataTable.RowChanging> 이벤트를 사용합니다.  그리고 데이터 구조상, 다른 열의 내용을 기본으로 하여 특정 열 값에 대한 유효성을 검사해야 하는 경우에는 <xref:System.Data.DataTable.RowChanging> 이벤트 동안 유효성 검사를 수행해야 합니다.  
  
 레코드가 업데이트되면 <xref:System.Data.DataTable> 개체는 변경이 이루어지는 동안 및 변경이 이루어진 후에 응답할 수 있는 이벤트를 발생시킵니다.  
  
 사용자 응용 프로그램에서 형식화된 데이터 집합을 사용하고 있으면 강력한 형식의 이벤트 처리기를 만들 수 있습니다.  이렇게 하면 처리기를 만들 수 있는 네 개의 형식화된 이벤트인 `dataTableNameRowChanging`, `dataTableNameRowChanged`, `dataTableNameRowDeleting` 및 `dataTableNameRowDeleted`를 추가할 수 있습니다.  이러한 형식화된 이벤트 처리기는 테이블의 열 이름을 포함하는 인수를 전달하므로 코드를 읽고 쓰기가 더 쉬워집니다.  
  
## 데이터 업데이트 이벤트  
  
|Event|설명|  
|-----------|--------|  
|<xref:System.Data.DataTable.ColumnChanging>|열 값이 변경되고 있습니다.  이 이벤트는 제안된 새 값과 함께 행과 열을 사용자에게 전달합니다.|  
|<xref:System.Data.DataTable.ColumnChanged>|열 값이 변경되었습니다.  이 이벤트는 제안된 값과 함께 행과 열을 사용자에게 전달합니다.|  
|<xref:System.Data.DataTable.RowChanging>|<xref:System.Data.DataRow> 개체의 변경 내용이 데이터 집합으로 다시 커밋될 것입니다.  <xref:System.Data.DataRow.BeginEdit%2A> 메서드를 호출하지 않았으면 <xref:System.Data.DataTable.ColumnChanging> 이벤트가 발생한 직후 열의 각 변경 내용에 대해 <xref:System.Data.DataTable.RowChanging> 이벤트가 발생합니다.  변경하기 전에 <xref:System.Data.DataRow.BeginEdit%2A>을 호출하였으면 <xref:System.Data.DataRow.EndEdit%2A> 메서드를 호출할 때만 <xref:System.Data.DataTable.RowChanging> 이벤트가 발생합니다.<br /><br /> 이 이벤트는 변경, 삽입 등 수행되어야 할 동작 유형을 표시하는 값과 행을 사용자에게 전달합니다.|  
|<xref:System.Data.DataTable.RowChanged>|한 행이 변경되었습니다.  이 이벤트는 변경, 삽입 등 수행되어야 할 동작 유형을 표시하는 값과 행을 사용자에게 전달합니다.|  
|<xref:System.Data.DataTable.RowDeleting>|한 행이 삭제되고 있습니다.  이 이벤트는 수행된 동작 유형\(삭제\)을 표시하는 값과 행을 사용자에게 전달합니다.|  
|<xref:System.Data.DataTable.RowDeleted>|한 행이 삭제되었습니다.  이 이벤트는 수행된 동작 유형\(삭제\)을 표시하는 값과 행을 사용자에게 전달합니다.|  
  
 업데이트 과정 동안 <xref:System.Data.DataTable.ColumnChanging>, <xref:System.Data.DataTable.RowChanging> 및 <xref:System.Data.DataTable.RowDeleting> 이벤트가 발생합니다.  이러한 이벤트를 사용하여 데이터 유효성 검사를 하거나 다른 유형의 처리 작업을 수행할 수 있습니다.  이러한 이벤트 중에 업데이트가 진행되고 있으므로 예외를 throw하여 업데이트 작업을 취소함으로써 변경이 완료되는 것을 막을 수 있습니다.  
  
 <xref:System.Data.DataTable.ColumnChanged>, <xref:System.Data.DataTable.RowChanged> 및 <xref:System.Data.DataTable.RowDeleted> 이벤트는 업데이트가 완료되었을 때 발생하는 알림 이벤트입니다.  업데이트가 성공적으로 이루어진 다음 후속 조치를 취해야 할 때 이러한 이벤트를 유용하게 사용할 수 있습니다.  
  
## 참고 항목  
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [방법: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../Topic/How%20to:%20Validate%20Data%20in%20the%20Windows%20Forms%20DataGridView%20Control.md)   
 [방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시](../Topic/How%20to:%20Display%20Error%20Icons%20for%20Form%20Validation%20with%20the%20Windows%20Forms%20ErrorProvider%20Component.md)
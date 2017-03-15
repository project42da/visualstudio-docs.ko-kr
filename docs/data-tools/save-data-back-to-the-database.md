---
title: "데이터 집합에 데이터 저장 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 저장"
  - "데이터 유효성 검사, 데이터 집합"
  - "데이터 집합[Visual Basic], 데이터 집합 정보"
  - "데이터 집합[Visual Basic], 제약 조건"
  - "데이터 집합[Visual Basic], 병합"
  - "데이터 집합[Visual Basic], 데이터 유효성 검사"
  - "행 버전"
  - "데이터 저장, 데이터 저장 정보"
  - "TableAdapter"
  - "업데이트, 데이터 집합의 제약 조건"
  - "데이터 집합 업데이트, 제약 조건"
ms.assetid: afe6cb8a-dc6a-428b-b07b-903ac02c890b
caps.latest.revision: 27
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 집합에 데이터 저장
데이터 저장은 응용 프로그램에서 변경된 데이터를 원래 데이터 저장소\(일반적으로 SQL Server와 같은 관계형 데이터베이스\)에서 유지할 수 있도록 하는 프로세스입니다.  
  
 데이터 집합은 실제로 데이터의 캐시, 즉 메모리 내의 복사본이므로 원래의 데이터 소스에 정보를 기록하는 과정은 데이터 집합의 데이터를 수정하는 과정과는 별개입니다.  TableAdapter의 `Update` 메서드 중 하나를 호출하거나 TableAdapter의 DBDirect 메서드 중 하나를 호출하여 데이터 집합에 있는 업데이트된 데이터를 데이터베이스에 다시 보낼 수 있습니다.  
  
 데이터 집합의 변경 내용을 다시 데이터베이스로 보내는 방법에 대한 자세한 내용은 [방법: TableAdapter를 사용하여 데이터 업데이트](../data-tools/update-data-by-using-a-tableadapter.md) 및 [방법: 데이터베이스에 데이터 집합 변경 내용 저장](../Topic/How%20to:%20Save%20Dataset%20Changes%20to%20a%20Database.md)을 참조하십시오.  
  
 Visual Studio에서는 데이터를 관련 테이블에 저장할 때 저장 작업을 지원하는 `TableAdapterManager` 구성 요소를 제공합니다.  이 구성 요소의 도움을 받아 저장 작업은 데이터베이스에 정의된 외래 키 제약 조건에 따라 올바른 순서로 수행됩니다.  자세한 내용은 [계층적 업데이트 개요](../Topic/Hierarchical%20Update%20Overview.md)을 참조하십시오.  
  
 데이터 집합의 데이터를 수정하는 방법에 대한 자세한 내용은 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)을 참조하십시오.  
  
## 2단계 업데이트  
 데이터 집합을 통해 데이터 소스를 업데이트하는 과정은 2단계로 이루어집니다.  첫 번째 단계는 새 레코드, 변경된 레코드, 삭제된 레코드와 같은 새로운 정보로 데이터 집합을 업데이트하는 것입니다.  응용 프로그램에서 데이터 집합과 관련된 작업만 수행하는 경우, 즉 데이터 집합을 업데이트한 다음 다른 응용 프로그램에 데이터 집합을 보내 처리 작업을 계속 수행하도록 하는 경우, 업데이트 작업이 종료된 것입니다.  
  
> [!NOTE]
>  Windows Forms에서 데이터 바인딩 아키텍처는 데이터 바인딩된 컨트롤에서 데이터 집합으로 변경 내용을 보내는 일을 맡고 있으므로 코드를 직접 작성하여 데이터 집합을 명시적으로 업데이트하지 않아도 됩니다.  자세한 내용은 [Windows Forms 데이터 바인딩](../Topic/Windows%20Forms%20Data%20Binding.md)을 참조하십시오.  
  
 데이터베이스와 같은 데이터 소스를 업데이트하는 경우 두 번째 단계는 데이터 집합의 변경 내용을 원래의 데이터 소스로 보내는 것입니다.  즉, 데이터 집합을 업데이트하더라도 내부 데이터 소스에 변경 내용이 직접 기록되는 것은 아니므로 이 두 번째 단계를 명시적으로 수행해야 합니다.  한 데이터 소스에서 다른 데이터 소스로 데이터를 이동하거나 여러 데이터 소스를 업데이트할 때는 다른 어댑터를 사용할 수도 있지만, 이 작업을 수행할 때는 데이터 집합을 채울 때 사용했던 것과 동일한 TableAdapter 또는 데이터 어댑터의 Update 메서드를 호출해야 합니다.  
  
 ![Visual Basic 데이터 집합 업데이트](../data-tools/media/vbdatasetupdates.gif "vbDatasetUpdates")  
2단계 업데이트 과정 및 성공적인 업데이트를 위한 DataRowVersion의 역할  
  
 구조적으로 데이터 집합은 데이터를 컬렉션 집합으로 사용할 수 있게 만듭니다.  데이터 집합은 테이블 컬렉션을 포함합니다.  테이블은 행 컬렉션을 포함합니다.  테이블은 <xref:System.Data.DataSet> 개체의 컬렉션으로 노출되며 레코드는 <xref:System.Data.DataTable> 개체의 <xref:System.Data.DataTable.Rows%2A> 컬렉션에서 사용할 수 있습니다.  기본 컬렉션 메서드를 사용하여 이러한 컬렉션을 간단히 조작함으로써 데이터 집합의 데이터를 변경할 수 있지만 내부 데이터 소스를 업데이트하려면 데이터 집합 수정을 위해 특별히 개발된 메서드를 사용해야 합니다.  
  
 예를 들어, 데이터 테이블에서 레코드를 제거하려면 테이블에 있는 <xref:System.Data.DataTable.Rows%2A> 컬렉션의 [RemoveAt 메서드](https://msdn.microsoft.com/en-us/library/system.data.datarowcollection.removeat.aspx)를 호출하여 데이터 집합의 레코드를 물리적으로 삭제합니다.  데이터 집합을 데이터의 구조적 저장소로만 사용하고 변경 정보를 다른 응용 프로그램에 전송하지 않아도 되는 경우, 이러한 방식으로 컬렉션을 조작하는 것은 데이터 집합을 업데이트할 때 허용되는 방식입니다.  
  
 하지만 변경 내용을 데이터 소스나 다른 응용 프로그램에 보내려면 각 업데이트에 대한 변경 정보\(예: 메타데이터\)를 유지해야 합니다.  이렇게 하면 나중에 변경 내용을 데이터 소스나 응용 프로그램으로 보낼 때 프로세스에서 필요한 정보를 사용하여 적절한 레코드를 찾아 업데이트합니다.  예를 들어, 데이터 집합의 레코드를 삭제할 경우 삭제된 데이터에 대한 정보는 데이터 집합에 유지되어야 합니다.  따라서 TableAdapter의 `DeleteCommand`를 호출하면 데이터 소스에서 원래 레코드를 찾는 데 필요한 기록 정보가 있어 원래 레코드를 삭제할 수 있습니다.  자세한 내용은 아래에 있는 "변경 내용에 대한 정보 유지"를 참조하십시오.  
  
## 데이터 집합 병합  
 데이터 집합을 *병합*하여, 즉 *소스* 데이터 집합이라고 하는 한 데이터 집합의 내용을 *대상* 데이터 집합이라고 하는 호출 데이터 집합에 복사하여 데이터 집합의 내용을 업데이트할 수 있습니다.  데이터 집합을 병합할 때 소스 데이터 집합의 새 레코드는 대상 데이터 집합에 추가됩니다.  그리고 소스 데이터 집합에 있는 나머지 열도 대상 데이터 집합에 추가됩니다.  데이터 집합의 병합이 특히 유용한 경우는 로컬 데이터 집합이 있고, XML Web services와 같은 구성 요소 또는 다른 응용 프로그램에서 두 번째 데이터 집합을 가져오거나  여러 데이터 집합의 데이터를 통합하는 경우입니다.  
  
 데이터 집합을 병합할 때 대상 데이터 집합에서 기존의 수정 내용을 유지할 것인지 여부를 <xref:System.Data.DataSet.Merge%2A> 메서드에 알려주는 선택적 부울 인수\(`preserveChanges`\)를 전달할 수도 있습니다.  데이터 집합에서는 레코드의 여러 버전을 유지할 수 있으므로 두 개 이상의 레코드 버전을 병합할 때 이 점을 기억하는 것이 중요합니다.  다음 표에서는 병합할 두 개의 데이터 집합에 있는 한 레코드를 설명합니다.  
  
|DataRowVersion|대상 데이터 집합|소스 데이터 집합|  
|--------------------|---------------|---------------|  
|원래 설정|James Wilson|James C.  Wilson|  
|Current|Jim Wilson|James C.  Wilson|  
  
 위 표에서 `preserveChanges=false targetDataset.Merge(sourceDataset)`를 사용하여 <xref:System.Data.DataSet.Merge%2A> 메서드를 호출하면 다음과 같은 결과가 발생합니다.  
  
|DataRowVersion|대상 데이터 집합|소스 데이터 집합|  
|--------------------|---------------|---------------|  
|원래 설정|James C.  Wilson|James C.  Wilson|  
|Current|James C.  Wilson|James C.  Wilson|  
  
 `preserveChanges = true targetDataset.Merge(sourceDataset, true)`를 사용하여 <xref:System.Data.DataSet.Merge%2A> 메서드를 호출하면 다음과 같은 결과가 발생합니다.  
  
|DataRowVersion|대상 데이터 집합|소스 데이터 집합|  
|--------------------|---------------|---------------|  
|원래 설정|James C.  Wilson|James C.  Wilson|  
|Current|Jim Wilson|James C.  Wilson|  
  
> [!CAUTION]
>  `preserveChanges = true` 시나리오의 경우 대상 데이터 집합의 레코드에서 <xref:System.Data.DataSet.RejectChanges%2A> 메서드가 호출되면 해당 레코드는 *소스* 데이터 집합의 원래 데이터로 되돌려집니다.  이는 대상 데이터 집합으로 원래 데이터 소스를 업데이트하려 할 때 업데이트할 원래 행을 찾을 수 없다는 의미입니다.  그러나 데이터 소스의 업데이트된 레코드를 사용하여 다른 데이터 집합을 채운 다음 병합을 수행하면 동시성 위반을 방지할 수 있습니다. 동시성 위반은 데이터 집합이 채워진 후 다른 사용자가 데이터 소스의 레코드를 수정하면 발생합니다.  
  
## 제약 조건 업데이트  
 기존 데이터 행을 변경하려면 개별 열에 데이터를 추가하거나 업데이트합니다.  데이터 집합에 외래 키나 nullable이 아닌 제약 조건과 같은 제약 조건이 들어 있으면 레코드를 업데이트할 때, 즉 한 열을 업데이트한 후 다음 열을 가져오기 전에 레코드가 일시적으로 오류 상태에 있을 수 있습니다.  
  
 성급한 제약 조건 위반이 발생하는 것을 막으려면 업데이트 제약 조건을 일시적으로 중단할 수 있습니다.  이러한 작업의 목적은 두 가지입니다.  
  
-   다른 열을 가져오기 전에 한 열을 업데이트할 때 오류가 발생하는 것을 throw합니다.  
  
-   주로 유효성 검사에 사용되는 특정 업데이트 이벤트의 발생을 일시 중단시킵니다.  
  
 업데이트를 완료한 다음 제약 조건 검사를 다시 사용할 수 있습니다. 이렇게 하면 업데이트 이벤트도 다시 사용할 수 있으므로 이벤트를 발생시킬 수 있습니다.  
  
> [!NOTE]
>  Windows Forms에서는 데이터 표에 내장된 데이터 바인딩 아키텍처에서 포커스가 행 밖으로 이동할 때까지 제약 조건 검사를 일시 중단시키므로 <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> 또는 <xref:System.Data.DataRow.CancelEdit%2A> 메서드를 명시적으로 호출하지 않아도 됩니다.  
  
 <xref:System.Data.DataSet.Merge%2A> 메서드가 데이터 집합에서 호출되면 제약 조건은 자동으로 사용할 수 없게 됩니다.  병합이 완료될 때 데이터 집합에 사용할 수 없는 제약 조건이 있으면 <xref:System.Data.ConstraintException>이 throw됩니다.  이 경우 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성은 `false`로 설정되며 <xref:System.Data.DataSet.EnforceConstraints%2A> 속성을 `true`로 다시 설정하기 전에 모든 제약 조건 위반을 해결해야 합니다.  
  
 업데이트를 완료한 다음 제약 조건 검사를 다시 사용할 수 있습니다. 이렇게 하면 업데이트 이벤트도 다시 사용할 수 있으므로 이벤트를 발생시킬 수 있습니다.  
  
 이벤트 일시 중단에 대한 자세한 내용은 [방법: 데이터 집합을 채우는 동안 제약 조건 해제](../data-tools/turn-off-constraints-while-filling-a-dataset.md)를 참조하십시오.  
  
## 데이터 집합 업데이트 오류  
 데이터 집합의 레코드를 업데이트할 때 오류가 발생할 가능성이 있습니다.  예를 들어, 잘못된 데이터 형식의 열이나 너무 긴 열 또는 기타 무결성 문제가 있는 열에 데이터를 실수로 기록하는 경우입니다.  또한 업데이트 이벤트 단계에서 사용자 지정 오류를 발생시킬 수 있는 응용 프로그램 관련 유효성 검사를 수행하는 경우도 있습니다.  자세한 내용은 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)을 참조하십시오.  
  
## 변경 내용에 대한 정보 유지  
 데이터 집합의 변경 내용에 대한 정보는 변경 여부를 표시하는 행에 플래그를 설정하거나\(<xref:System.Data.DataRow.RowState%2A>\) 레코드의 여러 복사본을 유지하는\(<xref:System.Data.DataRowVersion>\), 두 가지 방식으로 유지됩니다.  프로세스에서는 이러한 정보를 사용하여 데이터 집합의 변경 내용을 찾아 데이터 소스에 적절한 업데이트를 보냅니다.  
  
### RowState 속성  
 <xref:System.Data.DataRow> 개체의 <xref:System.Data.DataRow.RowState%2A> 속성은 데이터의 특정 행 상태에 대한 정보를 제공하는 값입니다.  
  
 다음 표에서는 <xref:System.Data.DataRowState> 열거형의 가능한 값을 설명합니다.  
  
|DataRowState 값|설명|  
|--------------------|--------|  
|<xref:System.Data.DataRowState>|<xref:System.Data.DataRowCollection>에 열이 항목으로 추가되었습니다. <xref:System.Data.DataRow.AcceptChanges%2A> 메서드가 마지막으로 호출되었을 때 이 상태의 행은 존재하지 않았으므로 이에 해당하는 원래 버전은 없습니다.|  
|<xref:System.Data.DataRowState>|<xref:System.Data.DataRow> 개체의 <xref:System.Data.DataRow.Delete%2A>를 사용하여 행이 삭제되었습니다.|  
|<xref:System.Data.DataRowState>|행이 만들어졌지만 <xref:System.Data.DataRowCollection>의 일부는 아닙니다.  <xref:System.Data.DataRow> 개체는 만들어진 다음 그리고 컬렉션에 추가되기 바로 전에 또는 컬렉션에서 제거되었을 때 이 상태가 됩니다.|  
|<xref:System.Data.DataRowState>|행의 열 값이 어떤 방식으로든 변경되었습니다.|  
|<xref:System.Data.DataRowState>|<xref:System.Data.DataRow.AcceptChanges%2A>가 마지막으로 호출된 이후에 행이 변경되지 않았습니다.|  
  
### DataRowVersion 열거형  
 데이터 집합은 여러 버전의 레코드를 유지합니다.  <xref:System.Data.DataRow> 개체의 <xref:System.Data.DataRowVersion> 열거형은 <xref:System.Data.DataRow> 개체의 특정 버전을 반환하는 데 사용할 수 있는 값입니다.  
  
 다음 표에서는 <xref:System.Data.DataRowVersion> 열거형의 가능한 값을 설명합니다.  
  
|DataRowVersion 값|설명|  
|----------------------|--------|  
|<xref:System.Data.DataRowVersion>|레코드의 현재 버전에는 마지막으로 <xref:System.Data.DataRow.AcceptChanges%2A>가 호출된 이후 레코드에 대해 수행된 모든 수정 내용이 들어 있습니다.  해당 행이 삭제되었으면 현재 버전이 없습니다.|  
|<xref:System.Data.DataRowVersion>|데이터 집합 스키마나 데이터 소스에서 정의한 레코드의 기본값입니다.|  
|<xref:System.Data.DataRowVersion>|레코드의 원래 버전은 데이터 집합에서 변경 내용이 마지막으로 커밋되었을 때의 레코드 복사본입니다.  실질적으로는 데이터 소스에서 가져온 레코드의 버전을 가리킵니다.|  
|<xref:System.Data.DataRowVersion>|업데이트 도중, 즉 <xref:System.Data.DataRow.BeginEdit%2A> 메서드를 호출한 시간과 <xref:System.Data.DataRow.EndEdit%2A> 메서드를 호출한 시간 사이에 일시적으로 사용할 수 있는 레코드의 제안된 버전입니다.  일반적으로 <xref:System.Data.DataTable.RowChanging>과 같은 이벤트의 처리기에서 레코드의 제안된 버전에 액세스합니다.  <xref:System.Data.DataRow.CancelEdit%2A> 메서드를 호출하면 변경 내용이 취소되고 데이터 행의 제안된 버전이 삭제됩니다.|  
  
 업데이트 정보를 데이터 소스에 전송할 때는 원래 버전과 현재 버전을 사용하는 것이 유용합니다.  일반적으로 업데이트를 데이터 소스에 전송할 경우 데이터베이스의 새로운 정보는 레코드의 현재 버전에 있으며  원래 버전의 정보를 사용하여 업데이트할 레코드를 찾습니다.  예를 들어, 레코드의 기본 키가 변경된 경우 변경 내용을 업데이트하려면 데이터 소스에서 적절한 레코드를 찾을 수 있는 방법이 있어야 합니다.  원래 버전이 없으면 레코드가 데이터 소스에 추가되어, 원하지 않는 여분의 레코드와 부정확하고 만료된 레코드가 생성됩니다.  두 개의 버전은 동시성 제어에도 사용됩니다. 데이터 소스의 레코드와 원래 버전을 비교하여 레코드가 데이터 집합에 로드된 이후에 변경되었는지 여부를 확인할 수 있습니다.  
  
 데이터 집합의 변경 내용을 실제로 커밋하기 전에 유효성 검사를 수행할 필요가 있을 때는 제안된 버전이 유용합니다.  
  
 레코드가 변경되었더라도 해당 행의 원래 버전이나 현재 버전이 항상 있는 것은 아닙니다.  새 행을 테이블에 삽입하면 원래 버전은 없고 현재 버전만 있게 됩니다.  마찬가지로 테이블의 `Delete` 메서드를 호출하여 한 행을 삭제하면 현재 버전은 없고 원래 버전만 있게 됩니다.  
  
 데이터 행의 <xref:System.Data.DataRow.HasVersion%2A> 메서드를 쿼리하여 레코드의 특정 버전이 존재하는지 여부를 확인할 수 있습니다.  열의 값을 요청할 때 <xref:System.Data.DataRowVersion> 열거형 값을 선택적 인수로 전달하여 레코드의 버전 중 하나에 액세스할 수 있습니다.  
  
## 변경된 레코드 가져오기  
 일반적으로 데이터 집합의 모든 레코드를 업데이트하지는 않습니다.  예를 들어, 많은 레코드를 표시하는 Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용할 수는 있지만  사용자가 원하는 작업은 몇 개의 레코드만 업데이트하거나 레코드 하나를 삭제하거나 새 레코드 하나를 삽입하는 것입니다.  데이터 집합과 데이터 테이블은 수정된 행만 반환하는 `GetChanges` 메서드를 제공합니다.  
  
 데이터 테이블\(<xref:System.Data.DataTable.GetChanges%2A>\)이나 데이터 집합\(<xref:System.Data.DataSet.GetChanges%2A>\) 자체의 `GetChanges` 메서드를 사용하여 변경된 레코드의 하위 집합을 만들 수 있습니다.  데이터 테이블의 메서드를 호출하면 변경된 레코드만 있는 테이블의 복사본을 반환합니다.  마찬가지로 데이터 집합의 메서드를 호출하면 변경된 레코드만 들어 있는 새 데이터 집합을 가져오게 됩니다.  `GetChanges` 메서드 자체는 변경된 레코드를 모두 반환합니다.  반면, 원하는 <xref:System.Data.DataRowState>를 매개 변수로 하여 `GetChanges` 메서드에 전달하면 새로 추가된 레코드, 삭제 표시된 레코드, 분리된 레코드, 수정된 레코드 등 변경된 레코드에서 원하는 하위 집합을 지정할 수 있습니다.  
  
 변경된 레코드의 하위 집합을 가져오는 것은 처리를 위해 레코드를 다른 구성 요소로 보낼 때 특히 유용합니다.  전체 데이터 집합을 보내는 대신 구성 요소에서 필요로 하는 레코드만 가져옴으로써 다른 구성 요소와의 통신 오버헤드를 줄일 수 있습니다.  자세한 내용은 [방법: 변경된 행 검색](../Topic/How%20to:%20Retrieve%20Changed%20Rows.md)을 참조하십시오.  
  
## 데이터 집합의 변경 내용 커밋  
 데이터 집합이 변경되면 변경된 행의 <xref:System.Data.DataRow.RowState%2A> 속성이 설정됩니다.  레코드의 원래 버전과 현재 버전이 만들어져 유지되므로 <xref:System.Data.DataRowView.RowVersion%2A> 속성을 통해 사용할 수 있습니다.  변경 내용을 나타내는 이러한 속성에 저장되어 있는 메타데이터는 적절한 업데이트를 데이터 소스로 보낼 때 필요합니다.  
  
 변경 내용에서 데이터 소스의 현재 상태를 반영하면 이러한 정보를 더 이상 유지하지 않아도 됩니다.  일반적으로 데이터 집합과 데이터 소스가 동기화되는 경우는 두 가지가 있습니다.  
  
-   소스에서 데이터를 읽어 온 경우와 같이, 데이터 집합으로 정보를 로드한 직후  
  
-   데이터 집합의 변경 내용을 데이터 소스로 보낸 다음. 하지만 변경 내용을 데이터베이스로 보낼 때 필요한 변경 정보를 잃을 수도 있기 때문에 보내기 전 상태는 동기화되지 않습니다.  
  
 <xref:System.Data.DataSet.AcceptChanges%2A> 메서드를 호출하여 데이터 집합에 대해 보류 중인 변경 내용을 커밋할 수 있습니다.  일반적으로 사용자 응용 프로그램에서 다음과 같은 경우에 <xref:System.Data.DataSet.AcceptChanges%2A>가 호출됩니다.  
  
-   데이터 집합을 로드한 다음.  TableAdapter의 `Fill` 메서드를 호출하여 데이터 집합을 로드한 경우 어댑터는 자동으로 변경 내용을 커밋합니다.  그러나 다른 데이터 집합을 병합하여 데이터 집합을 로드한 경우 변경 내용을 수동으로 커밋해야 합니다.  
  
    > [!NOTE]
    >  어댑터의 `AcceptChangesDuringFill` 속성을 `false`로 설정하면 `Fill` 메서드를 호출할 때 어댑터에서 자동으로 변경 내용을 커밋하는 것을 막을 수 있습니다.  `false`로 설정하면 채우기 작업 중에 삽입된 각 행의 <xref:System.Data.DataRow.RowState%2A>는 <xref:System.Data.DataRowState>로 설정됩니다.  
  
-   XML Web services와 같은 다른 프로세스로 데이터 집합 변경 내용을 보냅니다.  
  
    > [!CAUTION]
    >  이런 방식으로 변경 내용을 커밋하면 변경 정보가 지워집니다.  응용 프로그램에서 데이터 집합의 변경 내용을 알아야 하는 작업을 수행할 때까지는 변경 내용을 커밋하지 마십시오.  
  
 이 메서드는 다음과 같은 작업을 수행합니다.  
  
-   원래 버전을 덮어쓰면서 레코드의 <xref:System.Data.DataRowVersion> 버전을 해당 레코드의 <xref:System.Data.DataRowVersion> 버전에 기록합니다.  
  
-   해당 <xref:System.Data.DataRow.RowState%2A> 속성이 <xref:System.Data.DataRowState>로 설정되어 있는 행을 제거합니다.  
  
-   레코드의 <xref:System.Data.DataRow.RowState%2A> 속성을 <xref:System.Data.DataRowState>로 설정합니다.  
  
 <xref:System.Data.DataSet.AcceptChanges%2A> 메서드는 세 가지 수준에서 사용할 수 있으며,  해당 행에 대한 변경 내용만 커밋하는 <xref:System.Data.DataRow> 개체에서 호출할 수 있습니다.  이 메서드는 또한 테이블의 모든 행을 커밋하는 <xref:System.Data.DataTable> 개체에서 호출하거나 데이터 집합의 모든 테이블에 있는 모든 레코드의 보류된 변경 내용을 모두 커밋하는 <xref:System.Data.DataSet> 개체에서 호출할 수 있습니다.  
  
 다음 표에서는 메서드가 호출된 개체에 따라 커밋되는 변경 내용을 설명합니다.  
  
|방법|결과|  
|--------|--------|  
|<xref:System.Data.DataRow.AcceptChanges%2A?displayProperty=fullName>|특정 행에 대해서만 변경 내용이 커밋됩니다.|  
|<xref:System.Data.DataTable.AcceptChanges%2A?displayProperty=fullName>|특정 테이블의 모든 행에 대해서 변경 내용이 커밋됩니다.|  
|<xref:System.Data.DataSet.AcceptChanges%2A?displayProperty=fullName>|데이터 집합의 모든 테이블의 모든 행에 대한 변경 내용이 커밋됩니다.|  
  
> [!NOTE]
>  기본적으로 `Fill` 메서드는 데이터 테이블 채우기를 마치면 `AcceptChanges` 메서드를 호출하므로 TableAdapter의 `Fill` 메서드를 호출하여 데이터 집합을 로드할 때는 변경 내용을 명시적으로 적용할 필요가 없습니다.  
  
 관련 메서드인 `RejectChanges`는 <xref:System.Data.DataRowVersion> 버전을 다시 레코드의 <xref:System.Data.DataRowVersion> 버전으로 복사하고 각 레코드의 <xref:System.Data.DataRow.RowState%2A>를 다시 <xref:System.Data.DataRowState>로 설정합니다.  
  
## 데이터 유효성 검사  
 응용 프로그램의 데이터가 사용자에게 전달된 프로세스의 요구 사항에 부합하는지 확인하려면 유효성 검사를 추가해야 합니다.  여기에서는 사용자가 폼에 입력한 데이터가 올바른지 검사하거나, 다른 응용 프로그램에서 사용자 응용 프로그램에 보낸 데이터를 검사하거나, 사용자 구성 요소에서 계산한 정보가 데이터 소스의 제약 조건과 응용 프로그램 요구 사항에 맞는지를 검사합니다.  
  
 다음과 같은 몇 가지 방식으로 데이터의 유효성을 검사할 수 있습니다.  
  
-   비즈니스 계층에서 데이터 유효성을 검사하는 코드를 응용 프로그램에 추가합니다.  데이터 집합은 이러한 작업을 수행할 수 있는 장소 중 하나로,  열과 행 값이 변경될 때 변경 내용의 유효성을 검사할 수 있는 기능 같은 백 엔드 유효성 검사의 이점을 일부 제공합니다.  자세한 내용은 [데이터 집합의 데이터 유효성 검사](../data-tools/validate-data-in-datasets.md)을 참조하십시오.  
  
-   프레젠테이션 계층에서 폼에 유효성 검사를 추가합니다.  자세한 내용은 [Windows Forms에서 사용자 입력 유효성 검사](../Topic/User%20Input%20Validation%20in%20Windows%20Forms.md)을 참조하십시오.  
  
-   데이터 백 엔드에서 데이터베이스와 같은 데이터 소스에 데이터를 보내고 데이터 소스에서 데이터를 허용하거나 거부하도록 합니다.  데이터 유효성 검사를 하여 오류 정보를 제공하는 복잡한 기능을 갖는 데이터베이스를 사용하는 경우 데이터의 수집 위치에 상관없이 데이터 유효성 검사를 할 수 있으므로 실용적인 방법이 될 수 있습니다.  하지만 데이터베이스에서 응용 프로그램 관련 요구 사항을 수용하지 않을 수도 있습니다.  그리고 데이터 소스에서 데이터의 유효성 검사를 하게 하면 백 엔드에서 발생하는 유효성 검사 오류를 응용 프로그램에서 해결하는 방법에 따라 데이터 소스에 대한 라운드트립이 여러 번 발생할 수 있습니다.  
  
    > [!IMPORTANT]
    >  <xref:System.Data.SqlClient.SqlCommand.CommandType%2A> 속성을 <xref:System.Data.CommandType>로 설정한 상태에서 데이터 명령을 사용하는 경우, 클라이언트에서 전송된 정보를 데이터베이스에 전달하기 전에 이 정보를 자세히 검사해야 합니다.  악의적인 사용자가 데이터베이스에 무단으로 액세스하거나 데이터베이스를 훼손하기 위해 수정된 SQL 문이나 추가적인 SQL 문을 전송\(주입\)할 수도 있습니다.  사용자 입력을 데이터베이스에 전송하기 전에 항상 정보의 유효성을 검사해야 합니다. 가능하면 항상 매개 변수가 있는 쿼리나 저장 프로시저를 사용하는 것이 좋습니다.  자세한 내용은 [Script Exploits Overview](../Topic/Script%20Exploits%20Overview.md)을 참조하십시오.  
  
 데이터 집합을 변경한 다음 변경 내용을 데이터 소스에 전송할 수 있습니다.  가장 일반적인 방법은 TableAdapter 또는 데이터 어댑터의 `Update` 메서드를 호출하는 것입니다.  메서드는 데이터 테이블의 각 레코드에서 반복되어 업데이트, 삽입, 삭제 중 필요한 업데이트 유형을 결정한 다음 적절한 명령을 실행합니다.  
  
## 데이터 소스로 업데이트를 전송하는 방법  
 업데이트가 이루어지는 모습을 그려 보기 위해, 응용 프로그램에서 하나의 데이터 테이블이 들어 있는 데이터 집합을 사용하고 있다고 가정합시다.  응용 프로그램에서는 데이터베이스에서 두 개의 행을 페치합니다.  검색이 수행된 후 메모리 내의 데이터 테이블 모양은 다음과 같습니다.  
  
```  
(RowState)     CustomerID   Name             Status  
(Unchanged)    c200         Robert Lyon      Good  
(Unchanged)    c400         Nancy Buchanan    Pending  
```  
  
 응용 프로그램에서 Nancy Buchanan의 상태를 "Preferred"로 바꿉니다. 이러한 변경이 이루어지면 해당 행의 <xref:System.Data.DataRow.RowState%2A> 속성이 <xref:System.Data.DataRowState>에서 <xref:System.Data.DataRowState>로 변경됩니다.  첫 행의 <xref:System.Data.DataRow.RowState%2A> 속성 값은 <xref:System.Data.DataRowState>로 남아 있습니다.  이제 데이터 테이블의 모양은 다음과 같습니다.  
  
```  
(RowState)     CustomerID   Name             Status  
(Unchanged)    c200         Robert Lyon      Good  
(Modified)     c400         Nancy Buchanan    Preferred  
```  
  
 이제 응용 프로그램에서 `Update` 메서드를 호출하여 데이터 집합을 데이터베이스로 전송합니다.  메서드에서는 각 행을 차례로 검사합니다.  첫 행의 경우 데이터베이스에서 처음 페치된 이후에 변경되지 않았기 때문에 메서드에서 데이터베이스로 SQL 문을 보내지 않습니다.  
  
 하지만 두 번째 행에 대해서는 `Update` 메서드가 적절한 데이터 명령을 자동으로 호출하여 데이터베이스로 전송합니다.  SQL 문의 특정 구문은 내부 데이터 저장소에서 지원하는 SQL 언어에 따라 달라집니다.  전송된 SQL 문과 관련하여 주목해야 하는 일반적인 특성은 다음과 같습니다.  
  
-   전송된 SQL 문은 UPDATE 문입니다.  <xref:System.Data.DataRow.RowState%2A> 속성 값이 <xref:System.Data.DataRowState>이므로 어댑터에서 UPDATE 문을 사용한다는 것을 알 수 있습니다.  
  
-   전송된 SQL 문에는 UPDATE 문의 대상이 `CustomerID = 'c400'`인 행임을 표시하는 WHERE 절을 포함합니다.  `CustomerID`가 대상 테이블의 기본 키이므로 SELECT 문의 이러한 부분은 대상 행을 다른 행과 구분합니다.  WHERE 절의 정보는 레코드의 원래 버전\(`DataRowVersion.Original`\)에서 파생된 것으로 변경된 행을 식별하기 위해 필요한 값입니다.  
  
-   전송된 SQL 문에는 수정된 열의 새 값을 설정하는 SET 절이 포함됩니다.  
  
    > [!NOTE]
    >  TableAdapter의 `UpdateCommand` 속성이 저장 프로시저의 이름으로 설정되어 있는 경우 어댑터에서는 SQL 문을 생성하지 못하고,  대신 적절한 매개 변수를 전달하여 저장 프로시저를 호출합니다.  
  
## 매개 변수 전달  
 데이터베이스에서 업데이트되어야 하는 레코드의 값은 대개 매개 변수를 사용하여 전달됩니다.  TableAdapter의 `Update` 메서드가 UPDATE 문을 실행하는 경우 매개 변수 값을 채워야 합니다.  데이터 어댑터는 적절한 데이터 명령의 `Parameters` 컬렉션에서 값을 가져오는데, 여기서는 TableAdapter의 `UpdateCommand` 개체가 데이터 명령입니다.  
  
 Visual Studio 도구를 사용하여 데이터 어댑터를 생성하였다면 `UpdateCommand` 개체에 해당 문의 각 매개 변수 자리 표시자에 해당하는 매개 변수 컬렉션이 포함됩니다.  
  
 각 매개 변수의 <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A?displayProperty=fullName> 속성은 데이터 테이블의 한 열을 가리킵니다.  예를 들어, `au_id` 및 `Original_au_id` 매개 변수의 `SourceColumn` 속성은 author id가 들어 있는 데이터 테이블의 열로 설정됩니다.  어댑터의 `Update` 메서드가 실행되면 업데이트 중인 레코드의 author id 열을 읽어 해당 문에 값을 채웁니다.  
  
 UPDATE 문에서는 레코드에 기록될 새 값과 업데이트할 레코드를 데이터베이스에서 찾을 때 사용할 이전 값을 모두 지정해야 합니다.  따라서 각 값에는 두 개의 매개 변수가 있습니다. 한 매개 변수는 SET 절에서 사용되고 다른 매개 변수는 WHERE 절에서 사용됩니다.  두 매개 변수 모두 업데이트 중인 레코드에서 데이터를 가져오지만 매개 변수의 [SqlParameter.SourceVersion 속성](https://msdn.microsoft.com/en-us/library/system.data.sqlclient.sqlparameter.sourceversion.aspx)에 따라 다른 버전의 열 값을 가져옵니다.  SET 절의 매개 변수는 현재 버전을 가져오고 WHERE 절의 매개 변수는 원래 버전을 가져옵니다.  
  
> [!NOTE]
>  코드에서 `Parameters` 컬렉션의 값을 직접 설정할 수도 있습니다. 이 작업은 일반적으로 데이터 어댑터의 <xref:System.Data.DataTable.RowChanging> 이벤트에 대한 이벤트 처리기에서 수행합니다.  
  
## 관련 테이블 업데이트  
 데이터 집합에 여러 테이블이 있으면 각 데이터 어댑터의 `Update` 메서드를 별도로 호출하여 테이블을 개별적으로 업데이트해야 합니다.  테이블에 부모\-자식 관계가 있으면 특정 순서로 데이터베이스에 업데이트를 보내야 합니다.  일반적인 시나리오는 데이터 집합에 부모 레코드와 관련 자식 레코드를 모두 추가하는 것입니다. 하나의 새 고객 레코드에 한 개 이상의 관련 주문 레코드가 있는 경우가 이 경우에 해당됩니다.  데이터베이스 자체에서 관계 무결성 규칙을 적용하고 있는 경우, 부모 레코드를 만들지 않은 채 데이터베이스에 새로운 자식 레코드를 보내면 오류가 발생합니다.  
  
 반대로, 데이터 집합에서 관련 레코드를 삭제하는 경우에는 역순으로, 자식 테이블에 먼저 업데이트를 보낸 다음에 부모 테이블에 업데이트를 보내야 합니다.  그렇지 않은 경우 참조 무결성 규칙에서 관련 자식 레코드가 남아 있을 때 부모 레코드를 삭제하는 것을 방지하므로 오류가 발생합니다.  
  
 관련 테이블에 업데이트를 보내는 일반적인 규칙은 다음과 같은 순서를 따릅니다.  
  
1.  자식 테이블: 레코드 삭제  
  
2.  부모 테이블: 레코드 삽입, 업데이트 및 삭제  
  
3.  자식 테이블: 레코드 삽입 및 업데이트  
  
4.  자세한 내용은 [연습: 데이터베이스에 데이터 저장\(여러 테이블\)](../data-tools/save-data-to-a-database-multiple-tables.md)을 참조하십시오.  
  
## 동시성 제어  
 데이터 집합은 데이터 소스와 연결되어 있지 않기 때문에 데이터 소스의 레코드에 대해 잠금을 설정할 수 없습니다.  따라서 데이터베이스를 업데이트하려는 경우 응용 프로그램에서 동시성 제어를 유지하는 것이 중요하다면 데이터 집합의 레코드를 데이터베이스의 레코드와 조정해야 합니다.  예를 들어, 마지막으로 데이터 집합을 채운 이후에 데이터베이스의 레코드가 변경되었는지 확인해야 합니다.  이 경우 응용 프로그램에 적합한 논리를 실행하여 데이터베이스 레코드나 데이터 집합의 변경된 레코드를 처리할 방법을 지정해야 합니다.  
  
## 참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: TableAdapter를 사용하여 데이터 업데이트](../data-tools/update-data-by-using-a-tableadapter.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
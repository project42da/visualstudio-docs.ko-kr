---
title: "방법: 데이터 집합에서 변경 내용 커밋 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DataSet.AcceptChanges"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터 집합[Visual Basic], 변경 내용 커밋"
ms.assetid: 51931353-4d22-4e35-a9ef-6f2b44e1f7d9
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: 데이터 집합에서 변경 내용 커밋
레코드를 업데이트, 삽입, 삭제하여 데이터 집합의 레코드를 변경할 때 데이터 집합은 레코드의 원래 버전과 현재 버전을 유지합니다.  또한 각 행의 <xref:System.Data.DataRow.RowState%2A> 속성은 레코드가 원래 상태에 있는지 또는 업데이트나 삽입, 삭제되었는지 여부를 추적합니다.  이러한 정보는 행의 특정 버전을 찾아야 할 때 유용합니다.  일반적으로 변경된 레코드를 다른 프로세스로 보내려면 변경된 모든 레코드의 하위 집합을 가져와야 합니다.  자세한 내용은 [방법: 변경된 행 검색](../Topic/How%20to:%20Retrieve%20Changed%20Rows.md)을 참조하십시오.  변경된 행을 모두 처리한 다음에는 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataRow>의 `AcceptChanges` 메서드를 호출하여 변경 내용을 커밋할 수 있습니다.  `AcceptChanges` 메서드는 [TableAdapter](../data-tools/tableadapter-overview.md) 또는 데이터 어댑터의 업데이트 메서드를 호출할 때 자동으로 호출됩니다.  변경 내용을 데이터베이스로 커밋한 후 `AcceptChanges`를 호출합니다.  
  
 <xref:System.Data.DataSet>에 대해 <xref:System.Data.DataSet.AcceptChanges%2A>를 호출해도 편집 모드 상태인 모든 <xref:System.Data.DataRow> 개체의 편집이 성공적으로 완료됩니다.  또한 각 <xref:System.Data.DataRow>의 <xref:System.Data.DataRow.RowState%2A> 속성도 변경되어 <xref:System.Data.DataRowState> 및 <xref:System.Data.DataRowState> 행은 <xref:System.Data.DataRowState>로 바뀌고 <xref:System.Data.DataRowState> 행은 제거됩니다.  
  
 <xref:System.Data.DataSet>에 <xref:System.Data.ForeignKeyConstraint> 개체가 있는 경우 <xref:System.Data.DataSet.AcceptChanges%2A> 메서드를 호출하면 <xref:System.Data.AcceptRejectRule>도 적용됩니다.  
  
### 데이터 집합에서 변경 내용을 커밋하려면  
  
-   <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 <xref:System.Data.DataRow>에 대해 `AcceptChanges` 메서드를 호출하여 해당 개체의 변경 내용을 커밋합니다.  
  
     다음 예제에서는 `AcceptChanges` 메서드를 호출하여 데이터 소스를 업데이트한 다음 `Customers` 테이블의 변경 내용을 커밋하는 방법을 보여 줍니다.  
  
     [!code-cs[VbRaddataEditing#11](../data-tools/codesnippet/CSharp/how-to-commit-changes-in-a-dataset_1.cs)]
     [!code-vb[VbRaddataEditing#11](../data-tools/codesnippet/VisualBasic/how-to-commit-changes-in-a-dataset_1.vb)]  
  
## 참고 항목  
 <xref:System.Data.DataSet.AcceptChanges%2A?displayProperty=fullName>   
 <xref:System.Data.DataTable.AcceptChanges%2A?displayProperty=fullName>   
 <xref:System.Data.DataRow.AcceptChanges%2A?displayProperty=fullName>   
 [데이터 저장](../data-tools/saving-data.md)   
 [방법: 변경된 행 검색](../Topic/How%20to:%20Retrieve%20Changed%20Rows.md)
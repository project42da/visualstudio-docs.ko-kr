---
title: "데이터 집합에서의 관계 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbData.Microsoft.VSDesigner.DataSource.DesignRelation"
  - "vbdata.Microsoft.VSDesigner.DataSource.DesignRelation"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터 집합[Visual Basic], 관계"
  - "관계, 관계 정보"
  - "관계, 데이터 집합"
ms.assetid: cfe274f0-71fe-40f6-994e-7c7f6273c9ba
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 집합에서의 관계
데이터 집합에는 관계형 데이터베이스 같은 관련 테이블이 포함될 수 있습니다.  데이터 테이블 간의 관계를 맺어주는 개체를 **DataRelation** 개체라고 합니다.  다음 항목에서는 ADO.NET **DataRelation** 개체의 개요, 이 개체를 만드는 방법 그리고 이 개체를 사용하여 관련 테이블의 데이터를 처리하는 방법에 대해 설명합니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 단원 내용  
 [DataRelation 개체 소개](../Topic/Introduction%20to%20DataRelation%20Objects.md)  
 데이터 집합에서 테이블들 간의 관계를 지정하는 방법 및 이들 관계를 활용하는 방법을 간략하게 설명합니다.  
  
 [방법: 데이터 집합 디자이너를 사용하여 DataRelation 만들기](../Topic/How%20to:%20Create%20DataRelations%20with%20the%20Dataset%20Designer.md)  
 **데이터 집합 디자이너**를 사용하여 <xref:System.Data.DataRelation> 개체를 데이터 집합에 추가하는 방법을 설명합니다.  
  
 [방법: 관련 DataTable의 레코드에 액세스](../Topic/How%20to:%20Access%20Records%20in%20Related%20DataTables.md)  
 일대다 관계의 테이블을 사용하여 형식화된 데이터 집합의 관련 레코드를 프로그래밍 방식으로 반환하는 방법을 설명합니다.  
  
 [연습: 데이터 테이블 간의 관계 만들기](../Topic/Walkthrough:%20Creating%20a%20Relationship%20between%20Data%20Tables.md)  
 **데이터 집합 디자이너**를 사용하여 두 개의 데이터 테이블을 만들고 둘 사이에 관계를 추가하는 방법을 단계별로 설명합니다.  
  
## 참조  
 <xref:System.Data.DataRelation>  
 두 T:System.Data.DataTable 개체 사이의 부모\/자식 관계를 나타냅니다.  
  
 <xref:System.Data.DataRow.GetChildRows%2A>  
 T:System.Data.DataRow의 자식 행을 가져옵니다.  
  
 <xref:System.Data.DataRow.GetParentRow%2A>  
 T:System.Data.DataRow의 부모 행을 가져옵니다.  
  
 <xref:System.Data.Rule>  
 <xref:System.Data.ForeignKeyConstraint>가 적용될 때 발생하는 동작을 나타냅니다.  
  
 <xref:System.Data.DataColumn.Unique%2A>  
 열의 각 행 값이 고유해야 하는지 여부를 나타내는 값을 가져오거나 설정합니다.  
  
 <xref:System.Data.Constraint>  
 하나 이상의 <xref:System.Data.DataColumn> 개체에 적용할 수 있는 제약 조건을 나타냅니다.  
  
## 관련 단원  
 [DataRelations 추가](../Topic/Adding%20DataRelations.md)  
 <xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 만드는 방법에 대해 설명합니다.  
  
 [DataRelations 탐색](../Topic/Navigating%20DataRelations.md)  
 <xref:System.Data.DataSet>에 있는 테이블 사이의 관계를 사용하여 부모\-자식 관계의 자식 또는 부모 행을 반환하는 방법에 대해 설명합니다.  
  
 [DataRelations 중첩](../Topic/Nesting%20DataRelations.md)  
 <xref:System.Data.DataSet> 내용을 XML 데이터로 표현할 경우 중첩된 <xref:System.Data.DataRelation> 개체의 중요성과 이 개체를 만드는 방법에 대해 설명합니다.
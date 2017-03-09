---
title: "방법: TableAdapter 쿼리 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "데이터[Visual Studio], TableAdapter 쿼리"
  - "쿼리[Visual Studio], 만들기"
  - "쿼리[Visual Studio], TableAdapter"
  - "TableAdapter, 쿼리 만들기"
ms.assetid: df0cf4a5-e9cc-4de6-8b94-ce74fb7b2452
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: TableAdapter 쿼리 만들기
TableAdapter 쿼리는 응용 프로그램에서 데이터베이스에 대해 실행할 수 있는 SQL 문 또는 저장 프로시저입니다.  
  
 TableAdapter에 응용 프로그램에 필요한 만큼의 쿼리를 추가합니다.  TableAdapter 쿼리는 TableAdapter에 메서드로 나타납니다.  도시 값을 나타내는 매개 변수를 사용하는 `FillByCity`라는 쿼리를 만들면 이 쿼리는 TableAdapter에  올바른 형식의 매개 변수를 인수로 사용하는 형식화된 메서드로 추가됩니다. 이 경우 도시 값을 나타내는 문자열입니다.  TableAdapter 쿼리는 특정 개체의 특정 메서드처럼 호출됩니다.  예를 들어, 다음 코드는 `FillByCity` 쿼리를 실행하고 `Customers` 테이블을 도시 값이 `Seattle`로 설정된 모든 고객으로 채웁니다.  
  
 [!code-vb[VbRaddataTableAdapters#1](../data-tools/codesnippet/VisualBasic/how-to-create-tableadapter-queries_1.vb)]
 [!code-cs[VbRaddataTableAdapters#1](../data-tools/codesnippet/CSharp/how-to-create-tableadapter-queries_1.cs)]  
  
 TableAdapter 쿼리는 데이터 테이블\(`Fill` 및 `FillBy` 쿼리\)을 채우거나 쿼리\(`GetData` 및 `GetDataBy` 쿼리\)에 의해 반환된 데이터로 채워진 새 데이터 테이블을 반환할 수 있습니다.  
  
 [TableAdapter 쿼리 구성 마법사](../data-tools/editing-tableadapters.md)를 실행하여 기존 TableAdapter에 쿼리를 추가할 수 있습니다.  이렇게 하려면 TableAdapter를 마우스 오른쪽 단추로 클릭하고 **Query 추가**를 선택하면 됩니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## 데이터 집합 디자이너에서 쿼리 열기  
  
#### 데이터 집합 디자이너의 TableAdapter에 쿼리를 추가하려면  
  
1.  **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)를 참조하십시오.  
  
2.  원하는 TableAdapter를 마우스 오른쪽 단추로 클릭하고 **Query 추가**를 선택합니다.  
  
     또는  
  
3.  **도구 상자**의 **데이터 집합** 탭에서 디자이너로 **Query**를 끌어 옵니다.  
  
     **TableAdapter 쿼리 구성 마법사**가 열립니다.  
  
4.  마법사를 완료합니다. 쿼리가 TableAdapter에 추가됩니다.  
  
## Windows 응용 프로그램의 폼에서 쿼리 직접 만들기  
 폼에 TableAdapter의 인스턴스가 있으면 [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)를 사용하여 쿼리를 추가할 수 있습니다. 이 대화 상자에서는 쿼리에 필요한 입력 매개 변수를 받는 폼에 쿼리를 실행하는 단추뿐 아니라 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 추가합니다.  
  
#### 검색 기준 대화 상자를 사용하여 TableAdapter에 쿼리를 추가하려면  
  
1.  구성 요소 트레이에서 TableAdapter를 선택합니다.  
  
2.  TableAdapter의 스마트 태그를 클릭하고 **Query 추가**를 선택합니다.  
  
3.  대화 상자를 완료합니다. 그러면 TableAdapter에 쿼리가 추가됩니다.  자세한 내용은 [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)를 참조하십시오.  
  
## 참고 항목  
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [방법: TableAdapter 쿼리 편집](../data-tools/how-to-edit-tableadapter-queries.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 탐색](../Topic/How%20to:%20Navigate%20Data%20with%20the%20Windows%20Forms%20BindingNavigator%20Control.md)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [연습: 여러 개의 쿼리가 있는 TableAdapter 만들기](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)
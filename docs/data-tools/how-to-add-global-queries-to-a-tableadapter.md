---
title: "방법: 데이터 집합에 전역 쿼리 추가 | Microsoft Docs"
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
  - "데이터[Visual Studio], TableAdapter"
  - "데이터 집합[Visual Basic], 전역 함수"
  - "데이터 집합[Visual Basic], 스칼라 함수"
  - "전역 함수, 데이터 집합"
  - "쿼리[Visual Studio], TableAdapter"
  - "스칼라 함수, 데이터 집합"
  - "TableAdapter 쿼리"
  - "TableAdapter 쿼리 구성 마법사"
  - "TableAdapter, 전역 쿼리"
ms.assetid: 4abffd6b-2e9f-4ef3-99b2-6e9ae4ad4679
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: 데이터 집합에 전역 쿼리 추가
*전역 쿼리*는 값을 반환하지 않거나 단일\(스칼라\) 값을 반환하는 SQL 쿼리입니다.  일반적으로 전역 함수는 삽입, 업데이트, 삭제 및 정보의 집계\(예: 테이블의 고객 수 반환, 모든 항목의 총 금액을 특정 순서로 반환 등\)와 같은 데이터베이스 작업을 수행합니다.  
  
 **데이터 집합 디자이너**에서 **TableAdapter 쿼리 구성 마법사**를 실행하여 전역 쿼리를 추가할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### 데이터 집합에 전역 쿼리를 추가하려면  
  
1.  **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)를 참조하십시오.  
  
2.  **도구 상자**의 **데이터 집합** 탭에서 **Query**를 **데이터 집합 디자이너**의 빈 곳으로 끌어 옵니다.  
  
     [TableAdapter 쿼리 구성 마법사](../data-tools/editing-tableadapters.md)가 열립니다.  
  
3.  사용할 쿼리의 연결을 선택합니다.  목록에서 선택하거나 새 연결을 만들 수 있습니다.  새 연결을 만드는 경우 연결을 응용 프로그램 구성 파일에 저장할 수 있습니다.  자세한 내용은 [방법: 연결 문자열 저장 및 편집](../Topic/How%20to:%20Save%20and%20Edit%20Connection%20Strings.md)을 참조하십시오.  
  
4.  SQL 문을 사용할지 저장 프로시저를 사용할지 선택합니다.  
  
5.  사용할 저장 프로시저를 선택하거나 마법사의 **쿼리 형식 선택** 페이지에서 원하는 쿼리 형식을 선택한 후 **다음**을 클릭합니다.  
  
6.  `SELECT COUNT(*) AS CustomerCount FROM Customers`와 같은 원하는 작업을 수행하는 쿼리를 제공합니다.  
  
    > [!NOTE]
    >  쿼리를 직접 **데이터 집합 디자이너**로 끌어 놓으면 하나의 스칼라\(단일\) 값만 반환하는 메서드가 만들어집니다.  선택한 쿼리나 저장 프로시저에서는 여러 값을 반환할 수 있지만 마법사에 의해 만들어진 메서드에서는 단일 값만 반환합니다.  예를 들어, 쿼리에서 반환된 데이터에 대한 첫 번째 행의 첫 번째 열을 반환할 수 있습니다.  
  
7.  마법사를 완료합니다. 쿼리가 **데이터 집합 디자이너**에 추가됩니다.  쿼리 실행에 대한 자세한 내용은 [방법: TableAdapter 쿼리 실행](../Topic/How%20to:%20Execute%20TableAdapter%20Queries.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)   
 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 탐색](../Topic/How%20to:%20Navigate%20Data%20with%20the%20Windows%20Forms%20BindingNavigator%20Control.md)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)
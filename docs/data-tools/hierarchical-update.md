---
title: "계층적 업데이트 | Microsoft Docs"
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
  - "데이터[Visual Basic], 계층적 업데이트"
  - "데이터 집합[Visual Basic], 계층적 업데이트"
  - "계층적 업데이트"
  - "수정된 데이터 저장"
  - "관계 테이블, 저장"
  - "데이터 저장, 변경된 데이터"
  - "데이터 저장, 계층적 업데이트"
  - "업데이트된 데이터 저장"
  - "업데이트된 데이터 저장"
ms.assetid: 68bae3f6-ec9b-45ee-a33a-69395029f54c
caps.latest.revision: 26
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 계층적 업데이트
*계층적 업데이트*란 참조 무결성 규칙을 유지하면서 업데이트된 데이터\(두 개 이상의 관련 테이블이 있는 데이터 집합의 데이터\)를 다시 데이터베이스로 저장하는 프로세스를 가리킵니다.  *참조 무결성*이란 데이터베이스의 제약 조건이 제공하는 일관성 규칙을 가리키는 것으로, 관련 레코드의 삽입, 업데이트 및 삭제 동작을 제어합니다.  예를 들어 어떤 고객에 대한 주문을 만들 수 있는 상태가 되기 전에 그 고객 레코드를 만들도록 하는 것이 참조 무결성입니다.  
  
 관련 데이터 테이블의 수정된 데이터를 저장하는 것은 단일 테이블의 데이터를 저장하는 것보다 조금 더 복잡합니다.  참조 무결성 제약 조건을 위반하지 않기 위해 각 관련 테이블에 대한 업데이트, 삽입 및 삭제 명령을 특정 순서로 실행해야 하기 때문입니다.  기존 고객과 신규 고객, 주문을 모두 관리할 수 있는 주문 입력 응용 프로그램을 예로 들어보겠습니다.  기존 고객을 삭제해야 하는 경우 먼저 고객의 모든 주문을 삭제한 다음에 고객 레코드를 삭제해야 합니다.  신규 고객을 주문과 함께 추가하는 경우 테이블에 있는 외래 키 제약 조건 때문에 먼저 신규 고객 레코드를 먼저 삽입한 다음에 해당 고객의 주문을 삽입해야 합니다.  이 예에서 볼 수 있듯이 참조 무결성을 유지하려면 데이터의 특정 하위 집합을 추출하고 업데이트\(삽입, 업데이트 및 삭제\)를 전송해야 합니다.  
  
 계층적 업데이트 기능은 `TableAdapterManager`를 사용하여 `TableAdapter`를 형식화된 데이터 집합으로 관리합니다.  `TableAdapterManager` 구성 요소는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 생성되는 구성 요소이므로 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]의 일부가 아닙니다.  `TableAdapterManager` 클래스에 대한 자세한 내용은 [TableAdapterManager 개요](../Topic/TableAdapterManager%20Overview.md)의 "TableAdapterManager 참조" 단원을 참조하십시오.  
  
 응용 프로그램에서 형식화된 데이터 집합을 사용하고 사용자가 관련 데이터 테이블\(Customers, Orders와 같은 일대다 관계의 데이터 테이블\)의 데이터를 수정할 수 있는 경우 계층적 업데이트를 사용하는 것이 좋을 수 있습니다.  
  
## 단원 내용  
 [계층적 업데이트 개요](../Topic/Hierarchical%20Update%20Overview.md)  
 계층적 업데이트의 정의를 설명하고 구현 방법을 자세히 설명합니다.  
  
 [TableAdapterManager 개요](../Topic/TableAdapterManager%20Overview.md)  
 `TableAdapterManager`의 정의를 설명하고 데이터 집합 디자이너에서 생성되는 `TableAdapterManager` 코드를 설명합니다.  
  
 [방법: 계층적 업데이트 활성화 및 비활성화](../Topic/How%20to:%20Enable%20and%20Disable%20Hierarchical%20Update.md)  
 형식화된 데이터 집합의 `Hierarchical Update` 속성을 설정하여 관련 테이블을 저장하는 코드를 생성하는 방법을 설명합니다.  
  
 [방법: 데이터 집합의 외래 키 제약 조건 구성](../Topic/How%20to:%20Configure%20Foreign-Key%20Constraints%20in%20a%20Dataset.md)  
 데이터 집합에서 제약 조건을 구성하는 방법을 설명합니다.  
  
 [방법: 데이터 바인딩된 컨트롤에서 데이터를 저장하기 전에 In\-Process 편집 커밋](../data-tools/commit-in-process-edits-on-data-bound-controls-before-saving-data.md)  
 폼의 데이터 바인딩된 컨트롤에서 모든 in\-process 편집을 중지하고 데이터 소스 저장을 준비하는 방법을 설명합니다.  
  
 [방법: 계층적 업데이트를 수행하는 경우 순서 설정](../Topic/How%20to:%20Set%20the%20Order%20When%20Performing%20a%20Hierarchical%20Update.md)  
 `TableAdapterManager`의 `UpdateOrder` 속성을 설정하여 삽입, 업데이트 및 삭제가 수행되는 순서를 제어하는 방법을 설명합니다.  
  
 [방법: 기존 Visual Studio 프로젝트에서 계층적 업데이트 구현](../Topic/How%20to:%20Implement%20Hierarchical%20Update%20in%20Existing%20Visual%20Studio%20Projects.md)  
 `TableAdapterManager`에서 관련 데이터 테이블이 있는 응용 프로그램을 업그레이드하여 데이터를 저장하는 방법을 설명합니다.  
  
 [연습: 관련 데이터 테이블의 데이터 저장\(계층적 업데이트\)](../Topic/Walkthrough:%20Saving%20Data%20from%20Related%20Data%20Tables%20\(Hierarchical%20Update\).md)  
 `TableAdapterManager`를 사용하여 관련 데이터 테이블이 있는 응용 프로그램을 만들고 데이터를 저장하는 방법을 단계별로 설명합니다.  
  
## 참조  
 <xref:System.Data.DataSet>  
  
 <xref:System.Data.DataTable>  
  
## 관련 단원  
 [N 계층 응용 프로그램에서 데이터 집합 작업 작업](../data-tools/work-with-datasets-in-n-tier-applications.md)  
  
 [데이터 저장](../data-tools/saving-data.md)  
  
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)  
  
 [TableAdapter](../Topic/TableAdapters.md)  
  
 [DataSets, DataTables 및 DataViews](../Topic/DataSets,%20DataTables,%20and%20DataViews.md)  
  
 [DataTables](../Topic/DataTables.md)  
  
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)
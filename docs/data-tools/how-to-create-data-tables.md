---
title: "방법: 데이터 테이블 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Microsoft.VSDesigner.DataSource.DesignTable"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "aspx"
helpviewer_keywords: 
  - "데이터[Visual Studio], 데이터 테이블 만들기"
  - "데이터 집합 디자이너, 데이터 테이블 만들기"
  - "테이블[Visual Studio], 만들기"
ms.assetid: 0e8bf4c4-3d05-4b20-9926-9d29914b26ed
caps.latest.revision: 19
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: 데이터 테이블 만들기
데이터는 <xref:System.Data.DataTable> 개체의 메모리에 저장할 수 있습니다. 데이터 집합은 <xref:System.Data.DataTable> 개체로 구성되어 있습니다. [TableAdapter 구성 마법사](../Topic/TableAdapter%20Configuration%20Wizard.md)를 사용하거나 데이터베이스 개체를 **서버 탐색기**에서 **데이터 집합 디자이너**로 끌어서 놓아 TableAdapter가 있는 새 데이터 테이블을 만듭니다.  
  
 데이터 테이블은 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)에 새 TableAdapter를 만들 때 부수적으로 만들어지기도 하지만 독립적으로 만들 수도 있습니다.  **도구 상자**의 **데이터 집합** 탭에서 <xref:System.Data.DataTable> 개체를 **데이터 집합 디자이너**로 끌어서 놓아 독립 실행형 데이터 테이블을 만듭니다.  
  
> [!NOTE]
>  프로그래밍 방식으로 데이터 테이블을 만들려면 [DataTable 만들기](../Topic/Creating%20a%20DataTable.md)를 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## TableAdapter가 있는 DataTable 만들기  
 TableAdapter가 있는 데이터 테이블에는 테이블에 데이터를 입력하고 변경 내용을 다시 데이터베이스에 쓰는 메서드가 포함됩니다.  **TableAdapter 구성 마법사**를 실행하거나 데이터베이스 개체를 **서버 탐색기**에서 **데이터 집합 디자이너**로 끌어서 놓아 TableAdapter를 만듭니다.  
  
#### TableAdapter가 있는 새 데이터 테이블을 만들려면  
  
1.  **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)를 참조하십시오.  
  
2.  **TableAdapter**를 **도구 상자**의 **DataSet** 탭에서 **데이터 집합 디자이너**로 끌어서 놓습니다.  
  
     **TableAdapter 구성 마법사**가 열립니다.  
  
3.  마법사에서 필요한 작업을 완료합니다.  자세한 내용은 [TableAdapter 구성 마법사](../Topic/TableAdapter%20Configuration%20Wizard.md)을 참조하십시오.  
  
#### 서버 탐색기에서 TableAdapter가 있는 새 데이터 테이블을 만들려면  
  
1.  **데이터 소스 디자이너**에서 데이터 집합을 엽니다.  
  
2.  테이블 등의 데이터베이스 개체를 **서버 탐색기**에서 **데이터 집합 디자이너**로 끌어서 놓습니다.  
  
## 독립 실행형 DataTable 만들기  
 독립 실행형 테이블을 데이터로 채우려면 `Fill` 논리가 구현되어 있어야 합니다.  독립 실행형 데이터 테이블 채우기에 대한 자세한 내용은 [DataAdapter에서 DataSet 채우기](../Topic/Populating%20a%20DataSet%20from%20a%20DataAdapter.md)를 참조하십시오.  
  
#### 새 독립 실행형 데이터 테이블을 만들려면  
  
1.  **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  
  
2.  <xref:System.Data.DataTable>을 **도구 상자**의 **데이터 집합** 탭에서 **데이터 집합 디자이너**로 끌어 옵니다.  
  
3.  열을 추가하여 데이터 테이블을 정의합니다.  자세한 내용은 [방법: DataTable에 열 추가](../Topic/How%20to:%20Add%20Columns%20to%20a%20DataTable.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Data.DataTable>   
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [데이터 소스 창](../Topic/Data%20Sources%20Window.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)
---
title: "연습: 데이터 집합 디자이너에서 DataTable 만들기 | Microsoft Docs"
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
  - "데이터[Visual Studio], 데이터 집합 디자이너"
  - "데이터 집합 디자이너, 데이터 테이블 만들기"
  - "DataTable 개체, 만들기"
  - "테이블[Visual Studio], 만들기"
ms.assetid: abf0a2b5-e4e5-422e-97ef-55a0e35a82df
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 연습: 데이터 집합 디자이너에서 DataTable 만들기
이 연습에서는 **데이터 집합 디자이너**를 사용하여 TableAdapter 없이 <xref:System.Data.DataTable>을 만드는 방법에 대해 설명합니다.  TableAdapter를 포함하는 데이터 테이블 만들기에 대한 자세한 내용은 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)를 참조하십시오.  
  
 이 연습에서 수행할 작업은 다음과 같습니다.  
  
-   새 Windows 응용 프로그램 프로젝트 만들기  
  
-   응용 프로그램에 새 데이터 집합 추가  
  
-   데이터 집합에 새 데이터 테이블 추가  
  
-   데이터 테이블에 열 추가  
  
-   테이블의 기본 키 설정  
  
## 새 Windows 응용 프로그램 만들기  
  
#### 새로운 Windows 응용 프로그램 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 새 프로젝트를 만듭니다.  
  
2.  **프로젝트 형식** 창에서 프로그래밍 언어를 선택합니다.  
  
3.  **템플릿** 창에서 **Windows 응용 프로그램**을 클릭합니다.  
  
4.  프로젝트의 이름을 `DataTableWalkthrough`로 지정한 다음 **확인**을 클릭합니다.  
  
     프로젝트가 **솔루션 탐색기**에 추가되고 **Form1**이 디자이너에 표시됩니다.  
  
## 응용 프로그램에 새 데이터 집합 추가  
  
#### 프로젝트에 새 데이터 집합 항목을 추가하려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
     새 항목 추가 대화 상자가 나타납니다.  
  
2.  **템플릿** 상자에서 **데이터 집합**을 선택합니다.  
  
3.  **추가**를 클릭합니다.  
  
     그러면 **DataSet1.xsd** 파일이 프로젝트에 추가되어 **데이터 집합 디자이너**에 열립니다.  
  
## 데이터 집합에 새 DataTable 추가  
  
#### 데이터 집합에 새 데이터 테이블을 추가하려면  
  
1.  **DataTable**을 **도구 상자**의 **데이터 집합** 탭에서 **데이터 집합 디자이너**로 끌어 옵니다.  
  
     **DataTable1**이라는 테이블이 데이터 집합에 추가됩니다.  
  
    > [!NOTE]
    >  TableAdapter를 포함하는 데이터 테이블을 만들려면 [연습: 여러 개의 쿼리가 있는 TableAdapter 만들기](../data-tools/walkthrough-creating-a-tableadapter-with-multiple-queries.md)를 참조하십시오.  
  
2.  **DataTable1**의 제목 표시줄을 클릭하고 이름을 `Music`으로 바꿉니다.  
  
## 데이터 테이블에 열 추가  
  
#### 데이터 테이블에 열을 추가하려면  
  
1.  **Music** 테이블을 마우스 오른쪽 단추로 클릭합니다.  **추가**를 가리킨 다음 **열**을 클릭합니다.  
  
2.  열 이름을 `SongID`로 지정합니다.  
  
3.  **속성** 창에서 <xref:System.Data.DataColumn.DataType%2A> 속성을 <xref:System.Int16?displayProperty=fullName>로 설정합니다.  
  
4.  이 과정을 반복하여 다음 열을 추가합니다.  
  
     `SongTitle`: <xref:System.String?displayProperty=fullName>  
  
     `Artist`: <xref:System.String?displayProperty=fullName>  
  
     `Genre`: <xref:System.String?displayProperty=fullName>  
  
## 테이블의 기본 키 설정  
 모든 데이터 테이블에는 기본 키가 있어야 합니다.  기본 키는 데이터 테이블의 특정 레코드를 고유하게 식별합니다.  
  
#### 데이터 테이블의 기본 키를 설정하려면  
  
-   **SongID** 열을 마우스 오른쪽 단추로 클릭한 다음 **기본 키 설정**을 클릭합니다.  
  
     **SongID** 열 옆에 열쇠 모양 아이콘이 표시됩니다.  
  
## 프로젝트 저장  
  
#### DataTableWalkthrough 프로젝트를 저장하려면  
  
-   **파일** 메뉴에서 **모두 저장**을 클릭합니다.  
  
## 다음 단계  
 테이블을 만들었으므로 다음 작업 중 하나를 수행할 수 있습니다.  
  
|To|참조|  
|--------|--------|  
|데이터를 입력할 폼 만들기|[연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md).|  
|테이블에 데이터 추가|[DataTable에 데이터 추가](../Topic/Adding%20Data%20to%20a%20DataTable.md).|  
|테이블에서 데이터 보기|[DataTable에서 데이터 보기](../Topic/Viewing%20Data%20in%20a%20DataTable.md).|  
|데이터 편집|[DataTable 편집](../Topic/DataTable%20Edits.md)|  
|테이블에서 행 삭제|[DataRow 삭제](../Topic/DataRow%20Deletion.md)|  
  
## 참고 항목  
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)   
 [데이터 연습](../Topic/Data%20Walkthroughs.md)
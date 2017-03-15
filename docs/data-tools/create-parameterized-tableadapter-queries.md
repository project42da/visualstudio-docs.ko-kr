---
title: "방법: 매개 변수가 있는 TableAdapter 쿼리 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "09/21/2016"
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
  - "데이터[Visual Studio], 데이터 검색"
  - "데이터[Visual Studio], TableAdapter"
  - "쿼리[Visual Studio], 만들기"
  - "쿼리[Visual Studio], TableAdapter"
  - "TableAdapter, 매개 변수가 있는 쿼리"
  - "TableAdapter, 데이터 검색"
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
caps.latest.revision: 20
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 매개 변수가 있는 TableAdapter 쿼리 만들기
매개 변수가 있는 쿼리는 쿼리의 WHERE 절 조건을 충족하는 데이터를 반환합니다.  예를 들어 고객 목록을 반환하는 SQL 문 끝에 `WHERE City = @City`를 추가하여 특정 구\/군\/시의 고객만 표시하도록 고객 목록을 매개 변수화할 수 있습니다.  
  
 매개 변수가 있는 TableAdapter 쿼리는 [데이터 집합 디자이너](../data-tools/creating-and-editing-typed-datasets.md)에서 만들거나 **데이터** 메뉴의 **데이터 소스 매개 변수화** 명령을 사용하여 Windows 응용 프로그램에서 데이터 바인딩된 폼을 만들 때 만듭니다.  또한 **데이터 소스 매개 변수화** 명령은 매개 변수 값을 입력하기 위한 컨트롤을 폼에 만들고 쿼리를 실행합니다.  자세한 내용은 [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)을 참조하십시오.  
  
> [!NOTE]
>  매개 변수가 있는 쿼리를 생성할 때는 코딩 대상 데이터베이스에 맞는 매개 변수 표기법을 사용합니다.  예를 들어 Access 및 OleDb 데이터 소스는 물음표 '?'를 사용하여 매개 변수를 표기하므로 WHERE 절은 `WHERE City = ?`와 같습니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 매개 변수가 있는 TableAdapter 쿼리 만들기  
  
#### 데이터 집합 디자이너에서 매개 변수가 있는 쿼리를 만들려면  
  
-   원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 새 TableAdapter를 만듭니다.  자세한 내용은 [방법: TableAdapter 만들기](../data-tools/create-and-configure-tableadapters.md)을 참조하십시오.  
  
     또는  
  
-   원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 기존 TableAdapter에 쿼리를 추가합니다.  자세한 내용은 [방법: TableAdapter 쿼리 만들기](../data-tools/how-to-create-tableadapter-queries.md)를 참조하세요.  
  
#### 데이터 바인딩된 폼을 디자인하면서 매개 변수가 있는 쿼리를 만들려면  
  
1.  데이터 집합에 이미 바인딩되어 있는 폼의 컨트롤을 선택합니다.  자세한 내용은 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)을 참조하십시오.  
  
2.  **데이터** 메뉴에서 **쿼리 추가**를 클릭합니다.  
  
3.  원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 **검색 조건 작성기** 대화 상자에서 필요한 작업을 완료합니다.  자세한 내용은 [검색 조건 작성기 대화 상자](../Topic/Search%20Criteria%20Builder%20Dialog%20Box.md)을 참조하십시오.  
  
## 참고 항목  
 [TableAdapter](../Topic/TableAdapters.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)   
 [데이터 연습](../Topic/Data%20Walkthroughs.md)
---
title: "방법: TableAdapter 구성 마법사 시작 | Microsoft Docs"
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
  - "TableAdapter 구성 마법사"
  - "TableAdapter, 구성 마법사"
ms.assetid: 301f2dcd-ed72-4229-80ef-3b59cb062d5d
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
robots: noindex,nofollow
---
# 방법: TableAdapter 구성 마법사 시작
**TableAdapter 구성 마법사**는 강력한 형식의 데이터 집합에서 TableAdapter를 만들고 편집합니다.  이 마법사는 사용자가 마법사에 입력하는 SQL 문 또는 데이터베이스의 기존 저장 프로시저를 기반으로 TableAdapter를 만듭니다.  또한 사용자가 마법사에 입력하는 SQL 문을 기반으로 데이터베이스에 새 저장 프로시저를 만들 수도 있습니다.  
  
### TableAdapter 구성 마법사를 시작하여 새 TableAdapter를 만들려면  
  
1.  **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)을 참조하십시오.  
  
    > [!NOTE]
    >  프로젝트에 데이터 집합이 없으면 [방법: 형식화된 데이터 집합 만들기](../data-tools/create-and-configure-datasets-in-visual-studio.md)를 참조하세요.  
  
2.  새 TableAdapter를 만드는 경우 **도구 상자**의 **데이터 집합** 탭에서 **TableAdapter** 개체를 **데이터 집합 디자이너**로 끌어 옵니다.  
  
3.  **데이터 연결 선택** 페이지의 현재 사용 가능한 연결 목록에서 데이터 연결을 선택하거나 **새 연결**을 선택하여 새 연결을 만듭니다.  
  
### TableAdapter 구성 마법사를 시작하여 기존 TableAdapter를 편집하려면  
  
1.  **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  자세한 내용은 [방법: 데이터 집합 디자이너에서 데이터 집합 열기](../Topic/How%20to:%20Open%20a%20Dataset%20in%20the%20Dataset%20Designer.md)을 참조하십시오.  
  
2.  **데이터 집합 디자이너**에서 TableAdapter를 마우스 오른쪽 단추로 클릭하고 **구성**을 선택합니다.  TableAdapter를 원래 구성한 방식에 따라 마법사에서 **SQL 문 생성** 페이지 또는 **기존 저장 프로시저에 명령 바인딩** 페이지가 열립니다.  
  
3.  마법사에서 필요한 작업을 완료합니다.  
  
## 참고 항목  
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [TableAdapter 개요](../data-tools/tableadapter-overview.md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [방법: 데이터베이스의 데이터에 연결](../data-tools/how-to-connect-to-data-in-a-database.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [방법: Windows Forms BindingSource 구성 요소를 사용하여 ADO.NET 데이터 정렬 및 필터링](../Topic/How%20to:%20Sort%20and%20Filter%20ADO.NET%20Data%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)   
 [방법: Windows Forms BindingSource 구성 요소를 사용하여 조회 테이블 만들기](../Topic/How%20to:%20Create%20a%20Lookup%20Table%20with%20the%20Windows%20Forms%20BindingSource%20Component.md)   
 [연습: Windows Form에 데이터 표시](../data-tools/walkthrough-displaying-data-on-a-windows-form.md)
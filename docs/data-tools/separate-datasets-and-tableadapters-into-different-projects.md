---
title: "방법: 데이터 집합 및 TableAdapter를 다른 프로젝트로 분리 | Microsoft Docs"
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
  - "n 계층 응용 프로그램, 데이터 집합과 TableAdapter 분리"
  - "TableAdapter, n 계층 응용 프로그램"
ms.assetid: f66a3940-6227-46af-a930-9177f425f4fd
caps.latest.revision: 18
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 데이터 집합 및 TableAdapter를 다른 프로젝트로 분리
형식화된 데이터 집합은 [TableAdapter](../Topic/TableAdapters.md) 및 데이터 집합 클래스를 별도의 프로젝트로 생성할 수 있도록 향상되었습니다.  이를 통해 응용 프로그램 계층을 빠르게 분리하고 N 계층 데이터 응용 프로그램을 만들 수 있습니다.  
  
 다음 절차에서는 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)를 사용하여 생성된 `TableAdapter` 코드가 포함된 프로젝트와 분리된 프로젝트로 데이터 집합 코드를 생성하는 프로세스를 설명합니다.  
  
## 데이터 집합과 TableAdapter 분리  
 데이터 집합 코드와 `TableAdapter` 코드를 분리할 때는 데이터 집합 코드가 포함될 프로젝트가 현재 솔루션에 있어야 합니다.  이 프로젝트가 현재 솔루션에 있지 않으면 **속성** 창의 **데이터 집합 프로젝트** 목록에 표시되지 않습니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### 데이터 집합을 여러 다른 프로젝트로 분리하려면  
  
1.  데이터 집합\(.xsd 파일\)이 포함된 솔루션을 엽니다.  
  
    > [!NOTE]
    >  데이터 집합 코드를 분리할 프로젝트가 솔루션에 포함되지 않은 경우에는 새로 만들거나 기존 프로젝트를 솔루션에 추가합니다.  
  
2.  **솔루션 탐색기**에서 형식화된 데이터 집합 파일\(.xsd 파일\)을 두 번 클릭하여 **데이터 집합 디자이너**에서 데이터 집합을 엽니다.  
  
3.  **데이터 집합 디자이너**의 빈 곳을 클릭합니다.  
  
4.  **속성** 창에서 **데이터 집합 프로젝트** 노드를 찾습니다.  
  
5.  **데이터 집합 프로젝트** 목록에서 데이터 집합 코드를 생성할 대상 프로젝트의 이름을 클릭합니다.  
  
     데이터 집합 코드를 생성할 대상 프로젝트를 클릭하면 **데이터 집합 파일** 속성에 기본 파일 이름이 입력됩니다.  필요한 경우 이 이름을 변경할 수 있습니다.  또한 데이터 집합 코드를 특정 디렉터리에 생성하려면 **프로젝트 폴더** 속성을 폴더 이름으로 설정하면 됩니다.  
  
    > [!NOTE]
    >  **데이터 집합 프로젝트** 속성을 설정하여 데이터 집합과 TableAdapter를 분리할 때 프로젝트의 기존 partial 데이터 집합 클래스는 자동으로 이동하지 않습니다.  기존의 데이터 집합 partial 클래스는 데이터 집합 프로젝트에 수동으로 옮겨야 합니다.  
  
6.  데이터 집합을 저장합니다.  
  
     데이터 집합 코드가 **데이터 집합 프로젝트** 속성에서 선택된 프로젝트로 생성되고 **TableAdapter** 코드가 현재 프로젝트로 생성됩니다.  
  
 기본적으로 데이터 집합과 `TableAdapter` 코드를 분리하면 각 프로젝트에 별개의 클래스 파일이 생성됩니다.  원래 프로젝트에는 `TableAdapter` 코드가 포함된 DatasetName.Designer.vb\(또는 DatasetName.Designer.cs\)라는 파일이 남습니다.  **데이터 집합 프로젝트** 속성에 지정된 프로젝트에는 데이터 집합 코드가 포함된 DatasetName.DataSet.Designer.vb\(또는 DatasetName.DataSet.Designer.cs\)라는 파일이 추가됩니다.  
  
> [!NOTE]
>  데이터 집합 또는 `TableAdapter` 프로젝트를 선택한 상태에서 **솔루션 탐색기**의 **모든 파일 표시**를 클릭하면 생성된 클래스 파일을 볼 수 있습니다.  
  
## 참고 항목  
 [N 계층 데이터 응용 프로그램 개요](../data-tools/n-tier-data-applications-overview.md)   
 [연습: N 계층 데이터 응용 프로그램 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)   
 [계층적 업데이트](../data-tools/hierarchical-update.md)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)   
 [ADO.NET](../Topic/ADO.NET.md)
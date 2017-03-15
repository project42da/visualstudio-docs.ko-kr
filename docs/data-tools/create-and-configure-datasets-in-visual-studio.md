---
title: "방법: 형식화된 데이터 집합 만들기 | Microsoft Docs"
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
  - "데이터 집합[Visual Basic], 만들기"
  - "형식화된 데이터 집합, 만들기"
ms.assetid: 58f33b43-24e1-43b1-b08b-b74329960bd6
caps.latest.revision: 36
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 형식화된 데이터 집합 만들기
**데이터 소스 구성 마법사** 또는 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)를 사용하여 형식화된 <xref:System.Data.DataSet>을 만듭니다.  
  
> [!NOTE]
>  프로그래밍 방식으로 데이터 집합을 만드는 방법에 대한 자세한 내용은 [DataSet 만들기](../Topic/Creating%20a%20DataSet.md)를 참조하십시오.  
  
## 데이터 소스 구성 마법사 또는 데이터 집합 디자이너를 사용하여 형식화된 데이터 집합 만들기  
  
#### 데이터 소스 구성 마법사로 데이터 집합을 만들려면  
  
1.  **데이터** 메뉴에서 **새 데이터 소스 추가**를 클릭하여 **데이터 소스 구성 마법사**를 시작합니다.  
  
2.  **데이터 소스 형식 선택** 페이지에서 **데이터베이스**를 선택합니다.  
  
3.  마법사를 완료하면 형식화된 데이터 집합이 프로젝트에 추가됩니다.  자세한 내용은 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png)를 참조하십시오.  
  
#### 데이터 집합 디자이너로 데이터 집합을 만들려면  
  
1.  **프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **데이터 집합**을 선택합니다.  
  
3.  데이터 집합의 이름을 입력합니다.  
  
4.  **추가**를 클릭합니다.  
  
     데이터 집합이 프로젝트에 추가되고 **데이터 집합 디자이너**에 열립니다.  
  
5.  **도구 상자**의 **데이터 집합** 탭에서 디자이너로 항목을 끌어 옵니다.  자세한 내용은 [방법: 데이터 집합 편집](../Topic/How%20to:%20Edit%20a%20Dataset.md)을 참조하십시오.  
  
     또는  
  
     **서버 탐색기**\/**데이터베이스 탐색기**의 활성 연결에서 **데이터 집합 디자이너**로 항목을 끌어 옵니다.  
  
## 참고 항목  
 [연습: 데이터베이스의 데이터에 연결\(Windows Forms\)](../Topic/Walkthrough:%20Connecting%20to%20Data%20in%20a%20Database%20\(Windows%20Forms\).md)   
 [형식화된 데이터 집합 만들기 및 편집](../data-tools/creating-and-editing-typed-datasets.md)   
 [방법: 데이터 집합 편집](../Topic/How%20to:%20Edit%20a%20Dataset.md)   
 [TableAdapter](../Topic/TableAdapters.md)   
 [데이터 집합에서의 관계](../data-tools/relationships-in-datasets.md)   
 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)
---
title: "데이터 집합의 데이터 편집 | Microsoft Docs"
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
  - "데이터[Visual Studio], 데이터 집합에서 편집"
  - "데이터 집합[Visual Basic], 데이터 편집"
ms.assetid: 50d5c580-fbf7-408f-be70-e63ac4f4d0eb
caps.latest.revision: 15
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터 집합의 데이터 편집
<xref:System.Data.DataSet>에서 데이터를 편집하는 것은 데이터 집합을 구성하는 개별 <xref:System.Data.DataTable> 개체에서 실제 데이터를 조작하는 프로세스입니다.  임의의 데이터베이스에서 테이블의 데이터를 편집하는 것처럼 데이터 테이블의 데이터를 편집합니다. 이 프로세스에는 테이블에서 레코드를 삽입, 업데이트 및 삭제하는 작업이 포함될 수 있습니다.  
  
 <xref:System.Data.DataTable>을 조회하면 실제 데이터에 대한 변경 외에 개별 행과 같은 특정 데이터 행, 행의 특정 버전\(원본 및 제안\), 변경된 행 및 오류가 있는 행을 반환할 수도 있습니다.  
  
## 일반 데이터 테이블 작업  
 다음 테이블은 데이터 집합의 데이터 편집 및 조회와 연관된 일반 작업에 대한 링크를 제공합니다.  
  
|Task|설명|  
|----------|--------|  
|데이터 테이블에 새 레코드를 삽입합니다.|새 <xref:System.Data.DataRow>를 만들고 테이블의 행 컬렉션에 추가합니다.  자세한 내용은 [방법: DataTable에 행 추가](../Topic/How%20to:%20Add%20Rows%20to%20a%20DataTable.md)을 참조하십시오.|  
|데이터 테이블에서 기존 레코드를 업데이트합니다.|데이터 행의 특정 열에 직접 값을 지정합니다.  자세한 내용은 [방법: DataTable의 행 편집](../Topic/How%20to:%20Edit%20Rows%20in%20a%20DataTable.md)을 참조하십시오.|  
|데이터 테이블에서 기존 레코드를 삭제합니다.|테이블에서 제거할 데이터 행의 <xref:System.Data.DataRow.Delete%2A> 메서드를 호출합니다.  자세한 내용은 [방법: DataTable에서 행 삭제](../Topic/How%20to:%20Delete%20Rows%20in%20a%20DataTable.md)을 참조하십시오.|  
|데이터 테이블에서 변경된 레코드를 찾습니다.|데이터 테이블의 <xref:System.Data.DataTable.GetChanges%2A> 메서드를 호출합니다.  자세한 내용은 [방법: 변경된 행 검색](../Topic/How%20to:%20Retrieve%20Changed%20Rows.md)을 참조하십시오.|  
|데이터 테이블에서 다른 버전의 행에 액세스합니다.|보려는 <xref:System.Data.DataRowVersion>을 전달하여 데이터 행의 개별 열에 액세스합니다.  자세한 내용은 [방법: DataRow의 특정 버전 가져오기](../Topic/How%20to:%20Get%20Specific%20Versions%20of%20a%20DataRow.md)을 참조하십시오.|  
|데이터 테이블에서 오류가 있는 행을 찾습니다.|데이터 테이블의 <xref:System.Data.DataTable.HasErrors%2A> 속성을 검사합니다.  자세한 내용은 [방법: 오류가 있는 행 찾기](../Topic/How%20to:%20Locate%20Rows%20that%20Have%20Errors.md)을 참조하십시오.|  
  
## 참고 항목  
 [DataTables](../Topic/DataTables.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [DataTables](../Topic/DataTables.md)   
 [데이터 연습](../Topic/Data%20Walkthroughs.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Visual Studio의 데이터 응용 프로그램 개요](../data-tools/overview-of-data-applications-in-visual-studio.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
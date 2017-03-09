---
title: "방법: 데이터 집합을 XML로 저장 | Microsoft Docs"
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
  - "데이터[Visual Studio], XML로 저장"
  - "데이터 집합[Visual Basic], XML로 저장"
  - "데이터 저장"
  - "XML[Visual Basic], 데이터 집합"
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
caps.latest.revision: 11
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 데이터 집합을 XML로 저장
데이터 집합의 XML 데이터는 데이터 집합에서 사용할 수 있는 XML 메서드를 호출하여 액세스할 수 있습니다.  데이터를 XML 형식으로 저장하려면 <xref:System.Data.DataSet>의 <xref:System.Data.DataSet.GetXml%2A> 메서드 또는 <xref:System.Data.DataSet.WriteXml%2A> 메서드를 호출하면 됩니다.  
  
 <xref:System.Data.DataSet.GetXml%2A> 메서드를 호출하면 XML 형식의 데이터 집합의 모든 데이터 테이블에서 데이터가 포함된 문자열이 반환됩니다.  
  
 <xref:System.Data.DataSet.WriteXml%2A> 메서드를 호출하면 XML 형식 데이터를 사용자가 지정하는 파일로 보냅니다.  
  
### 데이터 집합의 데이터를 XML로서 변수에 저장하려면  
  
-   <xref:System.Data.DataSet.GetXml%2A> 메서드는 <xref:System.String>을 반환하므로 <xref:System.String> 형식의 변수를 선언하고 <xref:System.Data.DataSet.GetXml%2A> 메서드의 결과를 지정합니다.  
  
     [!code-vb[VbRaddataSaving#12](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_1.vb)]
     [!code-cs[VbRaddataSaving#12](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_1.cs)]  
  
### 데이터 집합의 데이터를 XML로서 파일에 저장하려면  
  
-   <xref:System.Data.DataSet.WriteXml%2A> 메서드에는 여러 오버로드가 있습니다.  다음 코드에서는 데이터를 파일에 저장하고 변수를 선언한 다음 파일을 저장할 올바른 경로를 지정하는 방법을 보여 줍니다.  
  
     [!code-vb[VbRaddataSaving#13](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_2.vb)]
     [!code-cs[VbRaddataSaving#13](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_2.cs)]  
  
## 참고 항목  
 [DataSets, DataTables 및 DataViews](../Topic/DataSets,%20DataTables,%20and%20DataViews.md)   
 [Visual Studio의 XML 도구](../xml-tools/xml-tools-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [Visual Studio에서 데이터에 연결](../data-tools/connecting-to-data-in-visual-studio.md)   
 [데이터를 받기 위해 응용 프로그램 준비](../Topic/Preparing%20Your%20Application%20to%20Receive%20Data.md)   
 [데이터를 응용 프로그램으로 페치](../data-tools/fetching-data-into-your-application.md)   
 [Visual Studio에서 데이터에 컨트롤 바인딩](../data-tools/bind-controls-to-data-in-visual-studio.md)   
 [응용 프로그램에서 데이터 편집](../data-tools/editing-data-in-your-application.md)   
 [데이터 유효성 검사](../Topic/Validating%20Data.md)   
 [데이터 저장](../data-tools/saving-data.md)
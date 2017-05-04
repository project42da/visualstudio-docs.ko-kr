---
title: "방법: 데이터베이스의 데이터로 워크시트 채우기 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "데이터[Visual Studio에서 Office 개발], 워크시트에 추가"
  - "데이터베이스[Visual Studio에서 Office 개발], 워크시트 채우기"
  - "워크시트[Visual Studio에서 Office 개발], 채우기"
ms.assetid: e9e37cf1-53ca-45d0-8409-5428be7f96c5
caps.latest.revision: 39
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 38
---
# 방법: 데이터베이스의 데이터로 워크시트 채우기
  Windows Forms 프로젝트의 데이터를 액세스 하는 동일한 방법으로 문서 수준 Office 프로젝트의에서 데이터를 액세스할 수 있습니다.  동일한 도구와 코드를 사용하여 데이터를 솔루션에 가져올 수 있고 Windows Forms 컨트롤을 사용하여 데이터를 표시할 수도 있습니다.  또한 이벤트 및 데이터 바인딩 기능이 향상된 Microsoft Office Excel의 네이티브 개체인 호스트 컨트롤이라는 컨트롤을 사용할 수도 있습니다.  자세한 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 다음 예제에서는 디자이너를 사용하여 문서 수준 프로젝트에서 데이터 바인딩된 컨트롤을 추가하는 방법을 보여 줍니다.  런타임에 응용 프로그램 수준 프로젝트에서 데이터 바인딩된 컨트롤을 추가하는 방법에 대한 예제는 [연습: VSTO 추가 기능 프로젝트의 복합 데이터 바인딩](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md)를 참조하십시오.  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 비디오 데모를 보려면 [How Do I: Transfer Data Into an Excel Worksheet?](http://go.microsoft.com/fwlink/?LinkID=130277) 및[How Do I: Consume Database Data in Excel?](http://go.microsoft.com/fwlink/?LinkID=130287)을 참조하십시오.  
  
## 디자인 타임에 워크시트에 데이터 바인딩된 컨트롤 추가  
  
#### 데이터베이스의 데이터로 워크시트를 채우려면  
  
1.  Visual Studio에서 Excel 문서 수준 프로젝트를 열고 디자이너에서 워크시트를 엽니다.  
  
2.  **데이터 소스** 창을 열고 프로젝트의 데이터 소스를 만듭니다.  자세한 내용은 [방법: 데이터베이스의 데이터에 연결](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md)을 참조하십시오.  
  
3.  필요한 필드나 테이블을 **데이터 소스** 창에서 워크시트로 끌어 놓습니다.  
  
 워크시트에 다음 컨트롤 중 하나가 만들어집니다.  
  
-   필드를 끌어 온 경우 워크시트에 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤이 만들어집니다.  자세한 내용은 [NamedRange 컨트롤](../vsto/namedrange-control.md)을 참조하십시오.  
  
-   테이블을 끌어 온 경우 워크시트에 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 만들어집니다.  자세한 내용은 [ListObject 컨트롤](../vsto/listobject-control.md)을 참조하십시오.  
  
 **데이터 소스** 창에서 테이블 또는 필드를 선택한 다음 드롭다운 목록에서 다른 컨트롤을 선택하여 다른 컨트롤을 추가할 수 있습니다.  
  
## 프로젝트의 개체  
 컨트롤뿐 아니라 다음과 같은 데이터 관련 개체도 프로젝트에 자동으로 추가됩니다.  
  
-   데이터베이스의 연결된 데이터 테이블을 캡슐화하는 형식화된 데이터 집합.  자세한 내용은 [Visual Studio에서 데이터 집합 작업](../data-tools/dataset-tools-in-visual-studio.md)을 참조하십시오.  
  
-   형식화된 데이터 집합에 컨트롤을 연결하는 <xref:System.Windows.Forms.BindingSource>.  자세한 내용은 [BindingSource 구성 요소 개요](../Topic/BindingSource%20Component%20Overview.md)을 참조하십시오.  
  
-   형식화된 데이터 집합을 데이터베이스에 연결하는 TableAdapter.  자세한 내용은 [TableAdapter 개요](/visual-studio/data-tools/tableadapter-overview)을 참조하십시오.  
  
-   계층적 업데이트를 사용하도록 설정하기 위해 데이터 집합의 테이블 어댑터를 조정하는 데 사용되는 TableAdapterManager.  자세한 내용은 [계층적 업데이트](../data-tools/hierarchical-update.md) 및 [TableAdapterManager 개요](../Topic/TableAdapterManager%20Overview.md)를 참조하십시오.  
  
 프로젝트를 실행하면 데이터 소스의 첫 번째 레코드가 컨트롤에 표시됩니다.  <xref:System.Windows.Forms.BindingSource>를 사용하여 사용자가 레코드를 스크롤할 수 있게 설정할 수 있습니다.  
  
#### 레코드를 스크롤하려면  
  
-   <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 및 <xref:System.Windows.Forms.BindingSource.MovePrevious%2A>와 같은 <xref:System.Windows.Forms.BindingSource> 메서드를 사용합니다.  
  
 형식화된 데이터 집합 및 데이터베이스에 업데이트를 보내는 방법에 대한 자세한 내용은 [방법: Host 컨트롤의 데이터로 데이터 원본 업데이트](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)를 참조하십시오.  
  
## 참고 항목  
 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [데이터 소스 개요](../data-tools/add-new-data-sources.md)   
 [Visual Studio에서 데이터에 Windows Forms 컨트롤 바인딩](../Topic/Binding%20Windows%20Forms%20controls%20to%20data%20in%20Visual%20Studio.md)   
 [방법: 개체의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [방법: 데이터베이스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [방법: 서비스의 데이터로 문서 채우기](../vsto/how-to-populate-documents-with-data-from-services.md)   
 [방법: Host 컨트롤의 데이터로 데이터 원본 업데이트](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [I: 방법 데이터 Excel 워크시트로 전송](http://go.microsoft.com/fwlink/?LinkID=130277)   
 [어떻게 수행할 i: 소비 데이터베이스 데이터를 Excel?](http://go.microsoft.com/fwlink/?LinkID=130287)  
  
  
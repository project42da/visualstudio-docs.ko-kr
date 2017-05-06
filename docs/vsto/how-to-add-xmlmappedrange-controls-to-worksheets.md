---
title: "방법: 워크시트에 XMLMappedRange 컨트롤 추가"
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
  - "컨트롤[Visual Studio에서 Office 개발], 워크시트에 추가"
  - "XMLMappedRange 컨트롤, 워크시트에 추가"
ms.assetid: e1d4f2a8-1157-49c2-9158-a1253b709cb8
caps.latest.revision: 25
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 25
---
# 방법: 워크시트에 XMLMappedRange 컨트롤 추가
  Microsoft Office Excel의 셀에 XML 요소를 매핑하면 Visual Studio에서 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤이 워크시트에 자동으로 추가됩니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 **도구 상자** 또는 **데이터 소스** 창에서 사용할 수 없습니다.  또한 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤은 프로그래밍 방식으로 만들 수 없습니다.  
  
### 워크시트에 XMLMappedRange 컨트롤을 추가하려면  
  
1.  Visual Studio 디자이너에서 Excel 통합 문서를 엽니다.  
  
2.  컨트롤을 추가할 워크시트를 엽니다.  
  
3.  **개발자** 탭에서 **소스**를 클릭합니다.  
  
    > [!NOTE]  
    >  리본 메뉴에 **개발 도구** 탭이 표시되지 않으면 이 탭을 표시해야 합니다.  자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하십시오.  
  
     그러면 **XML 소스** 작업 창이 표시됩니다.  
  
4.  **XML 소스** 작업 창에서 **XML 맵**을 클릭합니다.  
  
5.  **XML 맵** 대화 상자에서 **추가**를 클릭합니다.  
  
     **XML 소스** 대화 상자가 표시됩니다.  
  
6.  **XML 소스** 대화 상자에서 XML 스키마를 선택하고 **열기**를 클릭합니다.  
  
     **XML 맵** 대화 상자에 스키마가 추가됩니다.  
  
7.  **XML 맵** 대화 상자에서 **확인**을 클릭합니다.  
  
8.  **XML 소스** 작업 창에서 워크시트의 셀로 요소를 끌어 옵니다.  
  
     <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>가 만들어지고 프로젝트에 추가됩니다.  
  
    > [!NOTE]  
    >  **XML 소스** 작업 창에서 부모 요소를 끌어 온 경우에는 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤이 만들어집니다.  
  
## 참고 항목  
 [XmlMappedRange 컨트롤](../vsto/xmlmappedrange-control.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)  
  
  
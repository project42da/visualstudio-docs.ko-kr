---
title: "방법: Visual Studio 내에서 워크시트에 스키마 매핑 | Microsoft Docs"
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
  - "Excel[Visual Studio에서 Office 개발], XML 스키마"
  - "매핑[Visual Studio에서 Office 개발], XML 스키마를 Excel 워크시트로"
  - "워크시트[Visual Studio에서 Office 개발], XML 스키마"
  - "XML 스키마[Visual Studio에서 Office 개발], 매핑"
ms.assetid: cef3f751-c1cf-46f3-9177-0bacdcee4121
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 35
---
# 방법: Visual Studio 내에서 워크시트에 스키마 매핑
  워크시트가 Visual Studio에 열려 있는 동안 XML 스키마를 워크시트에 매핑할 수 있습니다.  Visual Studio 외부에서 통합 문서를 열었을 때와 동일한 Microsoft Office Excel 도구를 사용합니다.  Excel 솔루션을 만들기 전에 스키마를 워크시트에 매핑하는지 응용 프로그램을 만든 후에 매핑하는지 여부에 상관없이 Office 프로젝트에서는 동일한 개체를 만듭니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  multipart XML 스키마는 Excel 솔루션에서 사용할 수 없습니다.  
  
### Visual Studio에서 Excel 워크시트에 XML 스키마를 매핑하려면  
  
1.  Visual Studio 내에서 Excel 통합 문서 또는 서식 파일 프로젝트를 엽니다.  
  
2.  워크시트를 클릭하여 포커스를 디자이너로 이동합니다.  
  
3.  리본 메뉴에서 **개발 도구** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발 도구** 탭이 표시되지 않으면 먼저 이 탭을 표시해야 합니다.  자세한 내용은 [방법: 리본 메뉴에 개발 도구 탭 표시](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하십시오.  
  
4.  **XML** 그룹에서 **소스**를 클릭합니다.  
  
     **XML 소스** 창이 열립니다.  
  
5.  **XML 소스** 창에서 **XML 맵**을 클릭합니다.  
  
     **XML 맵** 대화 상자가 열립니다.  
  
6.  **XML 맵** 대화 상자에서 **추가**를 클릭합니다.  
  
7.  스키마 파일을 찾아 선택한 다음 **열기**를 클릭합니다.  
  
8.  **확인**을 클릭합니다.  
  
     **XML 소스** 창에 스키마가 표시됩니다.  프로젝트에서 형식화된 <xref:System.Data.DataSet>이 스키마를 기반으로 생성되고 <xref:System.Windows.Forms.BindingSource>가 만들어집니다.  
  
9. **XML 소스** 창에서 워크시트의 원하는 위치로 요소를 끌어와 해당 컨트롤을 만듭니다.  
  
     반복 되지 않는 스키마 요소를 끌면 Office 프로젝트를 생성 하는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 자동으로 바인딩되는 컨트롤은 <xref:System.Windows.Forms.BindingSource>.  
  
     반복 되는 스키마 요소를 끌면 Office 프로젝트를 생성 하는 <xref:Microsoft.Office.Tools.Excel.ListObject> 자동으로 데이터 소스에 바인딩된 컨트롤이 있습니다.  자세한 내용은 [문서 수준 사용자 지정의 XML 스키마 및 데이터](../vsto/xml-schemas-and-data-in-document-level-customizations.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: Visual Studio 내부의 Word 문서에 스키마 매핑](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [문서 수준 사용자 지정의 XML 스키마 및 데이터](../vsto/xml-schemas-and-data-in-document-level-customizations.md)  
  
  
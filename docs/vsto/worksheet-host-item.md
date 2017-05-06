---
title: "워크시트 호스트 항목"
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
  - "호스트 항목[Visual Studio에서 Office 개발], 워크시트"
  - "Excel[Visual Studio에서 Office 개발], 워크시트"
  - "워크시트 호스트 항목"
  - "워크시트, 이벤트"
  - "워크시트 호스트 항목, 이벤트"
  - "Excel 워크시트"
  - "워크시트, Excel"
  - "워크시트"
  - "이벤트[Visual Studio에서 Office 개발]"
ms.assetid: b4f7c501-81f5-409e-aa1b-748f010798b9
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# 워크시트 호스트 항목
  <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목은 Excel용 주 interop 어셈블리의 <xref:Microsoft.Office.Interop.Excel.Worksheet> 형식을 확장한 형식입니다.<xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목은 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체와 동일한 모든 속성, 메서드 및 이벤트를 제공할 뿐 아니라 추가 이벤트를 노출하고 호스트 컨트롤 및 Windows Forms 컨트롤에 대한 컨테이너 역할을 합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
 문서 수준 프로젝트에서는 디자인 타임에 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 프로젝트에 추가할 수 있습니다. VSTO 추가 기능 프로젝트에서 런타임에 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 생성할 수 있습니다.  
  
## 문서 수준 프로젝트에서 워크시트 호스트 항목 이해  
 Excel용 문서 수준 프로젝트를 만드는 경우 Visual Studio는 자동으로 세 개의 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 프로젝트에 만듭니다. 워크시트의 기본 이름은 `Sheet1`, `Sheet2`, `Sheet3`입니다. 기존 통합 문서를 기반으로 프로젝트를 만드는 경우 호스트 항목의 수는 통합 문서의 워크시트 수에 따라 달라집니다.  
  
 이러한 워크시트 클래스는 워크시트의 내용 수정과 같이 사용자 지정에서 기본 작업을 수행할 수 있도록 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목의 구성원에 대한 액세스를 제공합니다. 또한 이러한 클래스를 사용하여 컨트롤을 워크시트에 추가할 수도 있습니다. 다양한 컨트롤 집합을 결합하고 코드를 작성하여 컨트롤을 데이터에 바인딩하고, 사용자로부터 정보를 수집하고, 사용자 작업에 응답할 수 있습니다. 자세한 내용은 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)을 참조하십시오.  
  
 워크시트 클래스는 프로젝트에서 코드 작성을 시작할 수 있는 위치를 제공합니다. 이 클래스는 Excel용 주 interop 어셈블리의 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체와 동일한 속성, 메서드 및 이벤트를 제공하므로 이러한 클래스를 사용하여 Excel의 개체 모델에 액세스할 수 있습니다. 자세한 내용은 [Excel 개체 모델 개요](../vsto/excel-object-model-overview.md)을 참조하세요.  
  
 문서 수준 프로젝트에서는 디자인 타임에 새 워크시트를 디자이너의 통합 문서에 추가하여 추가 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 프로젝트에 추가할 수 있습니다.  
  
### 워크시트 이름 바꾸기  
 문서 수준 프로젝트에서는 Visual Studio 디자이너에서 워크시트 이름을 바꿀 수 있지만, 워크시트의 표시 이름만 변경합니다. 프로그래밍 이름이 여전히 워크시트의 기본 이름입니다.**속성** 창에서 워크시트의 이름을 바꾸는 경우 프로그래밍 이름만 변경됩니다.  
  
### 문서 수준 프로젝트에서 워크시트 호스트 항목 제한 사항  
 문서 수준 프로젝트에서는 런타임에 새 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 만들 수 없습니다. 런타임에 새 Excel 워크시트를 만드는 경우 <xref:Microsoft.Office.Interop.Excel.Worksheet> 형식이 됩니다. 이 형식은 호스트 항목이 아니므로 호스트 컨트롤 또는 Windows Forms 컨트롤을 포함할 수 없습니다. 런타임에 문서 만들기에 대한 자세한 내용은 [방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)를 참조하세요.  
  
## VSTO 추가 기능 프로젝트에서 워크시트 호스트 항목 이해  
 응용 프로그램 수준 프로젝트에서는 런타임에 Excel에서 열리는 워크시트에 대해 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 생성할 수 있습니다.<xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 사용하여 연결된 워크시트에 컨트롤을 추가하거나 <xref:Microsoft.Office.Interop.Excel.Worksheet> 개체에서 사용할 수 없는 이벤트를 처리할 수 있습니다.  
  
 <xref:Microsoft.Office.Tools.Excel.Worksheet> 호스트 항목을 생성하려면 GetVstoObject 메서드를 사용합니다. 자세한 내용은 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하십시오.  
  
## 참고 항목  
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)   
 [런타임에 VSTO 추가 기능에서 Word 문서 및 Excel 통합 문서 확장](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [통합 문서 호스트 항목](../vsto/workbook-host-item.md)   
 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  
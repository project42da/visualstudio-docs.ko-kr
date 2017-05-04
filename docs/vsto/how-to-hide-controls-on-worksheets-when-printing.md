---
title: "방법: 인쇄할 때 워크시트에서 컨트롤 숨기기 | Microsoft Docs"
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
  - "컨트롤[Visual Studio에서 Office 개발], 인쇄할 때 숨기기"
  - "인쇄[Visual Studio에서 Office 개발], 컨트롤 숨기기"
  - "인쇄[Visual Studio에서 Office 개발], 워크시트"
  - "워크시트, 인쇄할 때 컨트롤 숨기기"
ms.assetid: a637fe9a-9de1-4162-8ff6-fe28ccd62389
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# 방법: 인쇄할 때 워크시트에서 컨트롤 숨기기
  Windows Forms 컨트롤이 들어 있는 Microsoft Office Excel 문서를 인쇄하면 이 컨트롤이 인쇄된 워크시트에 표시됩니다.  워크시트를 인쇄할 때 이 컨트롤을 숨길 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Excel.Controls.TextBox> 같이 데이터를 표시하는 컨트롤을 숨기면 이 컨트롤의 데이터가 인쇄된 워크시트에 표시되지 않습니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 워크시트를 인쇄할 때 컨트롤을 숨기려면  
  
1.  Visual Studio에서 Excel 프로젝트를 만들거나 열고 **Sheet1**이 디자이너에 표시되어 있는지 확인합니다.  프로젝트를 만드는 것에 대한 자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)를 참조하십시오.  
  
2.  **도구 상자**의 **공용 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Excel.Controls.Button> 컨트롤을 `Sheet1`의 셀에 끌어 놓습니다.  
  
3.  **속성** 창에서 <xref:Microsoft.Office.Tools.Excel.Controls.Button.PrintObject%2A> 속성을 **False**로 설정합니다.  
  
## 참고 항목  
 [Office 문서의 컨트롤](../vsto/controls-on-office-documents.md)   
 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [방법: 워크시트 셀에서 컨트롤 크기 조정](../vsto/how-to-resize-controls-within-worksheet-cells.md)  
  
  
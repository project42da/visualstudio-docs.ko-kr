---
title: "Office 프로젝트의 개체에 전역 액세스"
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
  - "ThisDocument_Shutdown"
  - "ThisDocument_Startup"
  - "전역 클래스, 개체 전역 액세스"
  - "워크시트[Visual Studio에서 Office 개발], 전역 액세스"
  - "문서[Visual Studio에서 Office 개발], 전역 액세스"
  - "이벤트 처리기[Visual Studio에서 Office 개발]"
  - "ThisWorkbook_Startup"
  - "응용 프로그램 수준 추가 기능[Visual Studio에서 Office 개발]"
  - "추가 기능[Visual Studio에서 Office 개발], 이벤트"
  - "통합 문서[Visual Studio에서 Office 개발], 전역 액세스"
  - "ThisWorkbook_Shutdown"
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발]"
  - "Startup 이벤트"
  - "Shutdown 이벤트"
  - "프로젝트[Visual Studio에서 Office 개발], 전역 액세스"
  - "Office 문서[Visual Studio에서 Office 개발], 전역 액세스"
  - "ThisAddin_Startup"
  - "이벤트[Visual Studio에서 Office 개발]"
  - "ThisAddIn_Shutdown"
ms.assetid: f6a7f0ef-75d0-4a9b-9aec-be95ffa26adf
caps.latest.revision: 55
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 54
---
# Office 프로젝트의 개체에 전역 액세스
  Office 프로젝트를 만들면 Visual Studio에서 `Globals`라는 클래스를 프로젝트에 자동으로 생성합니다.`Globals` 클래스를 사용하여 프로젝트의 모든 코드에서 런타임에 여러 프로젝트 항목에 액세스할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## Globals 클래스를 사용하는 방법  
 `Globals`는 프로젝트의 특정 항목에 대한 참조를 유지하는 정적 클래스입니다.`Globals` 클래스를 사용하면 런타임에 프로젝트의 코드에서 다음과 같은 항목에 액세스할 수 있습니다.  
  
-   Excel 통합 문서 또는 서식 파일 프로젝트의 `ThisWorkbook` 및 `Sheet`*n* 클래스.`Globals.ThisWorkbook` 및 `Sheet`*n* 속성을 사용하여 이러한 개체에 액세스할 수 있습니다.  
  
-   Word 문서 또는 서식 파일 프로젝트의 `ThisDocument` 클래스.`Globals.ThisDocument` 속성을 사용하여 이 개체에 액세스할 수 있습니다.  
  
-   VSTO 추가 기능 프로젝트의 `ThisAddIn` 클래스입니다.`Globals.ThisAddIn` 속성을 사용하여 이 개체에 액세스할 수 있습니다.  
  
-   리본 디자이너를 사용하여 사용자 지정한 프로젝트의 모든 리본.`Globals.Ribbons` 속성을 사용하여 리본에 액세스할 수 있습니다. 자세한 내용은 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)을 참조하십시오.  
  
-   Outlook VSTO 추가 기능 프로젝트의 모든 Outlook 양식 영역입니다.`Globals.FormRegions` 속성을 사용하여 양식 영역에 액세스할 수 있습니다. 자세한 내용은 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)을 참조하세요.  
  
-   리본 컨트롤을 만들고 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]를 대상으로 하는 프로젝트에서 런타임에 호스트 항목을 만들 수 있는 팩터리 개체.`Globals.Factory` 속성을 사용하여 이 개체에 액세스할 수 있습니다. 이 개체는 다음 인터페이스 중 하나를 구현하는 클래스의 인스턴스입니다.  
  
    -   <xref:Microsoft.Office.Tools.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Excel.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Outlook.Factory>  
  
    -   <xref:Microsoft.Office.Tools.Word.Factory>  
  
 예를 들어 사용자가 Excel에 대한 문서 수준 프로젝트의 작업창에서 단추를 클릭하면 `Globals.Sheet1` 속성을 사용하여 `Sheet1`의 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤에 텍스트를 삽입할 수 있습니다.  
  
 [!code-csharp[Trin_VstcoreProgramming#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/CS/Sheet1.cs#1)]
 [!code-vb[Trin_VstcoreProgramming#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/VB/Sheet1.vb#1)]  
  
## Globals 클래스 초기화  
 문서 또는 VSTO 추가 기능이 완전히 초기화되기 전에 `Globals` 클래스를 사용하려고 시도하는 코드는 런타임 예외를 throw할 수 있습니다. 예를 들어 `Globals` 클래스는 선언된 개체가 인스턴스화되기 전에 모든 호스트 항목에 대한 참조로 초기화되지 않을 수 있으므로 클래스 수준 변수를 선언할 때 `Globals`를 사용하면 실패할 수 있습니다.  
  
> [!NOTE]  
>  `Globals` 클래스는 디자인 타임에 초기화되지 않지만 컨트롤 인스턴스는 디자이너에서 만듭니다. 즉, 사용자 정의 컨트롤 클래스 내부에서 `Globals` 클래스의 속성을 사용하는 사용자 정의 컨트롤을 만드는 경우 반환된 개체를 사용하기 전에 속성에서 **null**을 반환하는지 여부를 확인해야 합니다.  
  
## 참고 항목  
 [런타임에 리본 메뉴에 액세스](../vsto/accessing-the-ribbon-at-run-time.md)   
 [런타임에 양식 영역 액세스](../vsto/accessing-a-form-region-at-run-time.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)   
 [통합 문서 호스트 항목](../vsto/workbook-host-item.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)  
  
  
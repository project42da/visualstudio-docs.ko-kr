---
title: "Office 솔루션에서 WPF 컨트롤 사용 | Microsoft Docs"
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
  - "WPF[Visual Studio에서 Office 개발]"
ms.assetid: 305a212b-0a95-40ad-87aa-22896fe80a04
caps.latest.revision: 25
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# Office 솔루션에서 WPF 컨트롤 사용
  Visual Studio에서 Office 개발 도구를 사용하여 만든 솔루션은 Windows Forms 컨트롤에서 직접 작동하도록 설계되었지만 솔루션에서 WPF 컨트롤을 사용할 수도 있습니다.  WPF\(Windows Presentation Foundation\)는 Windows Forms 대신 사용자 인터페이스를 디자인하는 데 사용됩니다.  WPF는 XAML\(Extensible Application Markup Language\)이라는 태그 언어를 사용하여 UI, 미디어 및 문서를 통합하기 위한 새로운 기술을 제공합니다.  자세한 내용은 [Visual Studio 2015에서의 WPF 소개](../Topic/Introduction%20to%20WPF%20in%20Visual%20Studio%202015.md)를 참조하세요.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Office 솔루션에서 Windows Forms 컨트롤을 호스트할 수 있는 UI 요소는 WPF 컨트롤도 호스트할 수 있습니다.  다음과 같은 요소가 포함됩니다.  
  
-   문서 수준 사용자 지정의 문서 및 워크시트  
  
-   문서 수준 사용자 지정의 작업 창  
  
-   VSTO 추가 기능의 사용자 지정 작업창  
  
-   Outlook용 VSTO 추가 기능의 양식 영역  
  
## 디자인 타임에 Office 프로젝트에 WPF 컨트롤 추가  
 Office 솔루션의 UI 요소에 직접 WPF 컨트롤을 추가할 수 없습니다.  대신 **사용자 정의 컨트롤\(WPF\)** 항목을 프로젝트에 추가하고 WPF 컨트롤의 디자인 화면으로 사용합니다.  그런 다음 프로젝트에 있는 UI 요소에 WPF 사용자 정의 컨트롤을 추가합니다.  
  
#### 작업 창, 사용자 지정 작업창 또는 양식 영역에 WPF 컨트롤을 추가하려면  
  
1.  사용자 지정 작업창, 작업 창 또는 양식 영역을 추가하려는 프로젝트를 엽니다.  
  
2.  **사용자 정의 컨트롤\(WPF\)** 항목을 프로젝트에 추가합니다.  
  
3.  **도구 상자**에서 WPF 컨트롤을 WPF 사용자 정의 컨트롤 디자인 화면에 추가합니다.  
  
     WPF 사용자 정의 컨트롤 디자이너가 열려 있으면 기본적으로 **도구 상자**에 WPF 컨트롤만 포함됩니다.  
  
4.  프로젝트를 빌드합니다.  
  
5.  작업 창, 양식 영역 또는 사용자 지정 작업창을 프로젝트에 추가합니다.  
  
    -   양식 영역의 경우 **Outlook 양식 영역** 항목을 프로젝트에 추가합니다.  자세한 내용은 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)를 참조하세요.  
  
    -   작업 창의 경우 **작업 창 컨트롤** 또는 **사용자 정의 컨트롤** 항목을 프로젝트에 추가합니다.  자세한 내용은 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md) 및 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)를 참조하세요.  
  
    -   사용자 지정 작업창의 경우 **사용자 정의 컨트롤** 항목을 프로젝트에 추가합니다.  자세한 내용은 [방법: 응용 프로그램에 사용자 지정 작업 창 추가](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)를 참조하세요.  
  
6.  **도구 상자**의 *ProjectName* **WPF 사용자 정의 컨트롤** 탭에서 작업 창, 양식 영역 또는 사용자 지정 작업창에 대한 WPF 사용자 정의 컨트롤을 디자이너로 끌어옵니다.  
  
     Visual Studio에서 자동으로 UI 요소에 WPF 사용자 정의 컨트롤을 호스트하는 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 만듭니다.  
  
7.  프로젝트를 다시 빌드합니다.  
  
#### 문서 수준 프로젝트의 문서 또는 워크시트에 WPF 컨트롤을 추가하려면  
  
1.  Word 또는 Excel에 대한 문서 수준 프로젝트를 엽니다.  
  
2.  **사용자 정의 컨트롤\(WPF\)** 항목을 프로젝트에 추가합니다.  
  
3.  **도구 상자**에서 WPF 컨트롤을 WPF 사용자 정의 컨트롤 디자인 화면에 추가합니다.  
  
4.  프로젝트를 빌드합니다.  
  
5.  **사용자 정의 컨트롤** 항목\(즉, Windows Forms 사용자 정의 컨트롤\)을 프로젝트에 추가합니다.  
  
6.  Windows Forms 사용자 정의 컨트롤에 대한 디자이너를 엽니다.  
  
7.  **도구 상자**의 *ProjectName* **WPF 사용자 정의 컨트롤** 탭에서 WPF 사용자 정의 컨트롤을 디자이너로 끌어옵니다.  
  
     Visual Studio에서 자동으로 Windows Forms 사용자 정의 컨트롤에 WPF 사용자 정의 컨트롤을 호스트하는 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 만듭니다.  
  
8.  프로그래밍 방식으로 문서 또는 통합 문서에 Windows Forms 사용자 정의 컨트롤을 추가하는 코드를 작성합니다.  자세한 내용은 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)를 참조하세요.  
  
    > [!NOTE]  
    >  디자이너에서 Windows Forms 사용자 정의 컨트롤을 문서 또는 워크시트로 끌 수 없습니다.  
  
9. 프로젝트를 다시 빌드합니다.  
  
## ElementHost 클래스를 사용하여 WPF 컨트롤 호스트  
 Visual Studio은 Office 솔루션에서 Windows Forms 컨트롤을 사용하는 데 유용한 기능을 제공하지만 WPF 컨트롤에 대해서는 유사한 기능을 제공하지 않습니다.  예를 들어 디자인 타임에 **도구 상자**에서 컨트롤을 끌어 또는 런타임에 도우미 메서드를 사용하여 문서 및 워크시트에 Windows Forms 컨트롤을 추가할 수 있습니다.  그러나 WPF 컨트롤에는 이러한 도구를 사용할 수 없습니다.  
  
 WPF 컨트롤은 Windows Forms 컨트롤 또는 폼과 WPF 컨트롤 간의 통합 계층으로 <xref:System.Windows.Forms.Integration.ElementHost> 클래스를 사용합니다.  디자인 타임에 솔루션에 WPF 컨트롤을 추가하는 경우 Visual Studio에서 자동으로 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 생성합니다.  
  
## WPF 리소스  
 Windows Forms 컨트롤 및 폼에 WPF 컨트롤을 호스트하기 위한 아키텍처 및 디자인 문제에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [Windows Forms 및 WPF 상호 운용성 입력 아키텍처](../Topic/Windows%20Forms%20and%20WPF%20Interoperability%20Input%20Architecture.md)  
  
-   [Windows Forms 및 WPF 속성 매핑](../Topic/Windows%20Forms%20and%20WPF%20Property%20Mapping.md)  
  
-   [WPF 및 Windows Forms 상호 운용성](../Topic/WPF%20and%20Windows%20Forms%20Interoperation.md)  
  
-   [Windows Forms 컨트롤 및 해당 WPF 컨트롤](../Topic/Windows%20Forms%20Controls%20and%20Equivalent%20WPF%20Controls.md)  
  
 디자인 타임에 Visual Studio에서 Windows Forms 컨트롤과 폼에 WPF 컨트롤을 추가하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](../Topic/Walkthrough:%20Creating%20New%20WPF%20Content%20on%20Windows%20Forms%20at%20Design%20Time.md)  
  
-   [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬](../Topic/Walkthrough:%20Arranging%20WPF%20Content%20on%20Windows%20Forms%20at%20Design%20Time.md)  
  
-   [연습: WPF 콘텐츠 스타일 지정](../Topic/Walkthrough:%20Styling%20WPF%20Content.md)  
  
## 참고 항목  
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [사용자 지정 작업 창](../vsto/custom-task-panes.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [방법: Word 문서 또는 Excel 통합 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [방법: 응용 프로그램에 사용자 지정 작업 창 추가](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)  
  
  
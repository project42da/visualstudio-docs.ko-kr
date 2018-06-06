---
title: Office 솔루션에서 WPF 컨트롤 사용
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WPF [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87305902c80d9848df63d2c8bd9f431fd93a5508
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767597"
---
# <a name="use-wpf-controls-in-office-solutions"></a>Office 솔루션에서 WPF 컨트롤 사용
  Visual Studio에서 Office 개발 도구를 사용하여 만든 솔루션은 Windows Forms 컨트롤에서 직접 작동하도록 설계되었지만 솔루션에서 WPF 컨트롤을 사용할 수도 있습니다. WPF(Windows Presentation Foundation)는 Windows Forms 대신 사용자 인터페이스를 디자인하는 데 사용됩니다. WPF는 XAML(Extensible Application Markup Language)이라는 태그 언어를 사용하여 UI, 미디어 및 문서를 통합하기 위한 새로운 기술을 제공합니다. 자세한 내용은 참조 [Visual Studio 2015의 WPF 소개](/dotnet/framework/wpf/getting-started/introduction-to-wpf-in-vs)합니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Office 솔루션에서 Windows Forms 컨트롤을 호스트할 수 있는 UI 요소는 WPF 컨트롤도 호스트할 수 있습니다. 다음과 같은 요소가 포함됩니다.  
  
-   문서 수준 사용자 지정의 문서 및 워크시트  
  
-   문서 수준 사용자 지정의 작업 창  
  
-   VSTO 추가 기능의 사용자 지정 작업창  
  
-   Outlook용 VSTO 추가 기능의 양식 영역  
  
## <a name="add-wpf-controls-to-office-projects-at-design-time"></a>디자인 타임에 Office 프로젝트에 WPF 컨트롤 추가  
 Office 솔루션의 UI 요소에 직접 WPF 컨트롤을 추가할 수 없습니다. 대신 추가 **사용자 정의 컨트롤 (WPF)** 프로젝트에 항목을 WPF 컨트롤의 디자인 화면으로 사용 합니다. 그런 다음 프로젝트에 있는 UI 요소에 WPF 사용자 정의 컨트롤을 추가합니다.  
  
### <a name="to-add-wpf-controls-to-an-actions-pane-custom-task-pane-or-form-region"></a>작업 창, 사용자 지정 작업창 또는 양식 영역에 WPF 컨트롤을 추가하려면  
  
1.  사용자 지정 작업창, 작업 창 또는 양식 영역을 추가하려는 프로젝트를 엽니다.  
  
2.  추가 **사용자 정의 컨트롤 (WPF)** 항목을 프로젝트입니다.  
  
3.  **도구 상자**, WPF 컨트롤을 WPF 사용자 정의 컨트롤 디자인 화면에 추가 합니다.  
  
     WPF 사용자 정의 컨트롤 디자이너가 열릴 때 기본적으로는 **도구 상자** WPF 컨트롤만 포함 합니다.  
  
4.  프로젝트를 빌드합니다.  
  
5.  작업 창, 양식 영역 또는 사용자 지정 작업창을 프로젝트에 추가합니다.  
  
    -   양식 영역에 대 한 추가 **Outlook 양식 영역** 항목을 프로젝트입니다. 자세한 내용은 참조 [하는 방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)합니다.  
  
    -   작업 창에 대 한 추가 **작업 창 컨트롤** 또는 **사용자 정의 컨트롤** 항목을 프로젝트입니다. 자세한 내용은 참조 [하는 방법: Word 문서에 작업 창 추가 또는 Excel 통합 문서](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md) 및 [하는 방법: Word 문서에 작업 창 추가 또는 Excel 통합 문서](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)합니다.  
  
    -   사용자 지정 작업창에 대 한 추가 **사용자 정의 컨트롤** 항목을 프로젝트입니다. 자세한 내용은 참조 [하는 방법: 응용 프로그램에 사용자 지정 작업창 추가](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)합니다.  
  
6.  *p r o j* **WPF 사용자 정의 컨트롤** 탭은 **도구 상자**, 작업 창, 양식 영역 또는 사용자 지정 작업창에 대 한 디자이너를 WPF 사용자 정의 컨트롤을 끌어 옵니다.  
  
     Visual Studio에서 자동으로 UI 요소에 WPF 사용자 정의 컨트롤을 호스트하는 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 만듭니다.  
  
7.  프로젝트를 다시 빌드합니다.  
  
#### <a name="to-add-wpf-controls-to-a-document-or-worksheet-in-a-document-level-project"></a>문서 수준 프로젝트의 문서 또는 워크시트에 WPF 컨트롤을 추가하려면  
  
1.  Word 또는 Excel에 대한 문서 수준 프로젝트를 엽니다.  
  
2.  추가 **사용자 정의 컨트롤 (WPF)** 항목을 프로젝트입니다.  
  
3.  **도구 상자**, WPF 컨트롤을 WPF 사용자 정의 컨트롤 디자인 화면에 추가 합니다.  
  
4.  프로젝트를 빌드합니다.  
  
5.  추가 **사용자 정의 컨트롤** 프로젝트에 있는 항목 (즉, Windows Forms 사용자 정의 컨트롤).  
  
6.  Windows Forms 사용자 정의 컨트롤에 대한 디자이너를 엽니다.  
  
7.  *ProjectName* **WPF 사용자 정의 컨트롤** 탭은 **도구 상자**을 WPF 사용자 정의 컨트롤을 디자이너로 끌어옵니다.  
  
     Visual Studio에서 자동으로 Windows Forms 사용자 정의 컨트롤에 WPF 사용자 정의 컨트롤을 호스트하는 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 만듭니다.  
  
8.  프로그래밍 방식으로 문서 또는 통합 문서에 Windows Forms 사용자 정의 컨트롤을 추가하는 코드를 작성합니다. 자세한 내용은 참조 [런타임에 Office 문서에 컨트롤 추가](../vsto/adding-controls-to-office-documents-at-run-time.md)합니다.  
  
    > [!NOTE]  
    >  디자이너에서 Windows Forms 사용자 정의 컨트롤을 문서 또는 워크시트로 끌 수 없습니다.  
  
9. 프로젝트를 다시 빌드합니다.  
  
## <a name="host-wpf-controls-by-using-the-elementhost-class"></a>ElementHost 클래스를 사용 하 여 WPF 컨트롤을 호스트  
 Visual Studio은 Office 솔루션에서 Windows Forms 컨트롤을 사용하는 데 유용한 기능을 제공하지만 WPF 컨트롤에 대해서는 유사한 기능을 제공하지 않습니다. 예를 들어 있습니다 Windows Forms 컨트롤을 추가할 수 문서 및 워크시트 디자인 타임에 컨트롤을 끌어는 **도구 상자**, 또는 런타임에 도우미 메서드를 사용 하 여 합니다. 그러나 WPF 컨트롤에는 이러한 도구를 사용할 수 없습니다.  
  
 WPF 컨트롤은 Windows Forms 컨트롤 또는 폼과 WPF 컨트롤 간의 통합 계층으로 <xref:System.Windows.Forms.Integration.ElementHost> 클래스를 사용합니다. 디자인 타임에 솔루션에 WPF 컨트롤을 추가하는 경우 Visual Studio에서 자동으로 <xref:System.Windows.Forms.Integration.ElementHost> 개체를 생성합니다.  
  
## <a name="wpf-resources"></a>WPF 리소스  
 Windows Forms 컨트롤 및 폼에 WPF 컨트롤을 호스트하기 위한 아키텍처 및 디자인 문제에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [Windows Forms 및 WPF 상호 운용성 입력된 아키텍처](/dotnet/framework/wpf/advanced/windows-forms-and-wpf-interoperability-input-architecture)  
  
-   [Windows Forms 및 WPF 속성 매핑](/dotnet/framework/wpf/advanced/windows-forms-and-wpf-property-mapping)  
  
-   [WPF 및 Windows Forms 상호 운용](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)  
  
-   [Windows Forms 컨트롤 및 해당 WPF 컨트롤](/dotnet/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls)  
  
 디자인 타임에 Visual Studio에서 Windows Forms 컨트롤과 폼에 WPF 컨트롤을 추가하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기](/dotnet/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time)  
  
-   [연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬](/dotnet/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time)  
  
-   [연습: WPF 콘텐츠 스타일](/dotnet/framework/winforms/advanced/walkthrough-styling-wpf-content)  
  
## <a name="see-also"></a>참고자료  
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Office 문서 개요에서 Windows Forms 컨트롤](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [작업 창 개요](../vsto/actions-pane-overview.md)   
 [사용자 지정 작업 창](../vsto/custom-task-panes.md)   
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [방법: Excel 통합 문서 또는 Word 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [방법: Excel 통합 문서 또는 Word 문서에 작업 창 추가](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)   
 [방법: 응용 프로그램에 사용자 지정 작업창 추가](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)  
  
  
---
title: "시작 하기 VSTO 추가 기능 프로그래밍 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.ProjectItem.Outlook
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], getting started
- add-ins [Office development in Visual Studio], getting started
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: f395ce7fb85d71ed6e8c3f7dfb10726907832873
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="getting-started-programming-vsto-add-ins"></a>Getting Started Programming VSTO Add-ins
  VSTO 추가 기능을 사용하여 Microsoft Office 응용 프로그램을 자동화하고 응용 프로그램의 기능을 확장할 수 있으며 응용 프로그램의 UI(사용자 인터페이스)를 사용자 지정할 수 있습니다. Visual Studio를 사용 하 여 만들 수 있는 다른 유형의 Office 솔루션과 VSTO 추가 기능을 비교 하는 방법에 대 한 정보를 참조 하십시오. [Office 솔루션 개발 개요 &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
## <a name="creating-vsto-add-in-projects"></a>VSTO 추가 기능 프로젝트 만들기  
 에 VSTO 추가 기능 프로젝트 템플릿 중 하나를 사용 하 여 VSTO 추가 기능 프로젝트 만들기는 **새 프로젝트** 대화 상자. 이러한 템플릿에는 필요한 어셈블리 참조 및 프로젝트 파일이 포함되어 있습니다. Visual Studio에서는 대부분의 Office 응용 프로그램용 VSTO 추가 기능 프로젝트 템플릿을 제공합니다.  
  
 VSTO 추가 기능 프로젝트를 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다. 프로젝트 템플릿에 대 한 자세한 내용은 참조 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)합니다.  
  
## <a name="developing-vsto-add-in-projects"></a>VSTO 추가 기능 프로젝트 개발  
 ThisAddIn.vb에 Visual Studio에서 VSTO 추가 기능 프로젝트를 만들면 자동으로 만듭니다 (에서 [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) 또는 ThisAddIn.cs (C#) 코드 파일. 이 파일에 포함 된 `ThisAddIn` VSTO 추가 기능에 대 한 기초를 제공 하는 클래스입니다. 이 클래스의 멤버를 사용하여 VSTO 추가 기능이 로드되거나 언로드될 때 코드를 실행하고, 호스트 응용 프로그램의 개체 모델에 액세스하고, 응용 프로그램의 기능을 확장할 수 있습니다. 자세한 내용은 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)를 시작합니다.  
  
## <a name="automating-applications-by-using-the-object-models"></a>개체 모델을 사용하여 응용 프로그램 자동화  
 Microsoft Office 응용 프로그램의 개체 모델은 VSTO 추가 기능에서 프로그래밍의 대상이 될 수 있는 많은 형식을 노출합니다. 이러한 형식을 사용하여 응용 프로그램을 자동화할 수 있습니다. 예를 들어 프로그래밍 방식으로 Outlook에서 메일 메시지를 만들고 보내거나, 문서를 열고 Word에서 콘텐츠를 추가할 수 있습니다. 코드에서 호스트 응용 프로그램의 개체 모델에 액세스 하는 방법에 대 한 자세한 내용은 참조 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)합니다.  
  
 특정 Microsoft Office 응용 프로그램의 개체 모델에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [Excel Object Model Overview](../vsto/excel-object-model-overview.md)  
  
-   [Word Object Model Overview](../vsto/word-object-model-overview.md)  
  
-   [Outlook Object Model Overview](../vsto/outlook-object-model-overview.md)  
  
-   [InfoPath 솔루션](../vsto/infopath-solutions.md)  
  
-   [PowerPoint 솔루션](../vsto/powerpoint-solutions.md)  
  
-   [Project 솔루션](../vsto/project-solutions.md)  
  
-   [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)  
  
## <a name="customizing-the-user-interface-of-applications"></a>응용 프로그램의 사용자 인터페이스 사용자 지정  
 VSTO 추가 기능을 사용하여 호스트 응용 프로그램의 UI를 사용자 지정하는 몇 가지 방법이 있습니다.  
  
-   Excel과 Word의 경우 문서에 관리되는 컨트롤을 추가할 수 있습니다. 자세한 내용은 [Extending Word Documents and Excel Workbooks in VSTO Add-ins at Run Time](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)을 참조하세요.  
  
-   응용 프로그램이 지원하는 경우 리본을 사용자 지정할 수 있습니다. 자세한 내용은 참조 [리본 개요](../vsto/ribbon-overview.md)합니다.  
  
-   응용 프로그램이 지원하는 경우 사용자 지정 작업창을 만들 수 있습니다. 자세한 내용은 참조 [사용자 지정 작업창](../vsto/custom-task-panes.md)합니다.  
  
-   Outlook의 경우 사용자 지정 양식 영역을 만들 수 있습니다. 자세한 내용은 [Creating Outlook Form Regions](../vsto/creating-outlook-form-regions.md)을 참조하세요.  
  
-   모든 Microsoft Office 응용 프로그램의 경우 VSTO 추가 기능에서 Windows Forms를 표시할 수 있습니다.  
  
 UI의 Microsoft Office 응용 프로그램을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [Office UI 사용자 지정](../vsto/office-ui-customization.md)합니다.  
  
## <a name="next-steps"></a>다음 단계  
 VSTO 추가 기능을 만드는 방법을 알아보려면 다음 연습을 참조하세요.  
  
-   [연습: Excel용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)  
  
-   [연습: Outlook용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)  
  
-   [연습: PowerPoint용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)  
  
-   [연습: Project용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)  
  
-   [연습: Word용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)  
  
 이러한 연습에서는 Visual Studio의 Office 개발 도구와 VSTO 추가 기능의 프로그래밍 모델을 소개합니다.  
  
 Office 프로젝트에서 일반적인 작업 중 일부을 다루는 항목의 목록에 대 한 참조 [Office 프로그래밍의 일반적인 작업](../vsto/common-tasks-in-office-programming.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [시작 &#40; Visual Studio &#41;에서 Office 개발](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [VSTO 추가 기능 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)  
  
  
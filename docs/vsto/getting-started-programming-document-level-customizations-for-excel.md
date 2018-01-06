---
title: "Excel 용 문서 수준 사용자 지정 프로그래밍 시작 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel solutions in Visual Studio
- Excel projects [Office development in Visual Studio], getting started
ms.assetid: 8b73cf08-a173-4b49-b20f-2d2456dbe925
caps.latest.revision: "41"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0c2f8d0a8360153b81d54b5d1867af452e6aaf9d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-programming-document-level-customizations-for-excel"></a>Excel용 문서 수준 사용자 지정 프로그래밍 시작
  바로 시작 하는 Visual Studio를 사용 하 여 Microsoft Office Excel 용 문서 수준 사용자 지정 만들기를 경우 알아야 할 다음과 같습니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
## <a name="understanding-how-document-level-customizations-for-excel-work"></a>Excel 작업에 대 한 문서 수준 사용자 지정 이해  
 Excel 용 문서 수준 사용자 지정은를 기반으로 단일 통합 합니다. 를 사용자 지정을 사용 하려면 최종 사용자가 통합 문서 또는 Excel 서식에서 통합 문서를 만듭니다. 예를 들어 셀에 입력 하거나 단추 및 메뉴 항목을 클릭 하면 통합 문서에서 이벤트 어셈블리에서 이벤트 처리 메서드를 호출할 수 있습니다. 통합 문서를 닫을 때 사용자 지정에서 제공 하는 기능을 포함 하는 문서에만 Excel에서 사용할 수 없게 됩니다.  
  
 자세한 내용은 참조 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)합니다.  
  
## <a name="creating-document-level-projects-for-excel"></a>Excel 용 문서 수준 프로젝트 만들기  
 Excel 용 문서 수준 사용자 지정을 만들려면에서 Excel 통합 문서 또는 Excel 서식 파일 프로젝트 템플릿을 사용 하 여는 **새 프로젝트** 대화 상자. 이러한 템플릿에는 필요한 어셈블리 참조 및 프로젝트 파일이 포함되어 있습니다.  
  
 Excel 용 문서 수준 프로젝트를 만드는 방법에 대 한 자세한 내용은 참조 [하는 방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)합니다. 프로젝트 템플릿에 대 한 자세한 내용은 참조 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)합니다.  
  
## <a name="programming-excel-workbooks-by-using-host-items-and-host-controls"></a>Excel 통합 문서 호스트 항목 및 호스트 컨트롤을 사용 하 여 프로그래밍  
 *호스트 항목* 및 *호스트 컨트롤* Visual Studio를 사용 하 여 만든 문서 수준 사용자 지정 프로그래밍 모델을 제공 하는 클래스입니다.  
  
 호스트 항목 코드에 대 한 진입점을 제공 하 고 호스트 컨트롤 및 Windows Forms 컨트롤에 대 한 컨테이너로 취할 수 있습니다. Excel 용 문서 수준 프로젝트에서 이러한 호스트 항목으로 표시 됩니다는 `ThisWorkbook`, `Sheet1`, `Sheet2`, 및 `Sheet3` 클래스입니다.  
  
 호스트 컨트롤, 목록 개체 및 범위와 같은 기본 Excel 개체를 기반으로 합니다. 호스트 컨트롤은 네이티브 Excel 개체에 유사한 기능을 제공 하지만 새 이벤트, 디자이너 지원 및 데이터 바인딩 기능이 있습니다. 개체로 나타나므로 서 프로젝트 코드에서 쉽게 Excel 개체 모델을 탐색할 필요 하지 않고 코드에서 직접 특정 개체를 참조할 때 IntelliSense에 나타납니다.  
  
 자세한 내용은 다음 항목을 참조하세요.  
  
-   [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)  
  
-   [Automating Excel by Using Extended Objects](../vsto/automating-excel-by-using-extended-objects.md)  
  
-   [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)  
  
## <a name="customizing-the-user-interface-of-excel"></a>Excel의 사용자 인터페이스 사용자 지정  
 대부분의 Microsoft Office 솔루션 솔루션와 상호 작용 하는 사용자에 대 한 몇 가지 방법을 제공 하도록 Office 응용 프로그램의 사용자 인터페이스 (UI)를 수정 합니다. 여러 가지 방법으로는 문서 수준 사용자 지정을 사용 하 여 Excel의 UI를 수정할 수 있습니다. 예를 들어 리본 메뉴에 컨트롤을 추가할 수 있습니다 또는 작업 창에 표시할 수 있습니다. 자세한 내용은 참조 [Office UI 사용자 지정](../vsto/office-ui-customization.md)합니다.  
  
 Visual Studio에서 직접 프로젝트와 연결 된 통합 문서를 열 수 있습니다. 통합 문서를 연 Visual Studio에서 Excel 사용자 인터페이스를 사용 하 여 통합 문서를 수정할 수 있습니다. 워크시트에 컨트롤을 끌어 놓을 수 있는 디자인 화면으로 통합 문서를 사용할 수도 있습니다. 자세한 내용은 참조 [Visual Studio 환경의 Office 프로젝트](../vsto/office-projects-in-the-visual-studio-environment.md)합니다.  
  
## <a name="using-data-binding"></a>데이터 바인딩 사용  
 호스트 컨트롤에에서도 포함 되어에서 끌어 놓을 수 있는 컨트롤의 목록에서 **데이터 소스** 창. 이 방식으로 자동으로 호스트 컨트롤을 추가 창을 사용 하 여 설정 하는 데이터 원본에 바인딩합니다. 코드를 작성 하지 않고 데이터베이스, 웹 서비스 및 비즈니스 개체의 데이터를 표시할 수 있습니다. 자세한 내용은 참조 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)합니다.  
  
## <a name="next-steps"></a>다음 단계  
 Excel 용 문서 수준 사용자 지정을 만드는 방법을 알아보려면 참조 [연습: 만들기 Your 첫 번째 문서 수준 사용자 지정 Excel에 대 한](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)합니다. 이 연습에서는 Visual Studio 및 Excel 문서 수준 사용자 지정에 대 한 프로그래밍 모델의 Office 개발 도구를 소개합니다.  
  
 Excel 프로젝트에서 일반적인 작업 중 일부을 다루는 항목의 목록에 대 한 참조 [Office 프로그래밍의 일반적인 작업](../vsto/common-tasks-in-office-programming.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [문서 수준 사용자 지정 프로그래밍](../vsto/programming-document-level-customizations.md)   
 [Excel 솔루션](../vsto/excel-solutions.md)   
 [연습: Excel 용 첫 문서 수준 사용자 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)   
 [Excel을 사용한 연습](../vsto/walkthroughs-using-excel.md)   
 [Excel 개체 모델 개요](../vsto/excel-object-model-overview.md)   
 [Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)  
  
  
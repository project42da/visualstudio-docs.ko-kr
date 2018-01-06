---
title: "Office 솔루션 개발 | Microsoft Docs"
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
- Office development in Visual Studio, about developing solutions
- solutions [Office development in Visual Studio], developing
- Office solutions [Office development in Visual Studio], developing
ms.assetid: 7361cfe0-dee4-48d7-a066-232f87f093ca
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: b15c9fbf2815132ac4ad84e3b321bb22db199ed2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="developing-office-solutions"></a>Office 솔루션 개발
  Visual Studio에서 Office 개발자 도구를 사용하여 프로젝트를 디자인하고 프로젝트 파일을 설정한 후 코드와 사용자 지정 UI(사용자 인터페이스)의 구현에 집중하기 시작할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  Office 환경을 확장 하는 솔루션을 개발에 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 체크 아웃 새 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능에서 VSTO 추가 기능 및 솔루션에 비해 적을 있고 거의 모든 웹 프로그래밍 HTML5, JavaScript, CSS3 및 XML 등의 기술을 사용 하 여 빌드할 수 있습니다.  
  
## <a name="office-solutions-programming-model"></a>Office 솔루션 프로그래밍 모델  
 Office 개체 모델은 프로그래밍의 대상이 될 수 있는 다양한 개체를 노출합니다. 관리 코드를 사용하여 Office 솔루션을 프로그래밍할 때마다 Office 주 interop 어셈블리의 형식을 사용하는 코드를 작성합니다. Visual Studio에서 Office 프로젝트 템플릿을 사용하여 만드는 솔루션에서 프로젝트의 생성된 클래스에 대해서도 직접 코드를 작성합니다. 자세한 내용은 [Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)을 참조하세요.  
  
## <a name="programming-different-types-of-office-solutions"></a>다양한 유형의 Office 솔루션 프로그래밍  
 만들고 있는 솔루션 유형에 따라 프로젝트에서 사용할 수 있는 기능이 결정됩니다. 예를 들어 디자인 타임에 Visual Studio의 *도구 상자*에서 항목을 끌어 Windows Forms 컨트롤과 확장된 Office 컨트롤( **호스트 컨트롤** 이라고 함)을 문서 수준 사용자 지정에 추가할 수 있습니다. 그러나 VSTO 추가 기능을 개발하는 경우에는 코드를 작성하여 이러한 종류의 컨트롤을 런타임에만 문서에 추가할 수 있습니다.  
  
 다양한 유형의 솔루션과 관련된 기능에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)을 참조하세요.  
  
-   [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md).  
  
-   [Office UI 사용자 지정](../vsto/office-ui-customization.md)합니다.  
  
 Office 솔루션의 계획에 유용한 배경 정보와 프로젝트를 만드는 데 도움이 되는 절차는 [Designing and Creating Office Solutions](../vsto/designing-and-creating-office-solutions.md)를 참조하세요.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[Writing Code in Office Solutions](../vsto/writing-code-in-office-solutions.md)|Office 솔루션에서 코드를 작성하는 경우의 다양한 측면에 대해 설명합니다.|  
|[Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)|VSTO 추가 기능 및 관련된 프로그래밍 작업의 프로그래밍 모델에 대해 개괄적으로 설명합니다.|  
|[Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)|문서 수준 사용자 지정 및 관련된 프로그래밍 작업의 프로그래밍 모델에 대해 개괄적으로 설명합니다.|  
|[Office UI 사용자 지정](../vsto/office-ui-customization.md)|VSTO 추가 기능과 문서 수준 사용자 지정을 사용하여 Office 응용 프로그램의 UI를 사용자 지정할 수 있는 다양한 방법에 대해 설명합니다.|  
|[Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)|문서 수준 사용자 지정에서 데이터를 컨트롤에 바인딩하거나 데이터를 캐싱하는 것과 같이 Office 솔루션에서 데이터로 작업할 수 있는 다양한 방법에 대해 설명합니다.|  
|[자동 저장이 Office 솔루션에 미치는 영향](./how-autosave-impacts-office-solutions.md)|자동 저장을 사용 하는 경우 Office 솔루션에 수행 해야 하는 조정에 설명 합니다.|
|[Office 솔루션 문제 해결](../vsto/troubleshooting-office-solutions.md)|Office 솔루션을 만들 때 발생할 수 있는 일반적인 문제의 해결에 대한 팁을 제공합니다.|  
|[Office의 스레딩 지원](../vsto/threading-support-in-office.md)|Office 솔루션에서 여러 스레드로 작업하는 방법에 대해 개괄적으로 설명합니다.|  
|[Office 프로젝트의 접근성](../vsto/accessibility-in-office-projects.md)|Office 솔루션에서 사용할 수 있는 내게 필요한 옵션 기능에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [방법: 사용자 지정 문서 속성 만들기 및 수정](../vsto/how-to-create-and-modify-custom-document-properties.md)   
 [방법:에서 읽기 및 문서 속성에 쓰기](../vsto/how-to-read-from-and-write-to-document-properties.md)   
 [방법: Office 다국어 사용자 인터페이스 대상](../vsto/how-to-target-the-office-multilingual-user-interface.md)   
 [연습: Excel용 첫 VSTO 추가 기능 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)   
 [연습: Excel 용 첫 문서 수준 사용자 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)   
 [연습: 첫 번째 VSTO 추가 기능에 Outlook에 대 한 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)   
 [연습: 첫 번째 VSTO 추가 기능에 PowerPoint에 대 한 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)   
 [연습: 첫 번째에 VSTO 추가 기능 프로젝트 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [연습: 첫 번째 VSTO 추가 기능에 Word에 대 한 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)   
 [연습: Word용 첫 문서 수준 사용자 지정 만들기](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)  
  
  
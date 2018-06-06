---
title: 프로젝트 솔루션
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [Office development in Visual Studio], Project
- Office solutions [Office development in Visual Studio], Project
- Project [Office development in Visual Studio]
- templates [Office development in Visual Studio], Project
- Office projects [Office development in Visual Studio], Project
- solutions [Office development in Visual Studio], Project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c3364c778b8dfc290ef06b7daa5ba063ac31f3db
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34692602"
---
# <a name="project-solutions"></a>프로젝트 솔루션
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] 에서는 Microsoft Office Project용 VSTO 추가 기능을 만드는 데 사용할 수 있는 프로젝트 템플릿을 제공합니다. VSTO 추가 기능을 사용하여 Project를 자동화하거나 Project 기능을 확장하거나 Project UI(사용자 인터페이스)를 사용자 지정할 수 있습니다.  
  
 VSTO 추가 기능에 대 한 자세한 내용은 참조 [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md) 및 [아키텍처의 VSTO 추가 기능](../vsto/architecture-of-vsto-add-ins.md)합니다. Microsoft Office를 사용한 프로그래밍을 처음 접하는 경우 참조 [시작 &#40;Visual Studio에서 Office 개발&#41;](../vsto/getting-started-office-development-in-visual-studio.md)합니다.  
  
 [!INCLUDE[appliesto_projallapp](../vsto/includes/appliesto-projallapp-md.md)]  
  
> [!NOTE]  
>  Office 환경을 확장 하는 솔루션을 개발에 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 체크 아웃 새 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능에서 VSTO 추가 기능 및 솔루션에 비해 적을 있고 거의 모든 웹 프로그래밍 HTML5, JavaScript, CSS3 및 XML 등의 기술을 사용 하 여 빌드할 수 있습니다.  
  
## <a name="automate-project-by-using-the-project-object-model"></a>Project 개체 모델을 사용 하 여 project를 자동화 합니다.  
 Project 개체 모델은 Project 자동화에 사용할 수 있는 다양한 형식을 노출합니다. 이러한 형식을 사용하면 프로젝트에서 프로그래밍 방식으로 작업을 만들고 수정하는 등의 일반 작업을 수행하도록 코드를 작성할 수 있습니다.  
  
 VSTO 추가 기능에서 Project 개체 모델에 액세스하려면 프로젝트에서 `Application` 클래스의 `ThisAddIn` 필드를 사용합니다. `Application` 반환 필드는 `Microsoft.Office.Interop.MsProject.Application` Project의 현재 인스턴스를 나타내는 개체입니다. 자세한 내용은 참조 [프로그램 VSTO 추가 기능](../vsto/programming-vsto-add-ins.md)합니다.  
  
 Project 개체 모델을 호출할 때 Project의 주 Interop 어셈블리에서 제공되는 형식을 사용합니다. 주 interop 어셈블리는 VSTO 추가 기능의 관리 코드와 Project의 COM 개체 모델 간의 다리 역할을 합니다. Project 주 interop 어셈블리의 모든 형식에 정의 된는 `Microsoft.Office.Interop.MSProject` 네임 스페이스입니다. 주 interop 어셈블리에 대 한 자세한 내용은 참조 [Office 솔루션 개발 개요 &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) 및 [Office 주 interop 어셈블리](../vsto/office-primary-interop-assemblies.md)합니다.  
  
## <a name="use-the-project-object-model-documentation"></a>Project 개체 모델 설명서 사용  
 Project 개체 모델에 대한 자세한 내용은 Project VBA 개체 모델 참조를 참조하세요. VBA 개체 모델 참조에서는 VBA(Visual Basic for Applications) 코드로 표시되는 Project 개체 모델에 대해 설명합니다. 자세한 내용은 참조 [Project 2010 개체 모델 참조](http://go.microsoft.com/fwlink/?LinkId=199771)합니다.  
  
 VBA 개체 모델 참조의 모든 개체 및 멤버는 Project PIA(주 interop 어셈블리)의 형식 및 멤버에 해당합니다. VBA 개체 모델 참조의 달력 개체에 해당 하는 예를 들어는 `Microsoft.Office.Interop.MSProject.Calendar` 는 Project PIA의 형식입니다. VBA 개체 모델 참조에서는 대부분의 속성, 메서드 및 이벤트에 대한 코드 예제를 제공하지만 Visual Studio를 사용하여 만든 Project VSTO 추가 기능 프로젝트에서 사용하려면 이 참조의 VBA 코드를 Visual Basic 또는 Visual C#으로 변환해야 합니다.  
  
> [!NOTE]  
>  이번에는 Project 주 interop 어셈블리에 대한 참조 설명서가 없습니다.  
  
### <a name="infrastructure-types-in-the-project-primary-interop-assembly"></a>Project 주 interop 어셈블리의 인프라 형식  
 Project PIA를 사용하는 코드를 작성할 때 VBA 참조에서 설명되지 않은 여러 형식을 알게 될 수 있습니다. 이러한 추가 형식은 Project의 COM 기반 개체 모델의 개체를 관리 코드로 변환할 수 있도록 지원하지만 코드에서 직접 사용하려는 것은 아닙니다.  
  
 자세한 내용은 참조 [Office 주 interop 어셈블리의 클래스와 인터페이스의 개요](http://go.microsoft.com/fwlink/?LinkId=189592)합니다.  
  
## <a name="customize-the-user-interface-of-project"></a>프로젝트의 사용자 인터페이스 사용자 지정  
 다음과 같은 방법으로 Project UI를 사용자 지정할 수 있습니다.  
  
|작업|추가 정보|  
|----------|--------------------------|  
|Project에서 리본에 사용자 지정 탭을 추가합니다.|[리본 개요](../vsto/ribbon-overview.md)|  
  
 UI 프로젝트와 기타 Microsoft Office 응용 프로그램 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [Office UI 사용자 지정](../vsto/office-ui-customization.md)합니다.  
  
## <a name="see-also"></a>참고자료  
 [연습: 첫 번째에 VSTO 추가 기능 프로젝트 만들기](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)   
 [VSTO 추가 기능 프로그래밍 시작](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office 솔루션 개발 개요 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO 추가 기능 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [VSTO 추가 기능 프로그래밍](../vsto/programming-vsto-add-ins.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [Office 주 interop 어셈블리](../vsto/office-primary-interop-assemblies.md)   
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Project 2010 및 Office 개발의 Project Server 2010](http://go.microsoft.com/fwlink/?LinkId=199016)  
  
  
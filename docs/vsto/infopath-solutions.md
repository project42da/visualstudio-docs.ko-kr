---
title: InfoPath 솔루션 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], InfoPath
- templates [Office development in Visual Studio], InfoPath
- InfoPath [Office development in Visual Studio]
- Office development in Visual Studio, InfoPath solutions
- projects [Office development in Visual Studio], InfoPath
- Office solutions [Office development in Visual Studio], InfoPath
- Office projects [Office development in Visual Studio], InfoPath
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9db28542e4141767be55241b98e0a6b762b0e236
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="infopath-solutions"></a>InfoPath 솔루션
  Visual Studio에서는 Microsoft Office InfoPath 2013 및 InfoPath 2010용 VSTO 추가 기능을 만드는 데 사용할 수 있는 프로젝트 템플릿을 제공합니다. InfoPath는 Office 2016에서 사용할 수 없습니다.  
  
> [!NOTE]  
>  여전히 만들면 VSTO 추가 기능에서 InfoPath 용 Office 2016을 설치한 경우에 됩니다. InfoPath 2013 또는 Office 2013을 Office 2016과 함께 설치하기만 하면 됩니다.  
  
 [!INCLUDE[appliesto_infoallapp](../vsto/includes/appliesto-infoallapp-md.md)]  
  
> [!NOTE]  
>  Office 환경을 확장 하는 솔루션을 개발에 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 체크 아웃 새 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능에서 VSTO 추가 기능 및 솔루션에 비해 적을 있고 거의 모든 웹 프로그래밍 HTML5, JavaScript, CSS3 및 XML 등의 기술을 사용 하 여 빌드할 수 있습니다.  
  
 InfoPath용 VSTO 추가 기능은 다른 Microsoft Office VSTO 추가 기능과 유사합니다. 이러한 유형의 솔루션은 응용 프로그램에 의해 로드되는 어셈블리로 구성됩니다. 최종 사용자는 열려 있는 양식이나 양식 서식 파일과 상관없이 이 어셈블리의 기능에 액세스할 수 있습니다. VSTO 추가 기능에 대한 자세한 내용은 [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md) 및 [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)를 참조하세요.  
  
> [!NOTE]  
>  Visual Studio 2015에는 이전 버전의 Visual Studio에서 제공된 InfoPath 양식 서식 파일 프로젝트가 포함되어 있지 않습니다. 또한 Visual Studio 2015를 사용하여 이전 버전의 Visual Studio에서 만든 InfoPath 양식 서식 파일 프로젝트를 열거나 편집할 수 없습니다. 그러나 Visual Studio Tools for Applications를 사용하여 InfoPath 양식 서식 파일 프로젝트를 열고 편집할 수 있습니다. 자세한 내용은 [InfoPath 2010에서 VSTO 2008 프로젝트 작업](http://go.microsoft.com/fwlink/?LinkID=218903)을 참조하세요.  
  
## <a name="automating-infopath-by-using-an-add-in"></a>추가 기능을 사용하여 InfoPath 자동화  
 Visual Studio에서 Office 개발 도구를 사용하여 만든 Office VSTO 추가 기능에서 InfoPath 개체 모델에 액세스하려면 프로젝트에서 `Application` 클래스의 `ThisAddIn` 필드를 사용합니다. `Application` 필드는 InfoPath의 현재 인스턴스를 나타내는 <xref:Microsoft.Office.Interop.InfoPath.Application> 개체를 반환합니다. 자세한 내용은 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)를 시작합니다.  
  
 VSTO 추가 기능에서 InfoPath 개체 모델을 호출할 때 InfoPath의 주 Interop 어셈블리에서 제공되는 형식을 사용합니다. 주 interop 어셈블리는 VSTO 추가 기능의 관리 코드와 InfoPath의 COM 개체 모델 간의 다리 역할을 합니다. InfoPath 주 interop 어셈블리의 모든 형식은 <xref:Microsoft.Office.Interop.InfoPath> 네임스페이스에서 정의됩니다. InfoPath 주 interop 어셈블리에 대한 자세한 내용은 [Microsoft Office InfoPath 주 Interop 어셈블리 정보](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)를 참조하세요. 주 interop 어셈블리에 대 한 자세한 내용은 참조 일반적으로 [Office 솔루션 개발 개요 &#40;VSTO&#41; ](../vsto/office-solutions-development-overview-vsto.md) 및 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)합니다.  
  
## <a name="customizing-the-user-interface-of-infopath-by-using-an-add-in"></a>추가 기능을 사용하여 InfoPath의 사용자 인터페이스 사용자 지정  
 InfoPath용 VSTO 추가 기능을 만들 때 몇 가지 UI 사용자 지정 옵션이 있습니다. 다음 표에 이러한 옵션 중 일부가 나와 있습니다.  
  
|작업|추가 정보|  
|----------|--------------------------|  
|사용자 지정 작업창을 만듭니다.|[사용자 지정 작업창](../vsto/custom-task-panes.md)|  
|InfoPath에서 리본에 사용자 지정 탭을 추가합니다.|[InfoPath에 대해 리본 사용자 지정](../vsto/customizing-a-ribbon-for-infopath.md)|  
  
 UI의 InfoPath와 기타 Microsoft Office 응용 프로그램 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [Office UI 사용자 지정](../vsto/office-ui-customization.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft Office InfoPath 주 Interop 어셈블리 정보](http://msdn.microsoft.com/en-us/1b3ae03c-6951-49e4-a489-4712d3f7ba72)   
 [Getting Started Programming VSTO Add-ins](../vsto/getting-started-programming-vsto-add-ins.md)   
 [Office 솔루션 개발 개요 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)   
 [VSTO 추가 기능 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [Office 주 Interop 어셈블리](../vsto/office-primary-interop-assemblies.md)   
 [Office UI 사용자 지정](../vsto/office-ui-customization.md)   
 [Office 개발의 InfoPath 2010](http://go.microsoft.com/fwlink/?LinkId=199012)  
  
  
---
title: Office 주 Interop 어셈블리 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies
- assemblies [Office development in Visual Studio], primary interop assemblies
- Office primary interop assemblies
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d1851fd05999bfc2d925cbe4a079be3a9f4139db
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693473"
---
# <a name="office-primary-interop-assemblies"></a>Office 주 Interop 어셈블리
  Office 프로젝트에서 Microsoft Office 응용 프로그램의 기능을 사용하려면 응용 프로그램용 PIA(주 interop 어셈블리)를 사용해야 합니다. PIA를 사용하면 관리 코드가 Microsoft Office 응용 프로그램의 COM 기반 개체 모델과 상호 작용할 수 있습니다.  
  
 새 Office 프로젝트를 만들 때 Visual Studio는 프로젝트를 빌드하는 데 필요한 PIA에 대한 참조를 추가합니다. Microsoft Office Excel용 프로젝트에서 Microsoft Office Word 기능을 사용해야 하는 등의 경우에는 추가 PIA에 대한 참조를 추가해야 할 수도 있습니다.  
  
 이 항목에서는 Office 프로젝트에서 Microsoft Office PIA를 사용하는 방법과 관련하여 다음 측면에 대해 설명합니다.  
  
-   [프로젝트 빌드 및 실행을 위한 개별 주 interop 어셈블리](#separateassemblies)  
  
-   [단일 프로젝트에서 여러 Microsoft Office 응용 프로그램의 기능을 사용 합니다.](#usingfeatures)  
  
-   [Microsoft Office 응용 프로그램용 주 interop 어셈블리의 전체 목록](#pialist)  
  
 주 interop 어셈블리에 대 한 자세한 내용은 참조 [주 interop 어셈블리](http://msdn.microsoft.com/en-us/b977a8be-59a0-40a0-a806-b11ffba5c080)합니다.  
  
##  <a name="separateassemblies"></a> 빌드 및 실행을 위한 개별 주 interop 어셈블리  
 Visual Studio에서는 개발 컴퓨터의 여러 PIA 집합을 사용합니다. 이러한 여러 어셈블리 집합은 다음 위치에 있습니다.  
  
-   프로그램 파일 디렉터리의 폴더  
  
     이러한 어셈블리 복사본은 코드를 작성하고 프로젝트를 빌드할 때 사용됩니다. Visual Studio에서는 이러한 어셈블리를 자동으로 설치합니다.  
  
-   전역 어셈블리 캐시  
  
     이러한 어셈블리 복사본은 프로젝트를 실행하거나 디버그하는 경우 등의 일부 개발 작업 중에 사용됩니다. 이러한 어셈블리는 Visual Studio에서 설치 및 등록하지 않으므로 직접 설치하고 등록해야 합니다.  
  
### <a name="primary-interop-assemblies-in-the-program-files-directory"></a>프로그램 파일 디렉터리의 주 interop 어셈블리  
 Visual Studio를 설치하면 PIA가 전역 어셈블리 캐시 외부의 파일 시스템 위치에 자동으로 설치됩니다. 새 프로젝트를 만들 때 Visual Studio는 이러한 PIA 복사본에 대한 참조를 프로젝트에 자동으로 추가합니다. Visual Studio는 전역 어셈블리 캐시의 어셈블리 대신 이러한 PIA 복사본을 사용하여 프로젝트를 개발 및 빌드할 때 형식 참조를 확인합니다.  
  
 Visual Studio는 이러한 PIA 복사본을 사용함으로써 전역 어셈블리 캐시에 각기 다른 PIA 버전이 등록되는 경우 발생할 수 있는 여러 개발 문제를 방지할 수 있습니다.  
  
 Visual Studio는 이러한 PIA 복사본을 개발 컴퓨터의 다음 위치에 설치합니다.  
  
-   *%ProgramFiles%\Microsoft visual Studio 12.0\Visual Studio Tools for Office\PIA\Office14*  
  
     (또는 *%ProgramFiles (x86) %\Microsoft Visual Studio 12.0\Visual Studio Tools for Office\PIA\Office14* 64 비트 운영 체제에서)  
  
-   *%ProgramFiles%\Microsoft visual Studio 12.0\Visual Studio Tools for Office\PIA\Office15*  
  
     (또는 *%ProgramFiles (x86) %\Microsoft Visual Studio 12.0\Visual Studio Tools for Office\PIA\Office15* 64 비트 운영 체제에서)  
  
### <a name="primary-interop-assemblies-in-the-global-assembly-cache"></a>전역 어셈블리 캐시의 주 interop 어셈블리  
 특정 개발 작업을 수행하려면 개발 컴퓨터의 전역 어셈블리 캐시에 PIA를 설치하고 등록해야 합니다. 일반적으로는 개발 컴퓨터에 Office를 설치할 때 PIA가 자동으로 설치됩니다. 자세한 내용은 참조 [Office 솔루션을 개발 하도록 컴퓨터 구성](../vsto/configuring-a-computer-to-develop-office-solutions.md)합니다.  
  
 최종 사용자 컴퓨터에서는 Office 솔루션을 실행하는 데 Office PIA가 필요하지 않습니다. 자세한 내용은 참조 [디자인 Office 솔루션을 만들 및](../vsto/designing-and-creating-office-solutions.md)합니다.  
  
##  <a name="usingfeatures"></a> 단일 프로젝트에서 여러 Microsoft Office 응용 프로그램의 기능을 사용 합니다.  
 Visual Studio의 각 Office 프로젝트 템플릿은 단일 Microsoft Office 응용 프로그램에서 사용하도록 설계되어 있습니다. 여러 Microsoft Office 응용 프로그램에서 기능을 사용하거나 Visual Studio에 프로젝트가 없는 응용 프로그램 또는 구성 요소에서 기능을 사용하려면 필요한 PIA에 대한 참조를 추가해야 합니다.  
  
 대부분의 경우에서 Visual Studio에서 Office\PIA *%ProgramFiles%\Microsoft Visual Studio 12.0\Visual Studio Tools에 설치 되어 있는 Pia에 대 한 참조를 추가 해야\* 디렉터리입니다. 이러한 어셈블리 버전은 **참조 관리자** 대화 상자의 **프레임워크** 탭에 표시됩니다. 자세한 내용은 참조 [하는 방법: 주 interop 어셈블리를 통해 대상 Office 응용 프로그램](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)합니다.  
  
 전역 어셈블리 캐시에서 PIA를 설치 및 등록한 경우 이러한 어셈블리 버전은 **참조 관리자** 대화 상자의 **COM** 탭에 표시됩니다. 이러한 어셈블리 버전에 대한 참조는 추가해서는 안 됩니다. 해당 버전을 사용하는 경우 몇 가지 개발 문제가 발생할 수 있습니다. 예를 들어 전역 어셈블리 캐시에 여러 PIA 버전을 등록한 경우에는 **참조 관리자** 대화 상자의 **COM** 탭에서 다른 어셈블리 버전을 지정하더라도 프로젝트는 마지막으로 등록된 어셈블리 버전에 자동으로 바인딩됩니다.  
  
> [!NOTE]  
>  일부 어셈블리는 해당 어셈블리를 참조하는 어셈블리를 추가할 때 프로젝트에 자동으로 추가됩니다. 예를 들어에 대 한 참조는 *Office.dll* 및 *Microsoft.Vbe.Interop.dll* Word, Excel, Outlook, Microsoft Forms 또는 Graph에 대 한 참조를 추가 하면 어셈블리가 자동으로 추가 됩니다 어셈블리입니다.  
  
##  <a name="pialist"></a> Microsoft Office 응용 프로그램에 대 한 주 interop 어셈블리  
 다음 테이블에는 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 및 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]에 사용 가능한 주 interop 어셈블리가 나와 있습니다.  
  
|Office 응용 프로그램 또는 구성 요소|주 interop 어셈블리 이름|  
|-------------------------------------|-----------------------------------|  
|Microsoft Access 14.0 개체 라이브러리<br /><br /> Microsoft Access 15.0 개체 라이브러리|Microsoft.Office.Interop.Access.dll|  
|Microsoft Office 14.0 Access 데이터베이스 엔진 개체 라이브러리<br /><br /> Microsoft Office 15.0 Access 데이터베이스 엔진 개체 라이브러리|Microsoft.Office.Interop.Access.Dao.dll|  
|Microsoft Excel 14.0 개체 라이브러리<br /><br /> Microsoft Excel 15.0 개체 라이브러리|Microsoft.Office.Interop.Excel.dll|  
|Microsoft Graph 14.0 개체 라이브러리(PowerPoint, Access 및 Word에서 그래프에 사용됨)<br /><br /> Microsoft Graph 15.0 개체 라이브러리|Microsoft.Office.Interop.Graph.dll|  
|Microsoft InfoPath 2.0 형식 라이브러리(InfoPath 2007에만 해당함)|Microsoft.Office.Interop.InfoPath.dll|  
|Microsoft InfoPath XML Interop 어셈블리(InfoPath 2007에만 해당함)|Microsoft.Office.Interop.InfoPath.Xml.dll|  
|Microsoft Office 14.0 개체 라이브러리(Office 공유 기능)<br /><br /> Microsoft Office 15.0 개체 라이브러리(Office 공유 기능)|office.dll|  
|Microsoft Office Outlook 뷰 컨트롤(웹 페이지와 응용 프로그램에서 받은 편지함에 액세스하는 데 사용할 수 있음)|Microsoft.Office.Interop.OutlookViewCtl.dll|  
|Microsoft Outlook 14.0 개체 라이브러리<br /><br /> Microsoft Outlook 15.0 개체 라이브러리|Microsoft.Office.Interop.Outlook.dll|  
|Microsoft PowerPoint 14.0 개체 라이브러리<br /><br /> Microsoft PowerPoint 15.0 개체 라이브러리|Microsoft.Office.Interop.PowerPoint.dll|  
|Microsoft Project 14.0 개체 라이브러리<br /><br /> Microsoft Project 15.0 개체 라이브러리|Microsoft.Office.Interop.MSProject.dll|  
|Microsoft Publisher 14.0 개체 라이브러리<br /><br /> Microsoft Publisher 15.0 개체 라이브러리|Microsoft.Office.Interop.Publisher.dll|  
|Microsoft SharePoint Designer 14.0 웹 개체 참조 라이브러리|Microsoft.Office.Interop.SharePointDesigner.dll|  
|Microsoft SharePoint Designer 14.0 페이지 개체 참조 라이브러리|Microsoft.Office.Interop.SharePointDesignerPage.dll|  
|Microsoft 스마트 태그 2.0 형식 라이브러리 **참고:** 에 스마트 태그가 사용 되지 않습니다 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] 및 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]합니다.|Microsoft.Office.Interop.SmartTag.dll|  
|Microsoft Visio 14.0 형식 라이브러리<br /><br /> Microsoft Visio 15.0 형식 라이브러리|Microsoft.Office.Interop.Visio.dll|  
|Microsoft Visio 14.0 웹으로 저장 형식 라이브러리<br /><br /> Microsoft Visio 15.0 웹으로 저장 형식 라이브러리|Microsoft.Office.Interop.Visio.SaveAsWeb.dll|  
|Microsoft Visio 14.0 드로잉 컨트롤 형식 라이브러리<br /><br /> Microsoft Visio 15.0 드로잉 컨트롤 형식 라이브러리|Microsoft.Office.Interop.VisOcx.dll|  
|Microsoft Word 14.0 개체 라이브러리<br /><br /> Microsoft Word 15.0 개체 라이브러리|Microsoft.Office.Interop.Word.dll|  
|Microsoft Visual Basic for Applications Extensibility 5.3|Microsoft.Vbe.Interop.dll|  
  
### <a name="binding-redirect-assemblies"></a>바인딩 리디렉션 어셈블리  
 Office PIA를 Office와 함께 또는 PIA의 재배포 가능 패키지를 설치하여 전역 어셈블리 캐시에 설치 및 등록하면 바인딩 리디렉션 어셈블리도 전역 어셈블리 캐시에만 설치됩니다. 이러한 어셈블리는 주 interop 어셈블리의 올바른 버전이 런타임에 로드는 있는지 확인할 수 있습니다. 예를 들어 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] 어셈블리를 참조하는 솔루션이 같은 주 interop 어셈블리의 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 버전이 설치된 컴퓨터에서 실행되면 바인딩 리디렉션 어셈블리는 주 interop 어셈블리의 [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] 버전을 로드하도록 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 런타임에 명령합니다. 자세한 내용은 참조 [하는 방법: 자동 바인딩 리디렉션 사용 안 함 및 사용 하도록 설정](/dotnet/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection)합니다.  
  
## <a name="see-also"></a>참고자료  
 [방법: 주 interop 어셈블리를 통해 대상 Office 응용 프로그램](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Excel 개체 모델 개요](../vsto/excel-object-model-overview.md)   
 [InfoPath 솔루션](../vsto/infopath-solutions.md)   
 [Outlook 개체 모델 개요](../vsto/outlook-object-model-overview.md)   
 [PowerPoint 솔루션](../vsto/powerpoint-solutions.md)   
 [프로젝트 솔루션](../vsto/project-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [Word 개체 모델 개요](../vsto/word-object-model-overview.md)   
 [일반 참조 &#40;Visual Studio에서 Office 개발&#41;](../vsto/general-reference-office-development-in-visual-studio.md)  
  
  
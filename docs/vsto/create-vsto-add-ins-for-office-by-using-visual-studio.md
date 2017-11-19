---
title: "Visual Studio를 사용 하 여 Office 용 VSTO 추가 기능 만들기 | Microsoft Docs"
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
ms.assetid: eabd0377-cb94-4c1e-a99c-f13ff8df1a87
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d3006ddafa743a5cd55a687895e894f3cbb068a9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="create-vsto-add-ins-for-office-by-using-visual-studio"></a>Visual Studio를 사용하여 Office용 VSTO 추가 기능 만들기
  Visual Studio의 Microsoft Office 개발자 도구를 사용하여 Office를 확장하는 .NET Framework 응용 프로그램을 만들 수 있습니다. 이러한 응용 프로그램을 *Office 솔루션*이라고도 합니다.  
  
 Office 개발자 도구는 다양한 비즈니스 요구 사항에 맞는 Office 솔루션을 만드는 데 사용할 수 있는 기능을 제공합니다. 이 도구에는 Visual Basic 또는 Visual C#을 사용하여 Office 솔루션을 만들 수 있는 프로젝트 템플릿과 Office 솔루션용 사용자 지정 사용자 인터페이스를 만들 수 있는 비주얼 디자이너가 포함되어 있습니다.  
  
> [!NOTE]  
>  Office 환경을 확장 하는 솔루션을 개발에 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 체크 아웃 새 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능에서 VSTO 추가 기능 및 솔루션에 비해 적을 있고 거의 모든 웹 프로그래밍 HTML5, JavaScript, CSS3 및 XML 등의 기술을 사용 하 여 빌드할 수 있습니다.  
  
 Office 개발에 대한 최신 정보는 MSDN에서 다음 개발 센터를 참조하세요.  
  
-   [Visual Studio 개발자 포털을 통한 Office 개발](http://go.microsoft.com/fwlink/?LinkId=123844) 에서는 Visual Studio를 사용하여 솔루션의 일부분으로 Office 응용 프로그램을 사용자 지정하는 방법과 관련한 제품 정보, 코드 샘플, 동영상 및 커뮤니티 리소스의 링크를 제공합니다.  
  
-   [Microsoft Office 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=83467) 에서는 Office 사용자 지정 및 OBA(Office 비즈니스 응용 프로그램)과 관련한 기술 문서, 코드 샘플, 다운로드, 커뮤니티 정보, 지원 및 기타 설명서의 링크를 제공합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [시작 &#40; Visual Studio &#41;에서 Office 개발](../vsto/getting-started-office-development-in-visual-studio.md)  
 Office 솔루션을 만들기 위해 개발 컴퓨터를 구성하는 방법, Office 솔루션 만들기를 시작하는 방법 및 Visual Studio에 포함된 Office 개발용 새 기능에 대한 정보 링크를 제공합니다.  
  
 [Office 솔루션 업그레이드 및 마이그레이션](../vsto/upgrading-and-migrating-office-solutions.md)  
 이전 버전의 Visual Studio를 사용하여 만든 프로젝트의 업그레이드 프로세스에 대한 정보 링크를 제공합니다.  
  
 [Visual Studio의 Office 솔루션 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
 문서 수준 사용자 지정과 VSTO 추가 기능 관련 정보를 비롯한 Office 솔루션의 작동 방식에 대한 정보의 링크를 제공합니다.  
  
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
 Visual Studio에서 Office 프로젝트를 만들고 프로젝트를 구성하는 방법에 대한 정보를 제공합니다.  
  
 [Office 솔루션 개발](../vsto/developing-office-solutions.md)  
 Office 사용자 인터페이스를 사용자 지정하고 데이터를 사용하고 문제를 해결하는 방법을 비롯하여 Office 솔루션에서 관리 코드를 사용하는 방법에 대한 정보를 제공합니다.  
  
 [Excel 솔루션](../vsto/excel-solutions.md)  
 Excel을 자동화하고 Excel 솔루션을 만들고 Excel과 관련된 세계화 문제를 이해하는 방법에 대한 정보를 제공합니다.  
  
 [InfoPath 솔루션](../vsto/infopath-solutions.md)  
 InfoPath용 양식 템플릿 및 VSTO 추가 기능을 만드는 방법에 대한 정보를 제공합니다.  
  
 [Outlook 솔루션](../vsto/outlook-solutions.md)  
 Outlook을 자동화하고 Outlook VSTO 추가 기능 및 양식 영역을 만드는 방법에 대한 정보를 제공합니다.  
  
 [PowerPoint 솔루션](../vsto/powerpoint-solutions.md)  
 PowerPoint를 자동화하고 PowerPoint VSTO 추가 기능을 만드는 방법에 대한 정보를 제공합니다.  
  
 [Project 솔루션](../vsto/project-solutions.md)  
 Microsoft Office Project를 자동화하고 Project VSTO 추가 기능을 만드는 방법에 대한 정보를 제공합니다.  
  
 [Visio 솔루션](../vsto/visio-solutions.md)  
 Visio를 자동화하고 Visio VSTO 추가 기능을 만드는 방법에 대한 정보를 제공합니다.  
  
 [Word 솔루션](../vsto/word-solutions.md)  
 Word를 자동화하고 Word 솔루션을 만드는 방법에 대한 정보를 제공합니다.  
  
 [Office 솔루션 빌드](../vsto/building-office-solutions.md)  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 Office 프로젝트와 기타 유형의 프로젝트를 빌드하는 방식 간의 차이점에 대한 정보를 제공합니다.  
  
 [Office 프로젝트 디버깅](../vsto/debugging-office-projects.md)  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 Office 프로젝트와 기타 유형의 프로젝트를 디버그하는 방식 간의 차이점에 대한 정보를 제공합니다.  
  
 [Office 솔루션 보안](../vsto/securing-office-solutions.md)  
 Office 솔루션의 보안 기능 작동 방식에 대한 정보를 제공합니다.  
  
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
 사용자에게 Office 솔루션을 제공하는 방법과 배포 방법을 선택할 때 고려해야 하는 중요한 문제에 대한 정보를 제공합니다.  
  
 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)  
 일반적인 작업을 수행하기 위한 단계별 지침을 제공하는 항목과 샘플 응용 프로그램에 대한 링크를 제공합니다.  
  
 [일반 참조 &#40; Visual Studio &#41;에서 Office 개발](../vsto/general-reference-office-development-in-visual-studio.md)  
 Office 주 interop 어셈블리, 매니페스트, 사용자 인터페이스 요소 및 오류 메시지에 대한 자세한 정보를 확인할 수 있는 링크를 제공합니다.  
  
 [관리 참조 &#40; Visual Studio &#41;에서 Office 개발](../vsto/managed-reference-office-development-in-visual-studio.md)  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]를 대상으로 하는 Office 프로젝트에서 사용되는 API 네임스페이스 및 형식 관련 정보의 링크를 제공합니다. .NET Framework 3.5를 대상으로 하는 Office 프로젝트에서 사용되는 네임스페이스 및 형식에 대한 API 참조 설명서는 Visual Studio 2008 설명서에서 [2007 시스템 관리되는 참조](http://go.microsoft.com/fwlink/?LinkId=160658)참조 섹션을 참조하세요.  
  
 [관리 되지 않는 API 참조 &#40; Visual Studio &#41;에서 Office 개발](../vsto/unmanaged-api-reference-office-development-in-visual-studio.md)  
 Office 응용 프로그램의 관리되는 VSTO 추가 기능 로드/언로드와 같은 작업을 수행하는 데 사용할 수 있는 COM 인터페이스 관련 정보에 대한 링크를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Visual Studio 개발자 포털을 통한 Office 개발](http://go.microsoft.com/fwlink/?LinkId=123844)  
 기술 문서, 비디오, 블로그 등의 추가 리소스를 제공합니다.  
  
 [Visual Studio 개발자 센터](http://go.microsoft.com/fwlink/?LinkID=99124)  
 기술 문서, 비디오, 블로그 등의 추가 Visual Studio 리소스를 제공합니다.  
  
 [Office 비즈니스 응용 프로그램 개발자 포털](http://go.microsoft.com/fwlink/?LinkId=99125)  
 OBA(Office 비즈니스 응용 프로그램)에 대한 정보를 제공하고 Office 시스템 플랫폼을 사용하여 OBA를 빌드하는 방법을 설명합니다.  
  
 [MSDN 라이브러리의 Microsoft Office 개발 섹션](http://go.microsoft.com/fwlink/?LinkId=149870)  
 Visual Studio를 사용한 Office 개발에 국한되지 않고 다양한 Office 버전용으로 솔루션을 개발하는 방법에 대한 문서와 참조 설명서를 찾을 수 있는 MSDN 라이브러리 영역입니다.  
  
 [Visual Studio에서 응용 프로그램 개발](http://msdn.microsoft.com/en-us/97490c1b-a247-41fb-8f2c-bc4c201eff68)  
 Visual Studio를 사용하여 웹 응용 프로그램, XML 웹 서비스 및 기존의 클라이언트 응용 프로그램을 디자인/개발/디버그/배포하는 방법을 설명하는 항목의 링크를 제공합니다.  
  
 [Visual Studio의 .NET Framework 프로그래밍](http://msdn.microsoft.com/en-us/f3f63195-82c6-48e8-a4a0-612810e7d093)  
 Visual Basic 및 Visual C#에서 .NET Framework를 사용하여 응용 프로그램을 개발하는 방법을 설명합니다.  
  
  
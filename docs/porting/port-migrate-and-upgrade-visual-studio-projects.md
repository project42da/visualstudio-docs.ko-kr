---
title: "Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드 | Microsoft Docs"
ms.custom: 
ms.date: 2/27/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Win8ExpressDesktopBlock
- w8trefactor
- VS.ReviewProjectAndSolutionChangesDialog.UpgradeRetarget
- ProjectCompatibilityDlgHelpTopic
- VS.ReviewProjectAndSolutionChangesDialog.Upgrade
helpviewer_keywords:
- conversion, projects
- asset compatibility
- projects, conversion
ms.assetid: bee759bd-6ff5-4c2e-913a-ea7d3c906c29
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: 7c10c85c6bb6a300a117cd4a08cf80280cb431db
ms.openlocfilehash: 16458816633f954da30b8ca78ff6f6ae0f2fced5
ms.lasthandoff: 04/11/2017

---
# <a name="port-migrate-and-upgrade-visual-studio-projects"></a>Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드

새 버전의 Visual Studio에서는 일반적으로 이전 형식의 프로젝트, 파일 및 기타 자산을 대부분 지원합니다. 이러한 항목을 이전처럼 사용할 수 있습니다. 최신 기능에 의존하지 않을 경우 Visual Studio에서는 Visual Studio 2015, Visual Studio 2013, Visual Studio 2012 등과 같은 이전 버전과의 호환성을 유지합니다. 버전별로 특정한 기능은 [릴리스 정보](https://www.visualstudio.com/vs/release-notes/)를 참조하세요.

일부 형식 변경은 이후에 지원될 수 있습니다. 최신 버전의 Visual Studio에서 특정 형식을 더 이상 지원하지 않거나, 더 이상 이전 버전과 호환되지 않도록 마이그레이션 및 업데이트해야 할 수 있습니다. 이 항목에서는 Visual Studio 2017에서 영향을 받는 프로젝트 형식에 대해 자세히 설명합니다. Visual Studio 2017에 대해 지원되는 형식 목록은 [플랫폼 대상 지정 및 호환성](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs) 항목을 참조하세요.

> [!Note]
> 특정 프로젝트 형식을 열려면 Visual Studio 설치 관리자를 통해 적절한 워크로드를 추가해야 합니다.


## <a name="projects"></a>프로젝트

다음 목록에서는 이전 버전에서 만든 프로젝트에 대한 Visual Studio 2017의 지원에 대해 설명합니다. 여기에 나열된 프로젝트 또는 파일 형식이 표시되지 않는 경우 [이 항목의 Visual Studio 2015 버전](https://msdn.microsoft.com/library/hh266747.aspx)을 참조하고 아래 설명에 유의하세요.

| 프로젝트 형식 | Support(지원) |
| --- | --- |
| .NET Core 프로젝트(.xproj) | Visual Studio 2015에서 .xproj 프로젝트 파일을 포함하는 미리 보기 도구를 사용하여 만든 프로젝트입니다. Visual Studio 2017에서 .xproj 파일을 열면 파일을 .csproj 형식으로 마이그레이션(.xproj 파일의 백업이 생성됨)하라는 메시지가 표시됩니다. .NET Core 프로젝트에 대한 이 .csproj 형식은 VS2015 이전 버전에서 지원되지 않습니다.  .xproj 형식은 .csproj로 마이그레이션해야 만 Visual Studio 2017에서 지원됩니다. 자세한 내용은 [.csproj 형식으로 .NET Core 프로젝트 마이그레이션](https://docs.microsoft.com/dotnet/articles/core/migration/#visual-studio-2017)을 참조하세요.|
| Application Insights를 사용하도록 지정한 ASP.NET 웹 응용 프로그램 및 ASP.NET Core 웹 응용 프로그램 | 각 Visual Studio 사용자의 리소스 정보가 사용자 인스턴스별 레지스트리에 저장됩니다. 사용자가 프로젝트를 열지 않고 Azure Application Insights 데이터를 검색하려는 경우에 사용됩니다. Visual Studio 2015에서는 Visual Studio 2017과 다른 레지스트리 위치를 사용하므로 충돌하지 않습니다.<br/><br/>사용자가 ASP.NET 웹 응용 프로그램 또는 ASP.NET Core 웹 응용 프로그램을 만들면 리소스가 .suo 파일에 저장됩니다. 사용자는 Visual Studio 2015 또는 2017에서 프로젝트를 열 수 있으며, Visual Studio에서 두 버전 간 사용 중인 프로젝트 및 솔루션이 지원될 경우 두 버전 모두에서 리소스 정보가 사용됩니다. 사용자는 각 제품에 대해 한 번 인증해야 합니다. 예를 들어 Visual Studio 2015에서 프로젝트를 만든 다음 Visual Studio 2017에서 열 경우 사용자는 Visual Studio 2017에서 인증해야 합니다. |
| C#/Visual Basic Webform 또는 Windows Form | Visual Studio 2017 및 Visual Studio 2015에서 프로젝트를 열 수 있습니다. |
| 데이터베이스 단위 테스트 프로젝트(.csproj, .vbproj)    | 이전 데이터 단위 테스트 프로젝트는 Visual Studio 2017에 로드되지만 GAC'd 종속성 버전을 사용합니다. 최신 종속성을 사용하도록 단위 테스트 프로젝트를 업그레이드하려면 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **SQL Server 단위 테스트 프로젝트로 변환...**을 선택합니다. |
| F# | Visual Studio 2017에서는 Visual Studio 2013 및 2015에서 만든 프로젝트를 열 수 있습니다. 이러한 프로젝트에서 Visual Studio 2017 기능을 사용하려면 프로젝트 속성을 열고 대상 fsharp.core를 F# 4.1로 변경합니다. |
| InstallShield<br/>MSI 설정 | Visual Studio 2010에서 만든 설치 관리자 프로젝트는 [Visual Studio 설치 관리자 프로젝트 확장](https://marketplace.visualstudio.com/items?itemName=UnniRavindranathan-MSFT.MicrosoftVisualStudio2013InstallerProjects)을 사용하여 이후 버전에서 열 수 있습니다. [InstallShield Limited Edition](https://blogs.msdn.microsoft.com/visualstudio/2013/08/15/whats-new-in-visual-studio-2013-and-installshield-limited-edition/)을 사용하여 이러한 프로젝트를 유지할 수도 있습니다. |
| LightSwitch | LightSwitch는 Visual Studio 2017에서 더 이상 지원되지 않습니다. Visual Studio 2012 이전 버전에서 만든 프로젝트 Visual Studio 2013 또는 Visual Studio 2015에서 열면 파일이 업그레이드되므로 이후에는 Visual Studio 2013 또는 Visual Studio 2015에서만 열 수 있습니다. |
| Visual Studio용 Microsoft Azure 도구 | 이러한 형식의 프로젝트를 열려면 먼저 [Azure SDK for.NET](http://azure.microsoft.com/en-us/downloads/)을 설치한 다음 프로젝트를 엽니다. 필요한 경우 프로젝트를 업데이트합니다. |
| 모델-뷰-컨트롤러 프레임워크(ASP.NET MVC) | MVC 버전 및 Visual Studio 지원:<ul><li>Visual Studio 2010 SP1은 MVC 2 및 MVC 3을 지원합니다. MVC 4 지원은 [Visual Studio 2010 SP1용 ASP.NET 4 MVC 4 다운로드](https://www.microsoft.com/en-us/download/details.aspx?id=30683)를 통해 추가됩니다.</li><li>Visual Studio 2012에서는 MVC 3 및 MVC 4만 지원합니다.</li><li>Visual Studio 2013에서는 MVC 4 및 MVC 5만 지원합니다.</li><li>Visual Studio 2017 및 Visual Studio 2015에서는 MVC 4(기존 프로젝트를 열 수 있지만 새 프로젝트를 만들 수 없음) 및 MVC 5를 지원합니다.</li></ul><br/><br/>MVC 버전 업그레이드:<ul><li>MVC 2에서 MCV 3로 자동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 3 응용 프로그램 업그레이더](http://go.microsoft.com/fwlink/?LinkID=238178)를 참조하세요.</li><li>MVC 2에서 MVC 3로 수동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 3 도구 업데이트로 ASP.NET MVC 2 프로젝트 업그레이드](http://go.microsoft.com/fwlink/?linkid=238178)를 참조하세요.</li><li>MVC 3에서 MVC 4로 수동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 3 프로젝트를 ASP.NET MVC 4로 업그레이드](http://www.asp.net/whitepapers/mvc4-release-notes)를 참조하세요. 프로젝트 대상이 .NET Framework 3.5 SP1일 경우 대상을 변경하여 .NET Framework 4를 사용해야 합니다.</li><li>MVC 4에서 MVC 5로 수동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 4 및 Web API 프로젝트를 ASP.NET MVC 5 및 Web API 2로 업그레이드하는 방법](https://www.asp.net/mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2)을 참조하세요.</li></ul> |
| 모델링 | Visual Studio에서 프로젝트를 자동으로 업데이트하도록 허용하면 Visual Studio 2015, Visual Studio 2013 또는 Visual Studio 2012에서 프로젝트를 열 수 있습니다.<br/><br/>모델링 프로젝트의 형식은 Visual Studio 2015 및 Visual Studio 2017 간에 변경되지 않으므로 어느 버전에서든 프로젝트를 열고 수정할 수 있습니다. 하지만 Visual Studio 2017의 동작에 차이가 있습니다.<ul><li>모델링 프로젝트를 메뉴 및 템플릿에서 "종속성 유효성 검사" 프로젝트라고 합니다.</li><li>UML 다이어그램은 Visual Studio 2017에서 더 이상 지원되지 않습니다. UML 파일은 솔루션 탐색기에 이전처럼 나열되지만 XML 파일로 열립니다. UML 다이어그램을 보거나, 만들거나, 편집하려면 Visual Studio 2015를 사용하세요.</li><li>Visual Studio 2017에서는 모델링 프로젝트를 빌드할 때 더 이상 아키텍처 종속성 유효성 검사가 수행되지 않습니다. 대신 각 코드 프로젝트를 빌드할 때 유효성 검사가 수행됩니다. 이 변경은 모델링 프로젝트에 영향을 주지 않지만 유효성을 검사할 코드 프로젝트를 변경해야 합니다. Visual Studio 2017에서는 필요한 경우 코드 프로젝트를 자동으로 변경할 수 있습니다([자세한 정보](http://go.microsoft.com/fwlink/?LinkId=827800)).</li></ul> |
| MSI 설정(.vdproj) | 위의 InstallShield 프로젝트를 참조하세요. | 
| Office 2007 VSTO | Visual Studio 2017에 단방향 업그레이드가 필요합니다. |
| Office 2010 VSTO | 프로젝트 대상이 .NET Framework 4일 경우 Visual Studio 2010 SP1 이상에서 이 프로젝트를 열 수 있습니다. 다른 모든 프로젝트에는 단방향 업그레이드가 필요합니다. |
| SharePoint 2010 | Visual Studio 2017을 사용하여 SharePoint 솔루션 프로젝트를 열면 SharePoint 2013 또는 SharePoint 2016으로 업그레이드됩니다. ".NET 데스크탑 개발" 워크로드는 업그레이드를 위해 Visual Studio 2017에 설치되어야 합니다.<br/><br/>SharePoint 프로젝트를 업그레이드하는 방법에 대한 자세한 내용은 [SharePoint 2013으로 업그레이드](https://technet.microsoft.com/en-us/library/cc303420.aspx), [SharePoint Server 2013에서 워크플로 업데이트](https://technet.microsoft.com/en-us/library/dn133867.aspx) 및 [데이터베이스 연결 업그레이드를 위해 SharePoint Server 2016 팜 만들기](https://technet.microsoft.com/en-us/library/cc263026(v=office.16).aspx)를 참조하세요. |
| SharePoint 2016 | Office 개발자 도구 미리 보기 2에서 만든 SharePoint 추가 기능 프로젝트를 Visual Studio 2017에서 열 수 없습니다. 이 문제를 해결하려면 `.csproj` 또는 `.vbproj` 파일에 있는 `MinimumVisualStudioVersion`을 12.0로 업데이트하고 `MinimumOfficeToolsVersion`를 12.2로 업데이트해야 합니다. |
| Silverlight | Silverlight 프로젝트는 Visual Studio 2017에서 지원되지 않습니다. Silverlight 응용 프로그램을 유지하려면 Visual Studio 2015를 계속 사용합니다. |
| SQL Server Reporting Services, SQL Server Analysis Services(SSDT, SSAS, MSAS, SSDT) | 이러한 프로젝트 형식에 대한 지원은 Visual Studio 갤러리의 [Microsoft Analysis Servides Modeling Projects](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects) 및 [Microsoft Report Projects for Visual Studio](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio)라는 두 개의 확장을 통해 제공됩니다. |
| Visual C++ | Visual Studio 2017를 사용하여 Visual Studio 2015에서 만든 솔루션 및 프로젝트를 그대로 열 수 있지만, 더 이전 버전의 Visual Studio에서 만든 프로젝트의 경우 Visual Studio 2017에서 빌드하려면 프로젝트를 업그레이드하거나 최신 도구 집합으로 대상을 변경해야 합니다. 자세한 내용은 [방법: Visual C++ 프로젝트를 Visual Studio 2015로 업그레이드](https://msdn.microsoft.com/en-us/library/hh690665.aspx) 및 [Visual C++ 포팅 및 업그레이드 가이드](https://msdn.microsoft.com/en-us/library/dn986839.aspx)를 참조하세요. |
| Visual Studio 확장성/VSIX | MinimumVersion 14.0 이하의 프로젝트는 업데이트를 통해 MinimumVersion 15.0으로 선언됩니다. 그러면 이전 버전의 Visual Studio에서 프로젝트를 열 수 없습니다. 이전 버전에서 프로젝트를 열 수 있도록 허용하려면 MinimumVersion을 `$(VisualStudioVersion)`(으)로 설정합니다. [방법: Visual Studio 2017로 확장성 프로젝트 마이그레이션](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)을 참조하세요. |
| Visual Studio Lab Management | Microsoft Test Manager 또는 Visual Studio 2010 SP1 이상을 사용하여 이러한 버전에서 만든 환경을 열 수 있습니다. 그러나 Visual Studio 2010 SP1의 경우 환경을 만들기 전에 Microsoft Test Manager 버전이 Team Foundation Server 버전과 일치해야 합니다. |
| Apache Cordova용 Visual Studio Tools |이 프로젝트는 Visual Studio 2017에서 열 수 있지만 이전 버전과 호환되지 않습니다. Visual Studio 2015에서 프로젝트를 열면 프로젝트를 수정하도록 허용할지 여부를 묻는 메시지가 표시됩니다. 그러면 프로젝트에서 `taco.json` 파일 대신 도구 집합을 사용하여 Cordova 라이브러리, 플랫폼 및 플러그인의 버전과 노드/npm 종속성을 관리하도록 업그레이드됩니다. 자세한 내용은 [마이그레이션 가이드](http://taco.visualstudio.com/docs/vs-taco-2017-migration/)를 참조하세요. |
| Windows Communication Foundation, Windows Workflow Foundation | Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 및 Visual Studio 2012에서 이 프로젝트를 열 수 있습니다. |
| Windows Presentation Foundation | Visual Studio 2013, Visual Studio 2012 및 Visual Studio 2010 SP1에서 이 프로젝트를 열 수 있습니다. |
| Windows 스토어/전화 앱 | Visual Studio 2017에서는 Windows 스토어 8.1 및 8.0, Windows Phone 8.1 및 8.0용 프로젝트가 지원되지 않습니다. 이러한 앱을 유지하려면 Visual Studio 2015를 계속 사용합니다. Windows Phone 7.x 프로젝트를 유지하려면 Visual Studio 2012를 사용합니다. |
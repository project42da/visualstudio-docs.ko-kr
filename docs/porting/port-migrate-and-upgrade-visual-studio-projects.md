---
title: Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드 | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
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
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 65d1a8edac3de969528b6d27ed540d791d3d08f6
ms.sourcegitcommit: 236c250bb97abdab99d00c6525d106fc0035d7d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2018
---
# <a name="port-migrate-and-upgrade-visual-studio-projects"></a>Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드

새 버전의 Visual Studio에서는 일반적으로 이전 형식의 프로젝트, 파일 및 기타 자산을 대부분 지원합니다. 이러한 항목을 [이전처럼](../ide/solutions-and-projects-in-visual-studio.md) 사용할 수 있습니다. 최신 기능에 의존하지 않을 경우 Visual Studio에서는 일반적으로 Visual Studio 2015, Visual Studio 2013, Visual Studio 2012 등과 같은 이전 버전과의 호환성을 유지하려 합니다. 버전별로 특정한 기능은 [릴리스 정보](https://www.visualstudio.com/vs/release-notes/)를 참조하세요.

일부 프로젝트 형식 변경은 이후에 지원될 수 있습니다. 최신 버전의 Visual Studio에서 특정 프로젝트를 더 이상 지원하지 않거나, 더 이상 이전 버전과 호환되지 않도록 프로젝트를 업데이트할 수 있습니다. 마이그레이션 문제의 현재 상태는 [Visual Studio 개발자 커뮤니티 사이트](https://developercommunity.visualstudio.com)를 참조하세요.

> [!Important]
> 이 현재 문서에서는 마이그레이션과 관련된 Visual Studio 2017의 프로젝트 형식에 대한 세부 정보만 제공합니다. 마이그레이션 문제가 없는 지원되는 프로젝트 형식은 포함되지 않습니다. 해당 목록은 [플랫폼 대상 지정 및 호환성](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs)에서 확인할 수 있습니다. 또한 일부 프로젝트 형식은 Visual Studio 2017에서 더 이상 지원되지 않으므로 마이그레이션할 수 없습니다.

> [!Important]
> 특정 프로젝트 형식은 Visual Studio 설치 관리자를 통해 적절한 워크로드를 설치해야 합니다. 워크로드가 설치되어 있지 않으면 Visual Studio에서 알 수 없거나 호환되지 않는 프로젝트 형식을 보고합니다. 이 경우 설치 옵션을 확인하고 다시 시도하세요. Visual Studio 2017의 프로젝트 지원에 대한 자세한 내용은 [플랫폼 대상 지정 및 호환성](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs) 문서를 참조하세요.

## <a name="project-types"></a>프로젝트 형식

다음 목록에서는 이전 버전에서 만든 프로젝트에 대한 Visual Studio 2017의 지원에 대해 설명합니다.

여기에 나열된 프로젝트 또는 파일 형식이 표시되지 않는 경우 [이 문서의 Visual Studio 2015 버전](https://msdn.microsoft.com/library/hh266747.aspx)을 참조하고 이 페이지의 맨 아래에 “설명서 사용자 의견 제공” 옵션을 사용하여 프로젝트의 세부 정보를 제공해 주세요. (응답을 원하는 경우 익명으로 “이 페이지가 도움이 되었나요?”라고 하기 보다는 설명서 사용자 의견을  사용합니다.)

| 프로젝트 형식 | Support(지원) |
| --- | --- |
| .NET Core 프로젝트(.xproj) | Visual Studio 2015로 만든 프로젝트는 xproj 프로젝트 파일을 포함하는 미리 보기 도구를 사용했습니다. Visual Studio 2017에서 xproj 파일을 열면 파일을 csproj 형식으로 마이그레이션(xproj 파일의 백업이 생성됨)하라는 메시지가 표시됩니다. .NET Core 프로젝트의 이 csproj 형식은 Visual Studio 2015 및 이전 버전에서 지원되지 않습니다.  xproj 형식은 csproj로 마이그레이션해야만 Visual Studio 2017에서 지원됩니다. 자세한 내용은 [csproj 형식으로 .NET Core 프로젝트 마이그레이션](/dotnet/core/migration/#visual-studio-2017)을 참조하세요.|
| Application Insights를 사용하도록 지정한 ASP.NET 웹 응용 프로그램 및 ASP.NET Core 웹 응용 프로그램 | 각 Visual Studio 사용자의 리소스 정보가 사용자 인스턴스별 레지스트리에 저장됩니다. 이 정보는 사용자가 프로젝트를 열지 않고 Azure Application Insights 데이터를 검색하려는 경우에 사용됩니다. Visual Studio 2015에서는 Visual Studio 2017과 다른 레지스트리 위치를 사용하므로 충돌하지 않습니다.<br/><br/>사용자가 ASP.NET 웹 응용 프로그램 또는 ASP.NET Core 웹 응용 프로그램을 만들면 리소스가 .suo 파일에 저장됩니다. 사용자는 Visual Studio 2015 또는 2017에서 프로젝트를 열 수 있으며, Visual Studio에서 두 버전 간 사용 중인 프로젝트 및 솔루션이 지원될 경우 두 버전 모두에서 리소스 정보가 사용됩니다. 사용자는 각 제품에 대해 한 번 인증해야 합니다. 예를 들어 Visual Studio 2015에서 프로젝트를 만든 다음 Visual Studio 2017에서 열 경우 사용자는 Visual Studio 2017에서 인증해야 합니다. |
| C#/Visual Basic Webform 또는 Windows Form | Visual Studio 2017 및 Visual Studio 2015에서 프로젝트를 열 수 있습니다. |
| 데이터베이스 유닛 테스트 프로젝트(csproj, .vbproj) | 이전 데이터 유닛 테스트 프로젝트는 Visual Studio 2017에 로드되지만 GAC 종속성 버전을 사용합니다. 최신 종속성을 사용하도록 단위 테스트 프로젝트를 업그레이드하려면 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **SQL Server 단위 테스트 프로젝트로 변환...**을 선택합니다. |
| F# | Visual Studio 2017에서는 Visual Studio 2013 및 2015에서 만든 프로젝트를 열 수 있습니다. 이러한 프로젝트에서 Visual Studio 2017 기능을 사용하려면 프로젝트 속성을 열고 대상 fsharp.core를 F# 4.1로 변경합니다. Visual Studio 설치 관리자의 **F# 언어 지원** 옵션은 기본적으로 .NET 워크로드와 함께 선택되지 않습니다. 워크로드에 대해 해당 옵션을 선택하거나 **개발 작업** 아래 **개별 구성 요소** 탭에서 해당 옵션을 선택하여 포함해야 합니다. |
| InstallShield<br/>MSI 설정 | Visual Studio 2010에서 만든 설치 관리자 프로젝트는 [Visual Studio 설치 관리자 프로젝트 확장](https://marketplace.visualstudio.com/items?itemName=UnniRavindranathan-MSFT.MicrosoftVisualStudio2013InstallerProjects)을 사용하여 이후 버전에서 열 수 있습니다. 또한 [WiX 도구 집합 Visual Studio 2017 확장](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)을 참조하세요. InstallShield Limited Edition은 더 이상 Visual Studio에 포함되지 않습니다. Visual Studio 2017에 대한 가용성은 [Flexera Software](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio)에서 확인하세요. |
| LightSwitch | LightSwitch는 Visual Studio 2017에서 더 이상 지원되지 않습니다. Visual Studio 2012 이전 버전에서 만들고 Visual Studio 2013 또는 Visual Studio 2015에서 연 프로젝트는 업그레이드되며 이후에는 Visual Studio 2013 또는 Visual Studio 2015에서만 열 수 있습니다. |
| Visual Studio용 Microsoft Azure 도구 | 이러한 형식의 프로젝트를 열려면 먼저 [Azure SDK for.NET](http://azure.microsoft.com/downloads/)을 설치한 다음 프로젝트를 엽니다. 필요한 경우 프로젝트가 업데이트됩니다. |
| 모델-뷰-컨트롤러 프레임워크(ASP.NET MVC) | MVC 버전 및 Visual Studio 지원:<ul><li>Visual Studio 2010 SP1은 MVC 2 및 MVC 3을 지원합니다. MVC 4 지원은 [Visual Studio 2010 SP1용 ASP.NET 4 MVC 4 다운로드](https://www.microsoft.com/download/details.aspx?id=30683)를 통해 추가됩니다.</li><li>Visual Studio 2012에서는 MVC 3 및 MVC 4만 지원합니다.</li><li>Visual Studio 2013에서는 MVC 4 및 MVC 5만 지원합니다.</li><li>Visual Studio 2017 및 Visual Studio 2015에서는 MVC 4(기존 프로젝트를 열 수 있지만 새 프로젝트를 만들 수 없음) 및 MVC 5를 지원합니다.</li></ul><br/>MVC 버전 업그레이드:<ul><li>MVC 2에서 MVC 3로 자동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 3 응용 프로그램 업그레이더](http://go.microsoft.com/fwlink/?LinkID=238178)를 참조하세요.</li><li>MVC 2에서 MVC 3로 수동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 3 도구 업데이트로 ASP.NET MVC 2 프로젝트 업그레이드](http://go.microsoft.com/fwlink/?linkid=238178)를 참조하세요.</li><li>MVC 3에서 MVC 4로 수동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 3 프로젝트를 ASP.NET MVC 4로 업그레이드](http://www.asp.net/whitepapers/mvc4-release-notes)를 참조하세요. 프로젝트 대상이 .NET Framework 3.5 SP1일 경우 대상을 변경하여 .NET Framework 4를 사용해야 합니다.</li><li>MVC 4에서 MVC 5로 수동 업그레이드하는 방법에 대한 자세한 내용은 [ASP.NET MVC 4 및 Web API 프로젝트를 ASP.NET MVC 5 및 Web API 2로 업그레이드하는 방법](https://www.asp.net/mvc/overview/releases/how-to-upgrade-an-aspnet-mvc-4-and-web-api-project-to-aspnet-mvc-5-and-web-api-2)을 참조하세요.</li></ul> |
| 모델링 | Visual Studio에서 프로젝트를 자동으로 업데이트하도록 허용하면 Visual Studio 2015, Visual Studio 2013 또는 Visual Studio 2012에서 프로젝트를 열 수 있습니다.<br/><br/>모델링 프로젝트의 형식은 Visual Studio 2015 및 Visual Studio 2017 간에 변경되지 않으므로 어느 버전에서든 프로젝트를 열고 수정할 수 있습니다. 하지만 Visual Studio 2017의 동작에 차이가 있습니다.<ul><li>모델링 프로젝트를 메뉴 및 템플릿에서 “종속성 유효성 검사” 프로젝트라고 합니다.</li><li>UML 다이어그램은 Visual Studio 2017에서 더 이상 지원되지 않습니다. UML 파일은 솔루션 탐색기에 이전처럼 나열되지만 XML 파일로 열립니다. UML 다이어그램을 보거나, 만들거나, 편집하려면 Visual Studio 2015를 사용하세요.</li><li>Visual Studio 2017에서는 모델링 프로젝트를 빌드할 때 더 이상 아키텍처 종속성 유효성 검사가 수행되지 않습니다. 대신 각 코드 프로젝트를 빌드할 때 유효성 검사가 수행됩니다. 이 변경은 모델링 프로젝트에 영향을 주지 않지만 유효성을 검사할 코드 프로젝트를 변경해야 합니다. Visual Studio 2017에서는 필요한 경우 코드 프로젝트를 자동으로 변경할 수 있습니다([자세한 정보](http://go.microsoft.com/fwlink/?LinkId=827800)).</li></ul> |
| MSI 설정(vdproj) | InstallShield 프로젝트를 참조하세요. |
| Office 2007 VSTO | Visual Studio 2017에 단방향 업그레이드가 필요합니다. |
| Office 2010 VSTO | 프로젝트 대상이 .NET Framework 4일 경우 Visual Studio 2010 SP1 이상에서 이 프로젝트를 열 수 있습니다. 다른 모든 프로젝트에는 단방향 업그레이드가 필요합니다. |
| Service Fabric(sfproj) | Service Fabric 응용 프로그램 프로젝트가 ASP.NET Core 서비스 프로젝트를 참조하지 않을 경우 Visual Studio 2015 또는 Visual Studio 2017에서 Service Fabric 응용 프로그램 프로젝트를 열 수 있습니다. Visual Studio 2015의 Service Fabric 프로젝트를 Visual Studio 2017에서 여는 경우 xproj 형식에서 csproj 형식으로 단방향 마이그레이션됩니다. 이 표에서 앞부분에 있는 “.NET Core 프로젝트(xproj)”를 참조하세요. |
| SharePoint 2010 | Visual Studio 2017을 사용하여 SharePoint 솔루션 프로젝트를 열면 SharePoint 2013 또는 SharePoint 2016으로 업그레이드됩니다. 업그레이드를 위해서는 “.NET 데스크톱 개발” 워크로드가 Visual Studio 2017에 설치되어 있어야 합니다.<br/><br/>SharePoint 프로젝트를 업그레이드하는 방법에 대한 자세한 내용은 [SharePoint 2013으로 업그레이드](https://technet.microsoft.com/library/cc303420.aspx), [SharePoint Server 2013에서 워크플로 업데이트](https://technet.microsoft.com/library/dn133867.aspx) 및 [데이터베이스 연결 업그레이드를 위해 SharePoint Server 2016 팜 만들기](https://technet.microsoft.com/library/cc263026(v=office.16).aspx)를 참조하세요. |
| SharePoint 2016 | Office 개발자 도구 미리 보기 2에서 만든 SharePoint 추가 기능 프로젝트를 Visual Studio 2017에서 열 수 없습니다. 이 제한을 해결하려면 csproj 또는 vbproj 파일에 있는 `MinimumVisualStudioVersion`을 12.0으로, `MinimumOfficeToolsVersion`을 12.2로 업데이트합니다. |
| Silverlight | Silverlight 프로젝트는 Visual Studio 2017에서 지원되지 않습니다. Silverlight 응용 프로그램을 유지하려면 Visual Studio 2015를 계속 사용합니다. |
| SQL Server Reporting Services 및 SQL Server Analysis Services(SSRS, SSDT, SSAS, MSAS) | 이러한 프로젝트 형식에 대한 지원은 Visual Studio Gallery에서 [Microsoft Analysis Services Modeling Projects](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftAnalysisServicesModelingProjects) 및 [Microsoft Reporting Services Projects](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio)라는 두 개의 확장을 통해 제공됩니다. SSDT는 Visual Studio 2017에서 데이터 저장 및 처리 워크로드를 지원합니다. |
| SSIS(SQL Server Integration Services) | Visual Studio 2017에 대한 지원은 SSDT(SQL Server Data Tools)를 통해 제공됩니다. 자세한 내용은 [SQL Server Integration Services 블로그](https://blogs.msdn.microsoft.com/ssis/2017/08/23/ssis-designer-is-now-available-for-visual-studio-2017/)를 참조하세요. |
| Visual C++ | Visual Studio 2017을 사용하여 Visual Studio 2010까지 이전 버전의 Visual Studio에서 만든 프로젝트에서 작업할 수 있습니다. 프로젝트를 처음 열면 최신 컴파일러 및 도구 집합으로 업그레이드하거나 원래 항목을 계속 사용하는 옵션이 있습니다. 원래 항목을 계속 사용하도록 선택하면 Visual Studio 2017에서는 프로젝트 파일을 수정하지 않으며 이전 Visual Studio 설치의 도구 집합을 사용하여 프로젝트를 빌드합니다. 원래 옵션을 유지하는 것은 필요한 경우 원래 버전의 Visual Studio에서 프로젝트를 열 수 있음을 의미합니다. 자세한 내용은 [Visual Studio의 네이티브 멀티 타기팅을 사용하여 이전 프로젝트 빌드](/cpp/porting/use-native-multi-targeting)를 참조하세요. |
| Visual Studio 확장성/VSIX | MinimumVersion 14.0 이하의 프로젝트는 업데이트를 통해 MinimumVersion 15.0으로 선언됩니다. 그러면 이전 버전의 Visual Studio에서 프로젝트를 열 수 없습니다. 이전 버전에서 프로젝트를 열 수 있도록 허용하려면 MinimumVersion을 `$(VisualStudioVersion)`(으)로 설정합니다. [방법: Visual Studio 2017로 확장성 프로젝트 마이그레이션](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)을 참조하세요. |
| Visual Studio Lab Management | Microsoft Test Manager 또는 Visual Studio 2010 SP1 이상을 사용하여 이러한 버전에서 만든 환경을 열 수 있습니다. 그러나 Visual Studio 2010 SP1의 경우 환경을 만들기 전에 Microsoft Test Manager 버전이 Team Foundation Server 버전과 일치해야 합니다. |
| Apache Cordova용 Visual Studio Tools | Visual Studio 2017에서 프로젝트를 열 수는 있지만 이전 버전과 호환되지 않습니다. Visual Studio 2015에서 프로젝트를 열면 프로젝트를 수정하도록 허용할지 여부를 묻는 메시지가 표시됩니다. 이 수정은 프로젝트에서 `taco.json` 파일 대신 도구 집합을 사용하여 Cordova 라이브러리의 버전, 플랫폼 및 플러그인, 노드/npm 종속성을 관리하도록 업그레이드합니다. 자세한 내용은 [마이그레이션 가이드](https://docs.microsoft.com/visualstudio/cross-platform/tools-for-cordova/first-steps/migrate-from-visual-studio-2015)를 참조하세요. |
| 웹 배포(wdproj) | 게시 프로필 지원이 추가되면서 Visual Studio 2012에서 웹 배포 프로젝트 지원이 제거되었습니다. Visual Studio 2017에 동등한 기능이 없으므로 이러한 프로젝트에 대한 자동 마이그레이션 경로는 없습니다. 대신, [StackOverflow](https://stackoverflow.com/a/12061065/1203388)에 설명된 대로 텍스트 편집기에서 wdproj 파일을 열고 사용자 지정을 복사하여 pubxml(게시 프로필) 파일에 붙여넣습니다. 또한 [Plans regarding website and web deployment projects](https://blogs.msdn.microsoft.com/webdev/2012/08/06/plans-regarding-website-projects-and-web-deployment-projects)(웹 사이트 및 웹 배포 프로젝트에 관한 계획)(MSDN 블로그)를 참조하세요. |
| Windows Communication Foundation, Windows Workflow Foundation | Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 및 Visual Studio 2012에서 이 프로젝트를 열 수 있습니다. |
| Windows Presentation Foundation | Visual Studio 2013, Visual Studio 2012 및 Visual Studio 2010 SP1에서 이 프로젝트를 열 수 있습니다. |
| Windows 스토어/전화 앱 | Visual Studio 2017에서는 Windows 스토어 8.1 및 8.0, Windows Phone 8.1 및 8.0용 프로젝트가 지원되지 않습니다. 이러한 앱을 유지하려면 Visual Studio 2015를 계속 사용합니다. Windows Phone 7.x 프로젝트를 유지하려면 Visual Studio 2012를 사용합니다. |

## <a name="how-visual-studio-decides-when-to-migrate-a-project"></a>Visual Studio가 프로젝트를 마이그레이션하는 시기를 결정하는 방식

새 버전의 각 Visual Studio는 일반적으로 동일한 프로젝트가 다른 버전에서 열리고 수정되고 빌드될 수 있도록 이전 버전과 호환성을 유지하려 합니다. 그러나 일부 프로젝트 형식이 더 이상 지원되지 않을 정도로 시간이 흐르면 변경을 피할 수가 없습니다. (Visual Studio 2017에서 지원되는 프로젝트 형식에 대한 [플랫폼 타키팅 및 호환성](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs)을 참조합니다.) 이러한 경우에는 최신 버전의 Visual Studio가 프로젝트를 로드하지 않고 마이그레이션 경로를 제공하지 않습니다. Visual Studio 이전 버전의 프로젝트가 이를 지원하도록 유지해야 하기 때문입니다.

다른 경우에 최신 버전의 Visual Studio는 프로젝트를 열 수 있지만 이전 버전과 호환되지 않게 렌더링하는 방식으로 프로젝트를 업데이트하거나 마이그레이션해야 합니다. Visual Studio는 이러한 마이그레이션이 필요한지 여부를 결정하는 많은 기준을 사용합니다.

- Visual Studio 2013 RTM으로 돌아간 플랫폼의 대상 버전과의 호환성.

- Visual Studio 이전 버전과 디자인 타임 자산의 호환성. (즉 Visual Studio 2017의 다른 채널, Visual Studio 2015 RTM 및 업데이트 3, Visual Studio 2013 RTM 및 업데이트 5, Visual Studio 2012 업데이트 4, Visual Studio 2010 SP 1.) Visual Studio 2017은 이전 버전에서 프로젝트를 열 수 있을 정도로 더 이상 사용되지 않는 디자인 타임 자산을 손상시키지 않는 것을 목표로 합니다.

- 새로운 디자인 타임 자산이 이전 버전 Visual Studio 2013 RTM & 업데이트 5와의 호환성을 중단하는지 여부.

문제의 프로젝트 유형의 엔지니어링 소유자는 이러한 기준을 지향하며 지원, 호환성 및 마이그레이션이 관련된 위치에서 호출을 합니다. Visual Studio는 가능한 Visual Studio 버전 간에 투명한 호환성을 유지하려 합니다. 이는 Visual Studio의 한 버전에서 프로젝트를 만들고 수정할 수 있고 다른 버전에서도 작동한다는 의미입니다.

그러나 이 아티클에 설명된 일부 프로젝트 유형에서처럼 이러한 호환성이 가능하지 않은 경우 Visual Studio는 업그레이드 마법사를 열고 필요한 단방향 변경을 합니다.

이러한 단방향 변경이 프로젝트 파일에서 `ToolsVersion` 속성의 변경을 포함할 수 있습니다. 이는 정확하게 MSBuild의 버전이 프로젝트의 소스 코드를 사용자가 원하는 실행가능하고 배포가능한 아티팩트로 바꿀 수 있음을 나타냅니다. 곧 이전 버전의 Visual Studio와 호환되지 않는 프로젝트를 렌더링한 것은 *Visual Studio* 버전이 아니라 `ToolsVersion`에서 결정한 대로 *MSBuild* 버전입니다. Visual Studio 버전이 프로젝트의 `ToolsVersion`과 일치하는 MSBuild 도구 체인을 포함하는 한은 Visual Studio는 해당 도구 체인이 프로젝트를 빌드하도록 호출할 수 있습니다.

이전 버전에서 만든 프로젝트와 최대한 호환성을 유지하기 위해 Visual Studio 2017은 `ToolsVersion` 15, 14, 12 및 4를 지원하는 데 필요한 MSBuild 도구 체인을 포함합니다. 이러한 `ToolsVersion` 값 중 하나를 사용하는 프로젝트는 성공적인 빌드를 발생해야 합니다. ([플랫폼 대상 지정 및 호환성](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs)에 설명된 대로 Visual Studio 2017이 프로젝트 형식을 항상 지원하는지 여부의 주제.)

이 컨텍스트에서 수동으로 프로젝트를 최신 `ToolsVersion` 값으로 업데이트하거나 마이그레이션해야 하는지 여부의 의문이 자연스럽게 발생합니다. 이러한 변경은 필요하지 않으며, 프로젝트를 다시 빌드하도록 수정해야 하는 많은 오류 및 경고를 발생시킬 가능성이 있습니다. 또한 Visual Studio가 향후 특정 `ToolsVersion`에 대한 지원을 중단하는 경우 특히 `ToolsVersion` 값을 변경해야 하기 때문에 프로젝트를 열면 프로젝트 마이그레이션 프로세스를 트리거하게 됩니다. 이러한 경우 해당 특정 프로젝트 형식에 대한 하위 시스템은 변경될 사항을 정확히 알고 이 아티클의 앞에서 설명한 대로 자동으로 이러한 변경을 수행할 수 있습니다.

자세한 논의 내용은 다음 아티클을 참조하십시오.

- [ToolsVersion 지침](../msbuild/msbuild-toolset-toolsversion.md)
- [프레임워크 대상 지정 지침](../ide/visual-studio-multi-targeting-overview.md)

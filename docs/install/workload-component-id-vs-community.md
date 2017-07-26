---
title: "Visual Studio Community 2017 작업 및 구성 요소 ID | Microsoft Docs"
description: "작업 및 구성 요소 ID를 사용하여 명령줄로 Visual Studio를 설치하거나 VSIX 매니페스트에서 종속성으로 지정합니다."
keywords: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.date: 05/10/2017
ms.topic: article
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.prod: visual-studio-dev15
ms.service: 
ms.technology:
- vs-ide-install
- vs-ide-sdk
ms.assetid: 58494fc3-12de-4761-bd4a-74b54f72bfb3
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: bca3912b5ff1ce9e58717af4b58c66b6a8f09b03
ms.contentlocale: ko-kr
ms.lasthandoff: 05/13/2017

---

# <a name="visual-studio-community-2017-workload-and-component-ids"></a>Visual Studio Community 2017 작업 및 구성 요소 ID

이 페이지의 표에는 명령줄을 사용하여 Visual Studio를 설치하는 데 사용할 수 있는 ID 또는 VSIX 매니페스트에서 종속성으로 지정할 수 있는 ID가 나열되어 있습니다. Visual Studio에 대한 업데이트를 릴리스할 때 추가 구성 요소가 추가될 것입니다.

또한 이 페이지에 대해 다음 사항에 유의하세요.

* 각 작업에는 고유한 섹션 및 작업 ID와 해당 작업에 사용할 수 있는 구성 요소 표가 있습니다.
* 기본적으로 **필수** 구성 요소는 작업을 설치할 때 설치됩니다. 원하는 경우 **권장** 및 **선택적** 구성 요소를 설치할 수도 있습니다.
* 작업과 관련이 없는 추가 구성 요소를 나열하는 섹션도 추가했습니다.

VSIX 매니페스트에 종속성을 설정하는 경우 구성 요소 ID만 지정해야 합니다. 이 페이지의 표를 사용하여 최소 구성 요소 종속성을 확인합니다. 일부 시나리오에서는 작업에서 하나의 구성 요소만 지정한다고 의미할 수 있습니다. 다른 시나리오에서는 단일 작업에서 여러 구성 요소를 지정하거나 여러 작업에서 여러 구성 요소를 지정한다고 의미할 수 있습니다. 자세한 내용은 [방법: 확장성 프로젝트를 Visual Studio 2017로 마이그레이션](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) 페이지를 참조하세요.

이러한 ID를 사용하는 방법에 대한 자세한 내용은 [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md) 페이지를 참조하세요. 다른 제품의 작업 및 구성 요소 ID 목록은 [Visual Studio 2017 작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요.


## <a name="visual-studio-core-editor-included-with-visual-studio-community-2017"></a>Visual Studio 핵심 편집기(Visual Studio 커뮤니티 2017에 포함)

**ID:** Microsoft.VisualStudio.Workload.CoreEditor

**설명:** 구문 인식 코드 편집, 원본 코드 제어 및 작업 항목 관리를 포함하는 Visual Studio 핵심 셸 환경입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 15.0.26208.0 | 필수


## <a name="azure-development"></a>Azure 개발

**ID:** Microsoft.VisualStudio.Workload.Azure

**설명:** 클라우드 앱을 개발하고 리소스를 만들기 위한 Azure SDK, 도구 및 프로젝트입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | 필수
Microsoft.Component.NetFX.Core.Runtime | .NET Core 런타임 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.Net.Core.Component.SDK | .NET Core 1.0.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.NetCore.ComponentGroup.Web | .NET Core 1.0 - 1.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.CloudExplorer | 클라우드 탐색기 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.ComponentGroup.Azure.Prerequisites | Azure 개발 필수 구성 요소 | 15.0.26323.1 | 필수
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 권장
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake 도구 | 15.0.26208.0 | 권장
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 - 4.6 개발 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | 권장
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 계산 에뮬레이터 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.Azure.MobileAppsSdk | Azure Mobile Apps SDK | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Azure.ResourceManager.Tools | Azure Resource Manager 핵심 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Azure.ServiceFabric.Tools | Service Fabric 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 15.0.26424.2 | 권장
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services 핵심 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 권장
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server 명령줄 유틸리티 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 권장
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 15.0.26323.1 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.ComponentGroup.Azure.CloudServices | Azure Cloud Services 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.ComponentGroup.Azure.ResourceManager.Tools | Azure Resource Manager 도구 | 15.0.26323.1 | 권장
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.0.26419.1 | 선택적
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 15.0.26419.1 | 선택적
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.Azure.Storage.AzCopy | Azure Storage AzCopy | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.PowerShell.Tools | PowerShell 도구 | 3.0.427 | Optional
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | Optional


## <a name="data-storage-and-processing"></a>데이터 저장소 및 처리

**ID:** Microsoft.VisualStudio.Workload.Data

**설명:** SQL Server, Azure Data Lake, Hadoop 또는 Azure ML을 사용하여 데이터 솔루션을 연결, 개발 및 테스트합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Redgate.ReadyRoll | Redgate ReadyRoll | 1.13.22.3147 | 권장
Component.Redgate.SQLPrompt.VsPackage | Redgate SQL 프롬프트 | 7.4.1.767 | 권장
Component.Redgate.SQLSearch.VSExtension | SQL Redgate 검색 | 2.3.10.1131 | 권장
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 권장
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake 도구 | 15.0.26208.0 | 권장
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 권장
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 - 4.6 개발 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | 권장
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 계산 에뮬레이터 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 15.0.26424.2 | 권장
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services 핵심 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.CloudExplorer | 클라우드 탐색기 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 권장
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 권장
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server 명령줄 유틸리티 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 권장
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 15.0.26323.1 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 15.0.26208.0 | 선택적


## <a name="data-science-and-analytical-applications"></a>데이터 과학 및 분석 응용 프로그램

**ID:** Microsoft.VisualStudio.Workload.DataScience

**설명:** Python, R 및 F#을 포함하여 데이터 과학 응용 프로그램을 만들기 위한 언어 및 도구입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.Anaconda3.x64 | Anaconda3 64비트(4.3.0.1) | 4.3.0.2 | 권장
Microsoft.Component.CookiecutterTools | Cookiecutter 템플릿 지원 | 15.0.26419.1 | 권장
Microsoft.Component.PythonTools | Python 언어 지원 | 15.0.26419.1 | 권장
Microsoft.Component.PythonTools.Web | Python 웹 지원 | 15.0.26419.1 | 권장
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 권장
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.R.Open | Microsoft R Client(3.3.2) | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.RHost | R 개발 도구에 대한 런타임 지원 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.RTools | R 언어 지원 | 15.0.26419.1 | 권장
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.0.26208.0 | 권장
Component.Anaconda2.x64 | Anaconda2 64비트(4.3.0.1) | 4.3.0.2 | 선택적
Component.Anaconda2.x86 | Anaconda2 32비트(4.3.0.1) | 4.3.0.2 | 선택적
Component.Anaconda3.x86 | Anaconda3 32비트(4.3.0.1) | 4.3.0.2 | 선택적
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python 네이티브 개발 도구 | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Win81 | 그래픽 도구 Windows 8.1 SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.140 | VC++ 2015.3 v140 도구 집합(x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK(10.0.10586.0) | 15.0.26208.0 | Optional


## <a name="net-desktop-development"></a>.NET 데스크톱 개발

**ID:** Microsoft.VisualStudio.Workload.ManagedDesktop

**설명:** .NET Framework를 사용하여 WPF, Windows Forms 및 콘솔 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 필수
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Debugger.JustInTime | Just-In-Time 디버거 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 15.0.26419.1 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET 데스크톱 개발 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 필수
Microsoft.ComponentGroup.Blend | Blend for Visual Studio | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 - 4.6 개발 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26208.0 | 권장
Component.Dotfuscator | PreEmptive Protection - Dotfuscator | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.0.26419.1 | 선택적
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 15.0.26419.1 | 선택적
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 15.0.26419.1 | 선택적
Microsoft.Net.Core.Component.SDK | .NET Core 1.0.1 개발 도구 | 15.0.26208.0 | Optional
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET Core 1.0 - 1.1 개발 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | 코드 복제본 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | 코드 맵 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | 실시간 종속성 유효성 검사 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | 아키텍처 및 분석 도구 | 15.0.26208.0 | Optional


## <a name="game-development-with-unity"></a>Unity를 사용한 게임 개발

**ID:** Microsoft.VisualStudio.Workload.ManagedGame

**설명:** 강력한 플랫폼 간 개발 환경인 Unity를 사용하여 2D 및 3D 게임을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Unity | Visual Studio Tools for Unity | 15.0.26323.1 | 필수
Component.UnityEngine | Unity 5.6 편집기 | 15.0.26430.4 | 권장


## <a name="linux-development-with-c"></a>C++를 사용한 Linux 개발

**ID:** Microsoft.VisualStudio.Workload.NativeCrossPlat

**설명:** Linux 환경에서 실행되는 응용 프로그램을 만들고 디버그합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.MDD.Linux | Linux 개발용 Visual C++ | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 15.0.26208.0 | 필수


## <a name="desktop-development-with-c"></a>C++를 사용한 데스크톱 개발

**ID:** Microsoft.VisualStudio.Workload.NativeDesktop

**설명:** Visual C++ 도구 집합, ATL 및 선택적 기능(예: MFC 및 C++/CLI)을 사용하여 기존 Windows 기반 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.ClassDesigner | 클래스 디자이너 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.CodeMap | 코드 맵 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Debugger.JustInTime | Just-In-Time 디버거 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Native | C++용 아키텍처 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Core | Visual C++ 핵심 데스크톱 기능 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Graphics.Win81 | 그래픽 도구 Windows 8.1 SDK | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VC.CMake.Project | CMake용 Visual C++ 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | 데스크톱 C++ x86 및 x64용 Windows 10 SDK(10.0.15063.0) | 15.0.26403.0 | 권장
Component.Incredibuild | IncrediBuild | 15.0.26228.0 | Optional
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.140 | VC++ 2015.3 v140 도구 집합(x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL 지원 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | MFC 및 ATL 지원(x86 및 x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2(실험적) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CLI.Support | C++/CLI 지원 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | 표준 라이브러리 모듈 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK(10.0.10240.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK(10.0.10586.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK(10.0.14393.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.WinXP | C++용 Windows XP 지원 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK 및 UCRT SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | C++용 Windows XP 지원 | 15.0.26208.0 | Optional


## <a name="game-development-with-c"></a>C++를 사용한 게임 개발

**ID:** Microsoft.VisualStudio.Workload.NativeGame

**설명:** C++의 모든 기능을 사용하여 DirectX, Unreal 또는 Cocos2d로 구동하는 전문 게임을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Graphics.Win81 | 그래픽 도구 Windows 8.1 SDK | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | 데스크톱 C++ x86 및 x64용 Windows 10 SDK(10.0.15063.0) | 15.0.26403.0 | 권장
Component.Cocos | Cocos | 15.0.26323.1 | Optional
Component.Incredibuild | IncrediBuild | 15.0.26228.0 | Optional
Component.Unreal | 언리얼 엔진 설치 관리자 | 15.0.26323.1 | Optional
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 - 4.6 개발 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK(10.0.10240.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK(10.0.10586.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK(10.0.14393.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK 및 UCRT SDK | 15.0.26208.0 | Optional


## <a name="mobile-development-with-c"></a>C++를 사용한 모바일 개발

**ID:** Microsoft.VisualStudio.Workload.NativeMobile

**설명:** C++를 사용하여 iOS, Android 또는 Windows용 플랫폼 간 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | 필수
Component.Android.NDK.R13B | Android NDK(R13B) | 13.1.6 | 권장
Component.Android.SDK19 | Android SDK 설치(API 수준 19 및 21) | 15.0.26208.0 | 권장
Component.Android.SDK22 | Android SDK 설치(API 수준 22) | 15.0.26208.0 | 권장
Component.Ant | Apache Ant(1.9.3) | 1.9.3.7 | 권장
Component.MDD.Android | C++ Android 개발 도구 | 15.0.26208.0 | 권장
Component.Android.NDK.R11C | Android NDK(R11C) | 11.3.13 | Optional
Component.Android.NDK.R11C_3264 | Android NDK(R11C)(32비트) | 11.3.14 | Optional
Component.Android.NDK.R12B | Android NDK(R12B) | 12.1.9 | Optional
Component.Android.NDK.R12B_3264 | Android NDK(R12B)(32비트) | 12.1.9 | Optional
Component.Android.NDK.R13B_3264 | Android NDK(R13B)(32비트) | 13.1.6 | Optional
Component.Android.SDK23 | Android SDK 설치(API 수준 23) | 15.0.26208.0 | Optional
Component.Google.Android.Emulator.API23.V2 | Google Android 에뮬레이터(API 수준 23) | 15.0.26208.0 | Optional
Component.HAXM | Intel HAXM(Hardware Accelerated Execution Manager) | 15.0.26208.0 | Optional
Component.Incredibuild | IncrediBuild | 15.0.26228.0 | Optional
Component.JavaJDK | Java SE Development Kit(8.0.1120.15) | 15.0.26403.0 | Optional
Component.MDD.IOS | C++ iOS 개발 도구 | 15.0.26208.0 | Optional


## <a name="net-core-cross-platform-development"></a>.NET Core 플랫폼 간 개발

**ID:** Microsoft.VisualStudio.Workload.NetCoreTools

**설명:** .NET Core, ASP.NET Core, HTML, JavaScript 및 CSS를 사용하여 플랫폼 간 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 필수
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 필수
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.Net.Core.Component.SDK | .NET Core 1.0.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.NetCore.ComponentGroup.Web | .NET Core 1.0 - 1.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 15.0.26419.1 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server 명령줄 유틸리티 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 필수
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 15.0.26323.1 | 권장


## <a name="mobile-development-with-net"></a>.NET을 사용한 모바일 개발

**ID:** Microsoft.VisualStudio.Workload.NetCrossPlat

**설명:** Xamarin을 사용하여 iOS, Android 또는 Windows용 플랫폼 간 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Component.Android.NDK.R13B | Android NDK(R13B) | 13.1.6 | 권장
Component.Android.SDK23 | Android SDK 설치(API 수준 23) | 15.0.26208.0 | 권장
Component.Google.Android.Emulator.API23.V2 | Google Android 에뮬레이터(API 수준 23) | 15.0.26208.0 | 권장
Component.HAXM | Intel HAXM(Hardware Accelerated Execution Manager) | 15.0.26208.0 | 권장
Component.JavaJDK | Java SE Development Kit(8.0.1120.15) | 15.0.26403.0 | 권장
Component.Xamarin | Xamarin | 15.0.26424.2 | 권장
Component.Xamarin.Inspector | Xamarin Workbooks | 15.0.26228.0 | 권장
Component.Xamarin.Profiler | Xamarin Profiler | 15.0.26228.0 | 권장
Component.Xamarin.RemotedSimulator | Xamarin 원격 시뮬레이터 | 15.0.26228.0 | 권장
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 권장
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | Optional
Microsoft.Component.NetFX.Native | .NET 네이티브 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.CodeClone | 코드 복제본 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | 코드 맵 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | 실시간 종속성 유효성 검사 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics | 이미지 및 3D 모델 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Windows 10 모바일 에뮬레이터(크리에이터 업데이트) | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | UWP용 Windows 10 SDK(10.0.15063.0): C#, VB, JS | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | 아키텍처 및 분석 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Xamarin용 유니버설 Windows 플랫폼 도구 | 15.0.26403.0 | Optional


## <a name="aspnet-and-web-development"></a>ASP.NET 및 웹 개발

**ID:** Microsoft.VisualStudio.Workload.NetWeb

**설명:** ASP.NET, ASP.NET Core, HTML, JavaScript 및 CSS를 사용하여 웹 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 필수
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 필수
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.Net.Core.Component.SDK | .NET Core 1.0.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.NetCore.ComponentGroup.Web | .NET Core 1.0 - 1.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 15.0.26419.1 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server 명령줄 유틸리티 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 필수
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.0.26208.0 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 - 4.6 개발 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.CloudExplorer | 클라우드 탐색기 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.DockerTools | 컨테이너 개발 도구 | 15.0.26323.1 | 권장
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | 권장
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.0.26419.1 | 선택적
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 15.0.26419.1 | 선택적
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.ClassDesigner | 클래스 디자이너 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | 코드 복제본 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | 코드 맵 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | 실시간 종속성 유효성 검사 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.FSharp | F# 언어 지원 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | 아키텍처 및 분석 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Web.Mvc4.ComponentGroup | ASP.NET MVC 4 | 15.0.26208.0 | Optional


## <a name="nodejs-development"></a>Node.js 개발

**ID:** Microsoft.VisualStudio.Workload.Node

**설명:** 비동기 이벤트 구동 JavaScript 런타임인 Node.js를 사용하여 확장 가능한 네트워크 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 필수
Microsoft.VisualStudio.Component.Node.Tools | Node.js 지원 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 필수
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 권장
Microsoft.VisualStudio.Component.Git | Windows용 GIT | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.0.26208.0 | Optional


## <a name="officesharepoint-development"></a>Office/SharePoint 개발

**ID:** Microsoft.VisualStudio.Workload.Office

**설명:** C#, VB 및 JavaScript를 사용하여 Office 및 SharePoint 추가 기능, SharePoint 솔루션 및 VSTO 추가 기능을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 필수
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 필수
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 필수
Microsoft.VisualStudio.Component.Debugger.JustInTime | Just-In-Time 디버거 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 15.0.26419.1 | 필수
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET 데스크톱 개발 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Sharepoint.Tools | Visual Studio용 Office 개발자 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server 명령줄 유틸리티 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 필수
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Workflow | Windows Workflow Foundation | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TeamOffice | VSTO(Visual Studio Tools for Office) | 15.0.26228.0 | 권장
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | 선택적


## <a name="python-development"></a>Python 개발

**ID:** Microsoft.VisualStudio.Workload.Python

**설명:** Python에 대한 편집, 디버깅, 대화형 개발 및 소스 제어입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.CPython3.x64 | Python 3 64비트(3.6.0) | 3.6.0 | 권장
Microsoft.Component.CookiecutterTools | Cookiecutter 템플릿 지원 | 15.0.26419.1 | 권장
Microsoft.Component.PythonTools | Python 언어 지원 | 15.0.26419.1 | 권장
Microsoft.Component.PythonTools.Web | Python 웹 지원 | 15.0.26419.1 | 권장
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Common.Azure.Tools | 연결 및 게시 도구 | 1.9.170119.3 | 권장
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.WebDeploy | 웹 배포 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.0.26208.0 | 권장
Component.Anaconda2.x64 | Anaconda2 64비트(4.3.0.1) | 4.3.0.2 | 선택적
Component.Anaconda2.x86 | Anaconda2 32비트(4.3.0.1) | 4.3.0.2 | 선택적
Component.Anaconda3.x64 | Anaconda3 64비트(4.3.0.1) | 4.3.0.2 | 선택적
Component.Anaconda3.x86 | Anaconda3 32비트(4.3.0.1) | 4.3.0.2 | 선택적
Component.CPython2.x64 | Python 2 64비트(2.7.13) | 2.7.13 | 선택적
Component.CPython2.x86 | Python 2 32비트(2.7.13) | 2.7.13 | 선택적
Component.CPython3.x86 | Python 3 32비트(3.6.0) | 3.6.0.1 | 선택적
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 선택적
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | Optional
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Optional
Microsoft.Component.NetFX.Native | .NET 네이티브 | 15.0.26208.0 | 선택적
Microsoft.Component.PythonTools.UWP | Python IoT 지원 | 15.0.26419.1 | 선택적
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python 네이티브 개발 도구 | 15.0.26419.1 | 선택적
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | Optional
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 - 4.6 개발 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | 선택적
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure 작성 도구 | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET용 Azure 라이브러리 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure 계산 에뮬레이터 | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure Storage 계정 | 15.0.26424.2 | 선택적
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services 핵심 도구 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.ClassDesigner | 클래스 디자이너 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | 코드 복제본 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | 코드 맵 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio 핵심 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics | 이미지 및 3D 모델 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Win81 | 그래픽 도구 Windows 8.1 SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 선택적
Microsoft.VisualStudio.Component.ManagedDesktop.Core | 관리되는 데스크톱 워크로드 핵심 | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL 런타임 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server 명령줄 유틸리티 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.SQL.DataSources | SQL Server 지원용 데이터 원본 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Data Tools | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 선택적
Microsoft.VisualStudio.Component.VC.140 | VC++ 2015.3 v140 도구 집합(x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ 프로파일링 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.0.26208.0 | 선택적
Microsoft.VisualStudio.Component.Web | ASP.NET 및 웹 개발 도구 | 15.0.26323.1 | 선택적
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK(10.0.10586.0) | 15.0.26208.0 | Optional


## <a name="universal-windows-platform-development"></a>유니버설 Windows 플랫폼 개발

**ID:** Microsoft.VisualStudio.Workload.Universal

**설명:** C#, VB, JavaScript 또는 선택적으로 C++를 사용하여 유니버설 Windows 플랫폼용 응용 프로그램을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 필수
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 필수
Microsoft.Component.NetFX.Native | .NET 네이티브 | 15.0.26208.0 | 필수
Microsoft.ComponentGroup.Blend | Blend for Visual Studio | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Graphics | 이미지 및 3D 모델 편집기 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 필수
Microsoft.VisualStudio.Component.UWP.Support | 유니버설 Windows 플랫폼 도구 | 15.0.26412.1 | 필수
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | UWP용 Windows 10 SDK(10.0.15063.0): C#, VB, JS | 15.0.26419.1 | 필수
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Cordova용 유니버설 Windows 플랫폼 도구 | 15.0.26403.0 | 필수
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Xamarin용 유니버설 Windows 플랫폼 도구 | 15.0.26403.0 | 필수
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | 권장
Microsoft.Component.VC.Runtime.OSSupport | UWP용 Visual C++ 런타임 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeClone | 코드 복제본 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.CodeMap | 코드 맵 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | 실시간 종속성 유효성 검사 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX용 그래픽 디버거 및 GPU 프로파일러 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics.Win81 | 그래픽 도구 Windows 8.1 SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Windows 10 모바일 에뮬레이터(크리에이터 업데이트) | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM | ARM용 Visual C++ 컴파일러 및 라이브러리 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK(10.0.10240.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK(10.0.10586.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK(10.0.14393.0) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | UWP용 Windows 10 SDK(10.0.15063.0): C++ | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | 아키텍처 및 분석 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.ComponentGroup.UWP.VC | C++ 유니버설 Windows 플랫폼 도구 | 15.0.26403.0 | Optional


## <a name="visual-studio-extension-development"></a>Visual Studio 확장 개발

**ID:** Microsoft.VisualStudio.Workload.VisualStudioExtension

**설명:** 새로운 명령, 코드 분석기 및 도구 창을 포함하여 Visual Studio용 추가 기능 및 확장 기능을 만듭니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.0.26208.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.NuGet | NuGet 패키지 관리자 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.PortableLibrary | .NET 이식이 가능한 라이브러리 타기팅 팩 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.ComponentGroup.VisualStudioExtension.Prerequisites | Visual Studio 확장 개발 필수 구성 요소 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.CodeClone | 코드 복제본 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.CodeMap | 코드 맵 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | 실시간 종속성 유효성 검사 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.GraphDocument | DGML 편집기 | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.0.26208.0 | 권장
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server Native Client | 15.0.26208.0 | 권장
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | 아키텍처 및 분석 도구 | 15.0.26208.0 | 권장
Component.Dotfuscator | PreEmptive Protection - Dotfuscator | 15.0.26208.0 | Optional
Microsoft.Component.MSBuild | MSBuild | 15.0.26208.0 | Optional
Microsoft.Component.VC.Runtime.OSSupport | UWP용 Visual C++ 런타임 | 15.0.26208.0 | Optional
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.ClassDesigner | 클래스 디자이너 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.DslTools | Modeling SDK | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# 및 Visual Basic | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.TextTemplating | 텍스트 템플릿 변환 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL 지원 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | MFC 및 ATL 지원(x86 및 x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ 핵심 기능 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VSSDK | Visual Studio SDK | 15.0.26208.0 | Optional


## <a name="mobile-development-with-javascript"></a>JavaScript를 사용한 모바일 개발

**ID:** Microsoft.VisualStudio.Workload.WebCrossPlat

**설명:** Apache Cordova용 도구를 사용하여 Android, iOS 및 UWP 앱을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Component.CordovaToolset.6.3.1 | Cordova 6.3.1 도구 집합 | 15.0.26323.1 | 필수
Component.WebSocket | WebSocket4Net | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.Cordova | JavaScript 핵심 기능을 사용한 모바일 개발 | 15.0.26323.1 | 필수
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript 진단 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.JavaScript.TypeScript | TypeScript 및 JavaScript 언어 지원 | 15.0.26412.1 | 필수
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.0.26430.1 | 필수
Component.Android.SDK23 | Android SDK 설치(API 수준 23) | 15.0.26208.0 | Optional
Component.Google.Android.Emulator.API23.V2 | Google Android 에뮬레이터(API 수준 23) | 15.0.26208.0 | Optional
Component.HAXM | Intel HAXM(Hardware Accelerated Execution Manager) | 15.0.26208.0 | Optional
Component.JavaJDK | Java SE Development Kit(8.0.1120.15) | 15.0.26403.0 | Optional
Microsoft.Component.ClickOnce | ClickOnce 게시 도구 | 15.0.26208.0 | Optional
Microsoft.Component.NetFX.Native | .NET 네이티브 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.AppInsights.Tools | 개발자 분석 도구 | 15.0.26323.1 | Optional
Microsoft.VisualStudio.Component.DiagnosticTools | 프로파일링 도구 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Git | Windows용 GIT | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Graphics | 이미지 및 3D 모델 편집기 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Windows 10 모바일 에뮬레이터(크리에이터 업데이트) | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server용 CLR 데이터 형식 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.VisualStudioData | 데이터 원본 및 서비스 참조 | 15.0.26208.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | UWP용 Windows 10 SDK(10.0.15063.0): C#, VB, JS | 15.0.26419.1 | 선택적
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Cordova용 유니버설 Windows 플랫폼 도구 | 15.0.26403.0 | Optional
## <a name="unaffiliated-components"></a>독립적 구성 요소

이러한 구성 요소는 작업에 포함되지 않지만 개별 구성 요소로 선택할 수 있습니다.

구성 요소 ID | 이름 | 버전
--- | --- | ---
Component.Android.Emulator | Android용 Visual Studio 에뮬레이터 | 15.0.26430.1
Component.GitHub.VisualStudio | Visual Studio용 GitHub 확장 | 2.2.0.10
Microsoft.Component.Blend.SDK.WPF | .NET용 Blend for Visual Studio SDK | 15.0.26208.0
Microsoft.Component.HelpViewer | 도움말 뷰어 | 15.0.26208.0
Microsoft.Net.Component.3.5.DeveloperTools | .NET Framework 3.5 개발 도구 | 15.0.26208.0
Microsoft.VisualStudio.Component.DependencyValidation.Community | 종속성 유효성 검사 | 15.0.26208.0
Microsoft.VisualStudio.Component.LinqToSql | LINQ to SQL 도구 | 15.0.26208.0
Microsoft.VisualStudio.Component.Phone.Emulator | Windows 10 모바일 에뮬레이터(Anniversary Edition) | 15.0.26208.0
Microsoft.VisualStudio.Component.TestTools.Core | 테스트 도구 핵심 기능 | 15.0.26208.0
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK | 15.0.26208.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK | 15.0.26208.0

## <a name="see-also"></a>참고 항목

* [Visual Studio 작업 및 구성 요소 ID](workload-and-component-ids.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
  * [명령줄 매개 변수 예](command-line-parameter-examples.md)
* [Visual Studio의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)


---
title: Visual Studio Build Tools 2017 워크로드 및 구성 요소 ID
description: Visual Studio 작업 및 구성 요소 ID를 사용하여 기존 Windows 기반 응용 프로그램을 빌드합니다.
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 03/05/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: b99298df-0280-47fc-af73-44cd7a8ac553
ms.workload:
- multiple
ms.openlocfilehash: 677e0b9ea2bd809307e2fd59569f3109f62f0c4a
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="visual-studio-build-tools-2017-component-directory"></a>Visual Studio Build Tools 2017 구성 요소 디렉터리

이 페이지의 표에는 명령줄을 사용하여 Visual Studio를 설치하는 데 사용할 수 있는 ID가 나열되어 있습니다. Visual Studio에 대한 업데이트를 릴리스할 때 추가 구성 요소가 추가될 것입니다.

또한 이 페이지에 대해 다음 사항에 유의하세요.

* 각 작업에는 고유한 섹션 및 작업 ID와 해당 작업에 사용할 수 있는 구성 요소 표가 있습니다.
* 기본적으로 **필수** 구성 요소는 작업을 설치할 때 설치됩니다. 원하는 경우 **권장** 및 **선택적** 구성 요소를 설치할 수도 있습니다.
* 작업과 관련이 없는 추가 구성 요소를 나열하는 섹션도 추가했습니다.

이러한 ID를 사용하는 방법에 대한 자세한 내용은 [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md) 페이지를 참조하세요. 다른 제품의 작업 및 구성 요소 ID 목록은 [Visual Studio 2017 작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요.

## <a name="msbuild-tools"></a>MSBuild 도구

**ID:** Microsoft.VisualStudio.Workload.MSBuildTools

**설명:** MSBuild 기반 응용 프로그램을 빌드하는 데 필요한 도구를 제공합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.6.27309.0 | 필수
Microsoft.VisualStudio.Component.CoreBuildTools | Visual Studio Build Tools 핵심 | 15.6.27309.0 | 필수
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# 및 Visual Basic Roslyn 컴파일러 | 15.6.27309.0 | 필수
Microsoft.VisualStudio.Component.FSharp.MSBuild | F# 컴파일러 | 15.6.27406.0 | Optional

## <a name="net-core-build-tools"></a>.NET Core 빌드 도구

**ID:** Microsoft.VisualStudio.Workload.NetCoreBuildTools

**설명:** .NET Core 응용 프로그램을 빌드하기 위한 도구입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Net.Core.Component.SDK | .NET Core 2.0 개발 도구 | 15.6.27406.0 | 필수
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 대상 및 빌드 작업 | 15.0.26919.1 | 필수
Microsoft.Net.Core.Component.SDK.1x | .NET Core 1.0 - 1.1 개발 도구 | 15.6.27406.0 | Optional

## <a name="nodejs-build-tools"></a>Node.js 빌드 도구

**ID:** Microsoft.VisualStudio.Workload.NodeBuildTools

**설명:** 비동기 이벤트 구동 JavaScript 런타임인 Node.js를 사용하여 확장 가능한 네트워크 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Node.Build | Node.js 지원 | 15.6.27406.0 | 필수

## <a name="visual-c-build-tools"></a>Visual C++ 빌드 도구

**ID:** Microsoft.VisualStudio.Workload.VCTools

**설명:** Microsoft C++ 도구 집합, ATL 또는 MFC를 사용하여 Windows 데스크톱 응용 프로그램을 빌드합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Static.Analysis.Tools | 정적 분석 도구 | 15.0.26208.0 | 필수
Microsoft.VisualStudio.Component.VC.CoreBuildTools | Visual C++ Build Tools 핵심 기능 | 15.6.27406.0 | 필수
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 재배포 가능 업데이트 | 15.6.27406.0 | 필수
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC++ 2017 v141 도구 집합(x86, x64) | 15.6.27406.0 | 필수
Microsoft.VisualStudio.Component.Windows10SDK | Windows 유니버설 C 런타임 | 15.6.27406.0 | 필수
Microsoft.VisualStudio.Component.VC.CMake.Project | CMake용 Visual C++ 도구 | 15.6.27406.0 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | 데스크톱 C++용 [x86 및 x64] Windows 10 SDK(10.0.16299.0) | 15.6.27406.0 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | UWP용 Windows 10 SDK(10.0.16299.0): C#, VB, JS | 15.6.27406.0 | 권장
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | UWP용 Windows 10 SDK(10.0.16299.0): C++ | 15.6.27406.0 | 권장
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET 및 웹 개발 | 15.0.27005.2 | 권장
Microsoft.Component.VC.Runtime.UCRTSDK | Windows 유니버설 CRT SDK | 15.6.27309.0 | Optional
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.140 | 데스크톱용 VC++ 2015.3 v140 도구 집합(x86, x64) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.ATL | Visual C++ ATL 지원 | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.ATLMFC | MFC 및 ATL 지원(x86 및 x64) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2(실험적) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.CLI.Support | C++/CLI 지원 | 15.6.27309.0 | Optional
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | 표준 라이브러리용 모듈(실험적) | 15.6.27309.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM | ARM용 Visual C++ 컴파일러 및 라이브러리 | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | ARM64용 Visual C++ 컴파일러 및 라이브러리 | 15.6.27309.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK(10.0.10240.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK(10.0.10586.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK(10.0.14393.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | 데스크톱 C++용 [x86 및 x64] Windows 10 SDK(10.0.15063.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | UWP용 Windows 10 SDK(10.0.15063.0): C#, VB, JS | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | UWP용 Windows 10 SDK(10.0.15063.0): C++ | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | 데스크톱 C++용 [ARM 및 ARM64] Windows 10 SDK(10.0.16299.0) | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | Optional
Microsoft.VisualStudio.Component.WinXP | C++용 Windows XP 지원 | 15.6.27406.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK 및 UCRT SDK | 15.6.27406.0 | Optional
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | C++용 Windows XP 지원 | 15.6.27406.0 | Optional

## <a name="web-development-build-tools"></a>웹 개발 빌드 도구

**ID:** Microsoft.VisualStudio.Workload.WebBuildTools

**설명:** 웹 응용 프로그램을 빌드하기 위한 MSBuild 작업 및 대상입니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | name | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.Net.Component.4.6.1.SDK | .NET Framework 4.6.1 SDK | 15.6.27406.0 | 필수
Microsoft.Net.Component.4.6.1.TargetingPack | .NET Framework 4.6.1 타기팅 팩 | 15.6.27406.0 | 필수
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET Framework 4.6.1 개발 도구 | 15.6.27406.0 | 필수
Microsoft.VisualStudio.Wcf.BuildTools.ComponentGroup | WCF 개발 빌드 도구 | 15.6.27309.0 | 필수
Microsoft.VisualStudio.Web.BuildTools.ComponentGroup | 웹 개발 빌드 도구 | 15.6.27406.0 | 필수
Microsoft.Net.Component.4.5.1.TargetingPack | .NET Framework 4.5.1 타기팅 팩 | 15.6.27406.0 | 권장
Microsoft.Net.Component.4.5.2.TargetingPack | .NET Framework 4.5.2 타기팅 팩 | 15.6.27406.0 | 권장
Microsoft.Net.Component.4.5.TargetingPack | .NET Framework 4.5 타기팅 팩 | 15.6.27406.0 | 권장
Microsoft.Net.Component.4.6.TargetingPack | .NET Framework 4.6 타기팅 팩 | 15.6.27406.0 | 권장
Microsoft.Net.Component.4.TargetingPack | .NET Framework 4 타기팅 팩 | 15.6.27406.0 | 권장
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET Framework 4 – 4.6 개발 도구 | 15.6.27406.0 | 권장
Microsoft.Net.Core.Component.SDK | .NET Core 2.0 개발 도구 | 15.6.27406.0 | 권장
Microsoft.VisualStudio.Component.AspNet45 | 고급 ASP.NET 기능 | 15.6.27428.1 | 권장
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet 대상 및 빌드 작업 | 15.0.26919.1 | 권장
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK | 15.0.27406.0 | 권장
Microsoft.Net.Component.3.5.DeveloperTools | .NET Framework 3.5 개발 도구 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.SDK | .NET Framework 4.6.2 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.6.2.TargetingPack | .NET Framework 4.6.2 타기팅 팩 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.SDK | .NET Framework 4.7.1 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.1.TargetingPack | .NET Framework 4.7.1 타기팅 팩 | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.SDK | .NET Framework 4.7 SDK | 15.6.27406.0 | Optional
Microsoft.Net.Component.4.7.TargetingPack | .NET Framework 4.7 타기팅 팩 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET Framework 4.6.2 개발 도구 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET Framework 4.7.1 개발 도구 | 15.6.27406.0 | Optional
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET Framework 4.7 개발 도구 | 15.6.27406.0 | Optional

## <a name="unaffiliated-components"></a>독립적 구성 요소

이러한 구성 요소는 작업에 포함되지 않지만 개별 구성 요소로 선택할 수 있습니다.

구성 요소 ID | name | 버전
--- | --- | ---
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.3 | TypeScript 2.3 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.5 | TypeScript 2.5 SDK | 15.6.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.11 | VC++ 2017 버전 15.4 v14.11 도구 집합 | 15.0.27406.0
Microsoft.VisualStudio.Component.VC.Tools.14.12 | VC++ 2017 버전 15.5 v14.12 도구 집합 | 15.0.27406.0

## <a name="get-support"></a>지원 받기

때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.

* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고, 답변을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다. (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목

* [Visual Studio 작업 및 구성 요소 ID](workload-and-component-ids.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
  * [명령줄 매개 변수 예](command-line-parameter-examples.md)
* [Visual Studio의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)

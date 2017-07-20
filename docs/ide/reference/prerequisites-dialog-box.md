---
title: "필수 조건 대화 상자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.BaseProvider.Dialog.Bootstrapper
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Prerequisites dialog box
ms.assetid: 53ac863c-77a0-409b-91e5-7a4bd8b8474e
caps.latest.revision: 75
author: kempb
ms.author: kempb
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 8bf0b097be929b30627e0f1139c6e0b145933ab4
ms.openlocfilehash: 5a8237e5c437878b22bd3c67a3a4ba2cdc3fa126
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# Prerequisites Dialog Box
<a id="prerequisites-dialog-box" class="xliff"></a>
이 대화 상자에서는 설치할 필수 구성 요소, 설치 방법 및 패키지 설치 순서를 지정합니다.  
  
 이 대화 상자에 액세스하려면 **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 **프로젝트** 메뉴에서 **속성**을 클릭합니다. **프로젝트 디자이너** 가 나타나면 **게시** 탭을 클릭합니다. **게시** 페이지에서 **필수 구성 요소**를 클릭합니다. 설치 프로젝트인 경우 **프로젝트** 메뉴에서 **속성**을 클릭합니다. **속성 페이지** 대화 상자가 표시되면 **필수 구성 요소**를 클릭합니다.  
  
## UI 요소 목록
<a id="uielement-list" class="xliff"></a>  
  
|요소|설명|  
|-------------|-----------------|  
|**필수 구성 요소를 설치하기 위한 설치 프로그램 만들기**|종속성 순서에 따라 응용 프로그램보다 필수 구성 요소가 먼저 설치되도록 응용 프로그램의 설치 프로그램(Setup.exe)에 필수 구성 요소를 포함합니다. 기본적으로 이 옵션이 선택됩니다. 이 옵션을 선택하지 않으면 Setup.exe가 작성되지 않습니다.|  
|**설치할 필수 구성 요소 선택**|[!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)], Crystal Reports 등의 구성 요소를 설치할지 여부를 지정합니다.<br /><br /> 예를 들어, **SQL Server 2005 Express Edition SP2** 옆의 확인란을 선택하여 설치 프로그램에서 이 구성 요소가 대상 컴퓨터에 설치되었는지 여부를 확인하고 아직 설치되지 않았으면 설치하도록 지정할 수 있습니다.<br /><br /> 각 필수 구성 요소 패키지에 대한 자세한 내용은 이 항목의 뒷부분에서 필수 구성 요소 정보 표를 참조하십시오.|  
|**Microsoft Update에서 더 많은 재배포 가능 구성 요소 확인**|이 링크를 클릭하면 업데이트를 확인할 수 있는 [Bootstrapper Packages to Redistribute Components](http://go.microsoft.com/fwlink/?LinkId=208835)(구성 요소 재배포를 위한 부트스트래퍼 패키지) 웹 사이트로 이동합니다.|  
|**구성 요소 공급업체의 웹 사이트에서 필수 구성 요소 다운로드**|공급업체의 웹 사이트에서 필수 구성 요소를 설치하도록 지정합니다. 기본 옵션입니다.|  
|**내 응용 프로그램과 동일한 위치에서 필수 구성 요소 다운로드**|응용 프로그램과 동일한 위치에서 필수 구성 요소가 설치되도록 지정합니다. 이 옵션은 모든 필수 구성 요소 패키지를 게시 위치에 복사합니다. 이 옵션이 작동하려면 필수 구성 요소 패키지가 개발 컴퓨터에 있어야 합니다.|  
|**다음 위치에서 필수 구성 요소 다운로드**|선택한 위치에서 필수 구성 요소가 설치되도록 지정합니다. **찾아보기** 단추를 사용하여 위치를 선택할 수 있습니다.|  
  
## 필수 구성 요소 정보
<a id="prerequisites-information" class="xliff"></a>  
 **필수 구성 요소** 대화 상자에 나타나는 필수 구성 요소는 다음 목록에 나와 있는 구성 요소와 다를 수도 있습니다. 대화 상자를 처음 열면 **필수 조건 대화 상자**에 나열된 필수 조건 패키지가 자동으로 설정됩니다. 이후에 프로젝트의 대상 프레임워크를 변경하는 경우에는 새 대상 프레임워크에 맞도록 필수 구성 요소를 수동으로 선택해야 합니다.  
  
|요소|설명|  
|-------------|-----------------|  
|**.NET Framework 3.5 SP1**|이 패키지는 다음 항목을 설치합니다.<br /><br /> -   .NET Framework 버전 2.0, 3.0 및 3.5.<br />-   32비트(x86) 및 64비트(x64) 운영 체제에서 모든 .NET Framework 버전에 대한 지원.<br />-   패키지와 함께 설치된 각 .NET Framework 버전에 대한 언어 팩.<br />-   .NET Framework 2.0 및 3.0용 서비스 팩.<br /><br /> .NET Framework 3.0은 Windows Vista에 포함되고 .NET Framework 3.5는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에 포함됩니다. .NET Framework 3.5는 32비트 운영 체제용으로 컴파일되고 대상 프레임워크가 **.NET Framework 3.5**로 설정된 모든 Visual Basic 및 Visual C# 프로젝트와 64비트 운영 체제용으로 컴파일된 Visual Basic 및 Visual C# 프로젝트에 필요합니다. IA64는 지원되지 않습니다. Visual Basic 및 Visual C# 프로젝트는 기본적으로 모든 CPU 아키텍처에 대해 컴파일됩니다. 자세한 내용은 [Visual Studio 멀티 타기팅 개요](../../ide/visual-studio-multi-targeting-overview.md), [.NET Framework 재배포](http://msdn.microsoft.com/en-us/a18d0456-fd89-493e-97f4-756505bfe287) 및 [64비트 응용 프로그램의 필수 구성 요소 배포](../../deployment/deploying-prerequisites-for-64-bit-applications.md)를 참조하세요.<br /><br /> 이 항목은 기본적으로 선택됩니다.|  
|**.NET Framework 3.5 SP1 Client Profile**|.NET Framework 4 Client Profile은 전체 .NET Framework 3.5 SP1에서 클라이언트 응용 프로그램을 대상으로 하는 하위 집합입니다. WPF(Windows Presentation Foundation), Windows Forms, WCF(Windows Communication Foundation) 및 ClickOnce 기능의 효율적인 하위 집합이 제공됩니다. 이를 통해 .NET Framework 4 Client Profile을 대상으로 하는 WPF, Windows Forms, WCF 및 콘솔 응용 프로그램을 빠르게 배포할 수 있습니다. 자세한 내용은 [.NET Framework Client Profile](/dotnet/framework/deployment/client-profile)을 참조하세요.|  
|**Microsoft .NET Framework 4(x86 및 x64)**|이 패키지는 x86 및 x64 플랫폼 모두에 .NET Framework 4를 설치합니다.<br /><br /> 자세한 내용은 [Visual Studio 멀티 타기팅 개요](../../ide/visual-studio-multi-targeting-overview.md), [.NET Framework 재배포](http://msdn.microsoft.com/en-us/a18d0456-fd89-493e-97f4-756505bfe287) 및 [64비트 응용 프로그램의 필수 구성 요소 배포](../../deployment/deploying-prerequisites-for-64-bit-applications.md)를 참조하세요.<br /><br /> 이 항목은 기본적으로 선택됩니다.|  
|**Microsoft .NET Framework 4 Client Profile(x86 및 x64)**|.NET Framework 4 Client Profile은 전체 .NET Framework 4에서 클라이언트 응용 프로그램을 대상으로 하는 하위 집합입니다. WPF(Windows Presentation Foundation), Windows Forms, WCF(Windows Communication Foundation) 및 ClickOnce 기능의 효율적인 하위 집합이 제공됩니다. 이를 통해 .NET Framework 4 Client Profile을 대상으로 하는 WPF, Windows Forms 및 콘솔 응용 프로그램을 빠르게 배포할 수 있습니다. 자세한 내용은 [.NET Framework Client Profile](/dotnet/framework/deployment/client-profile)을 참조하세요.|  
|**Microsoft Office 2007 주 Interop 어셈블리**|이 패키지는 2007 Microsoft Office 제품에 주 Interop 어셈블리를 설치합니다. 주 Interop 어셈블리를 사용하면 관리 코드가 Microsoft Office 응용 프로그램의 COM 기반 개체 모델과 상호 작용할 수 있습니다. 자세한 내용은 [Office 주 Interop 어셈블리](/office-dev/office-dev/office-primary-interop-assemblies)를 참조하세요.|  
|**Microsoft Visual Basic PowerPacks 버전 10.0**|PowerPacks는 Visual Basic 응용 프로그램을 개발하는 데 도움이 되는 추가 기능, 컨트롤, 구성 요소 및 도구의 모음입니다. 이 버전에는 Windows Form의 내용을 인쇄하는 데 사용할 수 있는 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 구성 요소와 Visual Basic 6.0 Printer 코드를 수정하지 않고 실행하는 데 사용할 수 있는 프린터 호환성 라이브러리가 포함되어 있습니다.|  
|**Microsoft Visual F# Runtime for .NET 2.0**|이 패키지는 기존의 개체 지향 및 명령적 방식(절차적) 프로그래밍과 함수형 프로그래밍에 대한 지원을 모두 제공하는 x86 및 x64 운영 체제용 Visual F# 런타임 라이브러리를 설치합니다. 응용 프로그램 또는 구성 요소가 Visual F# 및 .NET Framework 2.0, .NET Framework 3.0 또는 .NET Framework 3.5에서 작성된 경우 이 패키지를 설치해야 합니다.<br /><br /> 자세한 내용은 [F# Language Reference](http://msdn.microsoft.com/Library/16b706f8-b5f2-4ff7-b2c1-64df33cd6adf)(F# 언어 참조)를 참조하세요.|  
|**Microsoft Visual F# Runtime for .NET 4.0**|이 패키지는 기존의 개체 지향 및 명령적 방식(절차적) 프로그래밍과 함수형 프로그래밍에 대한 지원을 모두 제공하는 x86 및 x64 운영 체제용 Visual F# 런타임 라이브러리를 설치합니다. 응용 프로그램 또는 구성 요소가 Visual F# 및 .NET Framework 4에서 작성된 경우 이 패키지를 설치해야 합니다.<br /><br /> 자세한 내용은 [F# Language Reference](http://msdn.microsoft.com/Library/16b706f8-b5f2-4ff7-b2c1-64df33cd6adf)(F# 언어 참조)를 참조하세요.|  
|**Microsoft Visual Studio 2010 보고서 뷰어**|이 패키지는 Windows Forms 및 ASP.NET 응용 프로그램에 다양한 데이터 보고 기능을 추가하는 데 사용할 수 있는 보고서 뷰어 컨트롤을 설치합니다.|  
|**Microsoft Visual Studio 2010 for Office Runtime(x86 및 x64)**|Visual Studio의 Office 개발자 도구는 Microsoft Office를 사용하여 사용자 지정 비즈니스 솔루션을 편리하게 개발할 수 있는 통합된 도구를 제공합니다. Office 응용 프로그램을 사용자 인터페이스로 사용하는 관리되는 스마트 클라이언트 솔루션을 만들 수 있습니다. 이 도구를 사용하면 쉽게 배포하고 유지 관리할 수 있는 보안 솔루션을 개발할 수 있습니다.<br /><br /> 자세한 내용은 [방법: ClickOnce를 사용하여 Office 솔루션 게시](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8)를 참조하세요.|  
|**SQL Server 2005 Express Edition SP2(x86)**|이 패키지는 [!INCLUDE[sqprsqext](../../ide/reference/includes/sqprsqext_md.md)]를 기반으로 하는 데이터베이스 응용 프로그램인 Microsoft SQL Server 2005 Express Edition SP2를 설치합니다. SQL Server Express는 MSDE(Microsoft SQL Server Desktop Engine)를 대체합니다. SQL Server Express는 무료이고 계약 내용에 따라 재배포할 수 있으며, 클라이언트 데이터베이스와 기본 서버 데이터베이스의 역할을 모두 수행합니다. 다음과 같은 차이점을 제외하면 SQL Server 2005와 같습니다.<br /><br /> -   엔터프라이즈 기능이 지원되지 않습니다.<br />-   하나의 CPU로 제한됩니다.<br />-   버퍼 풀의 메모리는 1GB로 제한됩니다.<br />-   데이터베이스의 최대 크기는 4GB입니다.|  
|**SQL Server 2008 Express**|이 패키지는 소규모 웹, 서버 또는 데스크톱 응용 프로그램에 적합한 데이터베이스이며 Microsoft SQL Server 2008의 무료 버전인 Microsoft SQL Server 2008 Express를 설치합니다. 이 응용 프로그램은 개발 및 프로덕션 용도로 무료로 사용할 수 있습니다. 응용 프로그램과 함께 SQL Server 2008 Express를 배포하려면 무료 [등록](http://go.microsoft.com/fwlink/?LinkId=130380)이 필요합니다.<br /><br /> 부트스트래퍼의 동작은 다음과 같습니다.<br /><br /> -   컴퓨터에 이미 SQL Server 2008 Express 이상이 있으면 해당 컴퓨터는 SQL Server 2008 Express 이상으로 유지됩니다.<br />-   컴퓨터에 이미 SQL Server 2008 Express 이상의 버전이 없으면 패키지가 SQL Server 2008 Express SP1의 최신 버전을 설치합니다.<br /><br /> SQL Server 2008 Express에 대한 자세한 내용은 [http://go.microsoft.com/fwlink/?LinkId=183586](http://go.microsoft.com/fwlink/?LinkId=183586)을 방문하세요.|  
|**Visual C++ 2010 런타임 라이브러리(IA64)**|이 패키지는 Microsoft Windows 운영 체제에 프로그래밍 루틴을 제공하는 Itanium 아키텍처용 Visual C++ 런타임 라이브러리를 설치합니다. 이러한 루틴은 C 및 C++ 언어에서 제공하지 않는 여러 일반 프로그래밍 작업을 자동화합니다.<br /><br /> 자세한 내용은 [C 런타임 라이브러리 참조](/cpp/c-runtime-library/c-run-time-library-reference)를 참조하세요.|  
|**Visual C++ 2010 런타임 라이브러리(x64)**|이 패키지는 Microsoft Windows 운영 체제에 프로그래밍 루틴을 제공하는 x64 운영 체제용 Visual C++ 런타임 라이브러리를 설치합니다. 이러한 루틴은 C 및 C++ 언어에서 제공하지 않는 여러 일반 프로그래밍 작업을 자동화합니다.<br /><br /> 자세한 내용은 [C 런타임 라이브러리 참조](/cpp/c-runtime-library/c-run-time-library-reference)를 참조하세요.|  
|**Visual C++ 2010 런타임 라이브러리(x86)**|이 패키지는 Microsoft Windows 운영 체제에 프로그래밍 루틴을 제공하는 x86 운영 체제용 Visual C++ 런타임 라이브러리를 설치합니다. 이러한 루틴은 C 및 C++ 언어에서 제공하지 않는 여러 일반 프로그래밍 작업을 자동화합니다.<br /><br /> 자세한 내용은 [C 런타임 라이브러리 참조](/cpp/c-runtime-library/c-run-time-library-reference)를 참조하세요.|  
|**Windows Installer 3.1**|이 패키지는 Windows Installer 설치 프로젝트를 설치할 수 있는 Microsoft Windows Installer 재배포 가능 패키지, 버전 3.1을 설치합니다. Windows Server 2003 SP1 이상에는 이 패키지가 미리 설치되어 있습니다.<br /><br /> 이 항목은 기본적으로 선택됩니다.|  
|**Windows Installer 4.5**|이 패키지는 Windows Installer 설치 프로젝트를 설치할 수 있는 Microsoft Windows Installer 재배포 가능 패키지, 버전 4.5를 설치합니다.|  
  
## 참고 항목
<a id="see-also" class="xliff"></a>  
 [프로젝트 디자이너, 게시 페이지](../../ide/reference/publish-page-project-designer.md)   
 [응용 프로그램 배포 필수 구성 요소](../../deployment/application-deployment-prerequisites.md)   
 [.NET Framework 재배포](http://msdn.microsoft.com/en-us/a18d0456-fd89-493e-97f4-756505bfe287)   
 [64비트 응용 프로그램의 필수 구성 요소 배포](../../deployment/deploying-prerequisites-for-64-bit-applications.md)   
 [Visual Studio 멀티 타기팅 개요](../../ide/visual-studio-multi-targeting-overview.md)

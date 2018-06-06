---
title: Visual Studio Tools for Office 런타임 개요
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office runtime [Office development in Visual Studio], about Office runtime
- VSTOLoader.dll
- runtime loader [Office development in Visual Studio]
- Office runtime [Office development in Visual Studio], assemblies
- Office runtime [Office development in Visual Studio]
- runtime [Office development in Visual Studio], assemblies
- vstoee.dll
- Visual Studio Tools for Office runtime
- Office solutions [Office development in Visual Studio], runtime
- solutions [Office development in Visual Studio], runtime
- versions [Office development in Visual Studio], runtime
- assemblies [Office development in Visual Studio], runtime
- runtime [Office development in Visual Studio], about VSTO runtime
- solution loader [Office development in Visual Studio]
- runtime [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c0bb3c800aece9531d6fe90ba04b9c99a0b4bd69
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767805"
---
# <a name="visual-studio-tools-for-office-runtime-overview"></a>Visual Studio Tools for Office 런타임 개요
  Visual Studio에서 Microsoft Office 개발자 도구를 사용 하 여 만든 솔루션을를 실행 하려면 최종 사용자 컴퓨터에 Visual Studio 2010 Tools for Office 런타임을 설치 합니다. 자세한 내용은 참조 [하는 방법: Visual Studio Tools for Office 런타임 재배포 가능 설치](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)합니다. Visual Studio 2010 Tools for Office 런타임에서 두 개의 주요 구성으로 구성 됩니다.  
  
-   .NET Framework용 Office 확장. 이러한 구성 요소는 솔루션과 Microsoft Office 응용 프로그램 간의 통신 계층을 제공하는 관리되는 어셈블리입니다. 자세한 내용은 참조 [.NET Framework 용 Office 확장 이해](#officeextensions)합니다.  
  
-   Office 솔루션 로더. 이 구성 요소는 Office 응용 프로그램에서 런타임 및 솔루션을 로드하는 데 사용하는 관리되지 않는 DLL 집합입니다. 자세한 내용은 참조 [Office 솔루션 로더 이해](#UnmanagedLoader)합니다.  
  
 런타임은 여러 가지 방법으로 설치할 수 있습니다. 런타임을 설치할 때는 컴퓨터의 구성에 따라 각기 다른 런타임 구성 요소가 설치됩니다. 자세한 내용은 참조 [Visual Studio Tools for Office 런타임 설치 시나리오](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)합니다.  
  
##  <a name="officeextensions"></a> .NET Framework 용 Office 확장 이해  
 Visual Studio 2010 Tools for Office 런타임.NET Framework 3.5 용 Office 확장이 포함 되어는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상. .NET Framework의 각 버전을 대상으로 하는 솔루션은 해당 버전에 적절한 확장명을 사용합니다.  
  
 이러한 확장은 솔루션에서 Office 응용 프로그램을 자동화하고 확장하는 데 사용하는 어셈블리로 구성되어 있습니다. Office 프로젝트를 만들면 프로젝트의 프로젝트 형식 및 대상 .NET Framework에 사용되는 어셈블리에 대한 참조가 자동으로 추가됩니다. Office 확장의 어셈블리에 대 한 자세한 내용은 참조 [의 Visual Studio Tools for Office 런타임 어셈블리](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)합니다.  
  
### <a name="design-differences-in-the-office-extensions"></a>Office 확장의 디자인 차이점  
 .NET Framework 3.5용 Office 확장에서 사용하는 대부분의 형식은 클래스입니다. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 이전 버전에 포함된 같은 클래스가 있습니다. 반대로 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상용 Office 확장에서 사용하는 대부분의 형식은 인터페이스입니다. 예를 들어 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 경우 <xref:Microsoft.Office.Tools.Excel.Worksheet> 및 <xref:Microsoft.Office.Tools.Word.Document> 형식은 클래스가 아닌 인터페이스입니다.  
  
 대부분의 경우 Office 솔루션에서 작성하는 코드는 솔루션이 .NET Framework 3.5를 대상으로 하는지 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]을 대상으로 하는지 여부에 관계없이 동일합니다. 그러나 다른 버전의 .NET Framework를 대상으로 하는 경우 일부 기능에는 다른 코드가 필요합니다. 자세한 내용은 참조 [.NET Framework 4 이상으로 마이그레이션 Office 솔루션](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)합니다.  
  
### <a name="interfaces-in-the-office-extensions-for-the-net-framework-4-or-later"></a>.NET Framework 4 이상용 Office 확장의 인터페이스  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상용 Office 확장에 있는 대부분의 인터페이스는 사용자 코드에서 구현되지 않도록 되어 있습니다. 직접 구현할 수 인터페이스 문자로 시작 하는 이름을 사용할 **I**와 같은 <xref:Microsoft.Office.Tools.Excel.ISmartTagExtension>합니다.  
  
 문자로 시작 하지 않는 모든 인터페이스 **I** Visual Studio 2010 Tools for Office 런타임에서 내부적으로 구현 되 고 이러한 인터페이스는 이후 릴리스에서 변경 될 수 있습니다. 이러한 인터페이스를 구현하는 개체를 만들려면 `Globals.Factory` 개체에서 제공하는 메서드를 프로젝트에 사용합니다. 예를 들어 <xref:Microsoft.Office.Tools.Excel.SmartTag> 인터페이스를 구현하는 개체를 가져오려면 `Globals.Factory.CreateSmartTag` 메서드를 사용합니다. 에 대 한 자세한 내용은 `Globals.Factory`, 참조 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)합니다.  
  
### <a name="enable-type-equivalence-and-embedded-types-in-projects-that-target-the-net-framework-4-or-later"></a>동일 형식 및.NET Framework 4 이상을 대상으로 하는 프로젝트에 포함 된 형식 사용  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상용 Office 확장의 개체 모델이 인터페이스를 기반으로 하기 때문에 Visual Studio에서 Visual C# 및 Visual Basic 모두의 동일 형식 기능을 사용하여 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 의 형식 정보를 솔루션에 포함할 수 있습니다. 이 기능을 통해 Office 솔루션 및 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 이 서로 독립적인 버전이 됩니다. 예를 들어 솔루션에서 <xref:Microsoft.Office.Tools.Word.Document> 인터페이스를 포함된 형식으로 사용하고 런타임의 향후 버전에서 <xref:Microsoft.Office.Tools.Word.Document> 인터페이스에 멤버를 추가하는 경우 해당 솔루션은 런타임의 향후 버전에서도 계속 작동합니다. 솔루션에서 <xref:Microsoft.Office.Tools.Word.Document> 인터페이스를 포함된 형식으로 사용하지 않는 경우 해당 솔루션은 런타임의 향후 버전에서 더 이상 작동하지 않습니다.  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 Office 프로젝트를 만드는 경우 동일 형식 기능은 기본적으로 사용되지 않습니다. 이 기능이 사용되도록 설정하려면 프로젝트에서 다음 어셈블리 참조 중 하나의 **Interop 형식 포함** 속성을 **True**로 설정합니다.  
  
-   Microsoft.Office.Tools.dll  
  
-   Microsoft.Office.Tools.Common.dll  
  
-   Microsoft.Office.Tools.Excel.dll  
  
-   Microsoft.Office.Tools.Outlook.dll  
  
-   Microsoft.Office.Tools.Word.dll  
  
 이와 같이 변경하면 프로젝트를 만들 때 해당 프로젝트에서 사용되는 모든 런타임 형식에 대한 형식 정보가 솔루션 어셈블리에 포함됩니다. 참조 된 어셈블리의 형식 정보를 사용 하지 않고이 포함 된 형식 정보를 런타임에 솔루션에서 사용 됩니다.  
  
##  <a name="UnmanagedLoader"></a> Office 솔루션 로더 이해  
 Visual Studio Tools for Office Runtime에는 Office 응용 프로그램에서 런타임 및 Office 솔루션을 로드하는 데 사용하는 관리되지 않는 DLL이 몇 개 포함되어 있습니다. 이러한 DLL에 대해 사용자가 직접 작업을 수행할 필요는 없지만 해당 DLL의 용도를 알고 있으면 Office 솔루션의 아키텍처를 보다 잘 이해할 수 있습니다.  
  
 로드 프로세스 중에 이러한 구성 요소는 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md) 및 [아키텍처의 VSTO 추가 기능](../vsto/architecture-of-vsto-add-ins.md)합니다.  
  
### <a name="vstoeedll"></a>vstoee.dll  
 Office 응용 프로그램에 호출 사용자가 문서 수준 사용자 지정을 열거나 VSTO 추가 기능을 시작, *VSTOEE.dll* 로드 하는 데 필요한 작업을 수행 하는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다.  
  
 *VSTOEE.dll* 그 올바른 버전의는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 해당 솔루션과 설치 된 Office 버전에 대 한 로드 됩니다. 하지만 여러 버전의는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 의 인스턴스가 하나만 동일한 컴퓨터에 설치할 수 있습니다 *VSTOEE.dll* 한 번에 설치 합니다. 이는 *VSTOEE.dll* 하는 컴퓨터에 설치 된 런타임의 최신 버전에 포함 되어 있습니다. 다양 한 버전의에 대 한 자세한 내용은 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 참조, 다른 솔루션에 사용할 수 있는 [다른 버전의 Microsoft Office에서 솔루션을 실행](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)합니다.  
  
### <a name="vstoloaderdll"></a>VSTOLoader.dll  
 후 *VSTOEE.dll* 적절 한 버전의 로드는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], *VSTOLoader.dll* 대부분의 솔루션 어셈블리를 로드 하는 데 필요한 작업을 수행 합니다. *VSTOLoader.dll* 여러 작업을 수행 합니다.  
  
-   각 솔루션 어셈블리의 응용 프로그램 도메인을 만듭니다.  
  
-   일련의 보안 검사를 수행하여 솔루션 어셈블리에 실행 권한이 있는지 확인합니다.  
  
-   솔루션에 필요한 버전의 .NET Framework용 Office 확장을 로드합니다.  
  
 *VSTOLoader.dll* VSTO 추가 기능과 관련 된 몇 가지 작업도 수행 합니다.  
  
-   <xref:Extensibility.IDTExtensibility2> 인터페이스를 구현합니다. <xref:Extensibility.IDTExtensibility2> 는 Microsoft Office 응용 프로그램의 모든 VSTO 추가 기능에서 구현해야 하는 COM 인터페이스입니다. 이 인터페이스는 응용 프로그램에서 VSTO 추가 기능과 통신하기 위해 호출하는 메서드를 정의합니다.  
  
-   IManagedAddin 인터페이스를 구현합니다. 이 인터페이스는 Office 응용 프로그램에서 VSTO 추가 기능의 로드를 돕기 위해 사용됩니다. 자세한 내용은 참조 [IManagedAddin 인터페이스](../vsto/imanagedaddin-interface.md)합니다.  
  
## <a name="understand-the-32-bit-and-64-bit-versions-of-the-runtime"></a>런타임 32 비트 및 64 비트 버전 이해  
 Visual Studio 2010 Tools for Office 런타임의 64 비트 및 32 비트 버전이 각각 있습니다. 이러한 런타임 버전은 64비트 및 32비트 버전 Office에서 솔루션을 실행하는 데 사용됩니다. 다음 표에서는 Windows와 Office의 각 조합에 필요한 런타임 버전을 보여 줍니다.  
  
|Windows 버전|Microsoft Office 버전|필요한 Visual Studio Tools for Office 런타임 버전|  
|------------------------|---------------------------------|--------------------------------------------------------------------|  
|32비트|32비트|32비트|  
|64비트|32비트|64비트|  
|64비트|64비트|64비트|  
  
 Office를 설치하는 경우 필요한 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 버전이 Office와 함께 설치됩니다. 예를 들어 Office의 64비트 버전을 Windows의 64비트 버전에 설치하는 경우 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 의 64비트 버전도 설치됩니다. 설치에 대 한 자세한 내용은 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Office와 함께 참조 [Visual Studio Tools for Office 런타임 설치 시나리오](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)합니다.  
  
 Office의 64비트 버전은 Visual Studio 2008에서 2007 Microsoft Office system용 프로젝트 템플릿을 사용하여 만든 Office 솔루션도 실행할 수 있습니다. 그러나 Visual Studio 2008에서 Microsoft Office 2003용 프로젝트 템플릿을 사용하여 만든 Office 솔루션 또는 Visual Studio 2005를 사용하여 만든 Office 솔루션은 실행할 수 없습니다. 자세한 내용은 참조 [다른 버전의 Microsoft Office에서 솔루션을 실행](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)합니다.  
  
## <a name="repair-the-visual-studio-2010-tools-for-office-runtime"></a>Visual Studio 2010 Tools for Office 런타임 복구  
 런타임을 복구해야 하는 경우 제어판에서 **프로그램 및 기능** 이나 **프로그램 추가/제거** 를 열고 프로그램 목록에서 **Microsoft Visual Studio 2010 Tools for Office Runtime** 을 선택한 다음 **제거**를 클릭합니다. 실행되는 설치 프로그램에서 런타임을 복구할 수 있습니다. **변경**을 클릭하면 런타임을 복구하기 위한 옵션이 표시되지 않습니다.  
  
## <a name="see-also"></a>참고자료  
 [Visual Studio Tools for Office 런타임 설치 시나리오](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)   
 [Visual Studio Tools for Office 런타임의 어셈블리](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)   
 [Visual Studio에서 Office 솔루션의 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)   
 [VSTO 추가 기능 아키텍처](../vsto/architecture-of-vsto-add-ins.md)   
 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [업그레이드 및 Office 솔루션 마이그레이션](../vsto/upgrading-and-migrating-office-solutions.md)  
  
  
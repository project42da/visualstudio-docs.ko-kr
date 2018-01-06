---
title: "Visual Studio Tools for Office 런타임 설치 시나리오 | Microsoft Docs"
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
helpviewer_keywords: Visual Studio Tools for Office runtime, installation scenarios
ms.assetid: 71f34daf-8163-4a53-a401-9cab6581f30d
caps.latest.revision: "42"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 057b9430f6cbac64479e6623e74497427f7824ee
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-tools-for-office-runtime-installation-scenarios"></a>Visual Studio Tools for Office Runtime Installation Scenarios
  세 가지 방법으로 Visual Studio 2010 Tools for Office Runtime을 설치할 수 있습니다.  
  
-   Visual Studio를 설치할 때  
  
-   Microsoft Office를 설치할 때  
  
-   재배포 가능한 Visual Studio 2010 Tools for Office Runtime을 설치할 때  
  
 설치된 런타임 구성 요소는 컴퓨터의 구성과 설치 시나리오에 따라 달라집니다.  
  
## <a name="runtime-components-that-are-installed-in-each-installation-scenario"></a>각 설치 시나리오에서 설치된 런타임 구성 요소  
 Visual Studio 2010 Tools for Office Runtime에는 세 가지 구성 요소인 Office 솔루션 로더, .NET Framework 3.5용 Office 확장 및 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상용 Office 확장이 있습니다. 런타임을 설치할 때 Office 솔루션 로더가 항상 설치됩니다. .NET Framework용 Office 확장의 설치는 컴퓨터의 구성과 설치 시나리오에 따라 달라집니다. 런타임을 처음 설치할 때 Office 확장명 중 하나를 설치할 수 없는 경우 런타임은 나중에 특정 요구 사항이 충족될 때 없는 Office 확장을 자동으로 설치합니다. 런타임의이 기능을 라고 *필요할 때 설치*합니다.  
  
 다음 표에서는 각 런타임 설치 시나리오에서 기본적으로 설치되는 런타임 구성 요소를 보여 줍니다. 각 시나리오에 대한 자세한 내용은 뒷부분에 있습니다.  
  
|런타임 설치 시나리오|Office 솔루션 로더|.NET Framework 3.5용 Office 확장|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]용 Office 확장|[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]용 Office 확장|  
|-----------------------------------|----------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------|  
|[!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] 이상과 함께|예|예, .NET Framework 3.5가 이미 설치된 경우|예|예|  
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]과 함께|예|예, .NET Framework 3.5가 이미 설치된 경우|아니요|아니요|  
|Office 2010 서비스 팩 1(SP1) 이상과 함께|예|예, .NET Framework 3.5가 이미 설치된 경우|예, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]가 이미 설치된 경우|아니요|  
|재배포 가능한 런타임과 함께|예|예, .NET Framework 3.5가 이미 설치된 경우|예, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]가 이미 설치된 경우|예, [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]가 이미 설치된 경우|  
  
### <a name="installing-the-runtime-with-visual-studio-or-the-microsoft-office-developer-tools-for-visual-studio"></a>Visual Studio 또는 Visual Studio용 Microsoft Office 개발자 도구와 함께 런타임 설치  
 Visual Studio에서 Office 개발자 도구를 설치하는 경우 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] 및 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]용 Office 확장이 개발 컴퓨터에 항상 설치됩니다. .NET Framework 3.5용 Office 확장은 .NET Framework 3.5가 이미 개발 컴퓨터에 있는 경우에만 설치됩니다. [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]을 설치한 후 .NET Framework 3.5를 설치하는 경우 .NET Framework 3.5를 대상으로 하는 Office 프로젝트를 처음으로 만들 때 런타임은 .NET Framework 3.5용 Office 확장을 자동으로 설치합니다.  
  
> [!WARNING]  
>  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] 이상을 사용하여 .NET Framework 3.5를 대상으로 하는 Office 프로젝트를 만들 수 없습니다.  
  
 Office 개발자 도구를 설치 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: Office 솔루션을 개발할 수 있도록 컴퓨터 구성](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)합니다.  
  
### <a name="installing-the-runtime-with-office"></a>Office와 함께 런타임 설치  
 Office를 설치할 때 .NET Framework 3.5용 Office 확장은 .NET Framework 3.5가 이미 컴퓨터에 있는 경우 설치됩니다. Office 다음에 .NET Framework 3.5를 설치하는 경우 Office 응용 프로그램에서 .NET Framework 3.5를 대상으로 하는 솔루션을 처음으로 로드하려고 할 때 런타임은 .NET Framework 3.5용 Office 확장을 자동으로 설치합니다.  
  
 Office를 설치할 때 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상이 이미 있는 경우에도 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상용 Office 확장은 Office와 함께 설치되지 않습니다.  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]용 Office 확장은 Office와 함께 설치됩니다. 최종 사용자는 Windows 업데이트를 설치하여 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]용 Office 확장을 가져올 수 있습니다.  
  
 사용자가 응용 프로그램을 사용하는 데 필요한 확장을 갖고 있도록 하려면 재배포 가능한 최신 버전의 Visual Studio 2010 Tools for Office Runtime을 솔루션의 필수 구성 요소로 포함합니다. 필수 구성 요소에 대 한 자세한 내용은 참조 [배포를 위한 Office 솔루션 필수 조건](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e)합니다.  
  
### <a name="installing-the-runtime-by-using-the-runtime-redistributable"></a>재배포 가능한 런타임을 사용하여 런타임 설치  
 재배포 가능한 Visual Studio 2010 Tools for Office Runtime을 수동으로 실행하거나 Office 솔루션을 배포할 때 재배포 가능한 런타임을 필수 구성 요소로 포함하여 런타임을 설치할 수 있습니다.  
  
 재배포 가능한 Visual Studio 2010 Tools for Office Runtime을 사용하여 런타임을 설치하는 경우 해당 버전의 .NET Framework가 이미 컴퓨터에 있으면 .NET Framework 3.5용 Office 확장과 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상용 Office 확장이 설치됩니다. 런타임이 설치될 때 컴퓨터에 이러한 .NET Framework 버전 중 하나가 없는 경우 없는 .NET Framework 버전용 Office 확장이 해당 시점에 설치되지 않습니다. 나중에 없는 .NET Framework 버전을 설치하는 경우 다음번에 해당 Office 확장을 필요로 하는 솔루션이 설치되거나(런타임이 ClickOnce를 사용하여 배포된 솔루션과 함께 설치된 경우) 로드될 때(런타임이 Windows Installer를 사용하여 배포된 솔루션과 함께 설치된 경우) 런타임은 해당 Office 확장을 자동으로 설치합니다.  
  
 ClickOnce 솔루션에 필수 구성 요소를 포함 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: Office 솔루션을 실행 하려면 최종 사용자 컴퓨터에 필수 조건 설치](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98)합니다. 재배포 가능 패키지에서 런타임을 수동으로 설치 하는 방법에 대 한 자세한 내용은 참조 하십시오. [하는 방법: Office 런타임 재배포 가능 패키지에 대 한 Visual Studio Tools를 설치](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio Tools for Office Runtime Overview](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Visual Studio Tools for Office 런타임의 어셈블리](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)  
  
  
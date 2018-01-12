---
title: "방법: Visual Studio Tools for Office 런타임 재배포 가능 설치 | Microsoft Docs"
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
helpviewer_keywords:
- Office runtime [Office development in Visual Studio]
- installing Office development tools in Visual Studio
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 5f76191ca8b41f252e5009c0d3e7e09415f6f081
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-install-the-visual-studio-tools-for-office-runtime-redistributable"></a>방법: 재배포 가능한 Visual Studio Tools for Office 런타임 설치
  Visual Studio 2010 Tools for Office Runtime의 Microsoft Office 개발자 도구를 사용 하 여 만든 솔루션을 사용 하는 컴퓨터에 설치 해야 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 런타임은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 및 Microsoft Office를 설치할 때 자동으로 설치됩니다. 자세한 내용은 [Visual Studio Tools for Office Runtime Installation Scenarios](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)을 참조하십시오.  
  
 다음과 같은 상황에서는 아래의 수동 설치 지침을 따라야 할 수 있습니다.  
  
-   [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]을 서버에 설치해야 합니다. 예를 들어 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 사용하여 서버에서 문서 수준 솔루션을 관리하려고 합니다.  
  
-   Office 솔루션에 대한 다른 모든 필수 구성 요소가 이미 설치된 컴퓨터에 런타임을 설치해야 합니다.  
  
    > [!NOTE]  
    >  .NET Framework와 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]을 설치하려면 개발 컴퓨터의 관리자여야 합니다.  
  
### <a name="to-install-the-visual-studio-tools-for-office-runtime"></a>Visual Studio Tools for Office 런타임을 설치하려면  
  
1.  [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 설치합니다.  
  
    -   다운로드 하는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], 참조 [Microsoft.NET Framework 4 (웹 설치 관리자)](http://go.microsoft.com/fwlink/?LinkId=178957)합니다.  
  
    -   다운로드 하는 [!INCLUDE[net_client_v40_long](../vsto/includes/net-client-v40-long-md.md)], 참조 [MICROSOFT.NET Framework 4 Client Profile (웹 설치 관리자)](http://go.microsoft.com/fwlink/?LinkId=178958)합니다.  
  
    -   다운로드 하는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], 참조 [Microsoft.NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653)합니다.  
  
2.  vstor_redist.exe를 실행하여 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]을 설치합니다.  
  
     이러한 설치 파일을 다운로드할 수 있습니다 [Visual Studio 2010 Tools for Office Runtime](http://go.microsoft.com/fwlink/?LinkId=140384)합니다. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에 대한 필수 구성 요소는 .NET Framework에 대한 필수 구성 요소와 일치합니다.  
  
     [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]언어 팩을 포함 합니다. Windows 설치가 영어 이외의 언어로 설정된 경우 Windows에 사용하는 동일한 언어로 런타임 메시지를 표시할 수 있습니다. 이와 마찬가지로 최종 사용자가 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]을 설치하고 영어 이외의 언어로 설정된 Windows 설치에서 솔루션을 실행하는 경우 런타임 메시지가 Windows와 동일한 언어로 표시됩니다. 경우에 따라 추가 언어 팩이 필요할 수 있습니다. 예를 들어 windows 둘 이상의 언어 설정을 사용 하거나 이미 설치 된 후 다른 언어로 전환 하는 경우 추가 언어 팩 할 수도 있습니다는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다. 언어 팩을 찾을 수 있습니다 [Microsoft Visual Studio 2010 Tools for Microsoft Office System (버전 4.0 런타임) 언어 팩](http://go.microsoft.com/fwlink/?LinkId=140386)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작 &#40; Visual Studio &#41;에서 Office 개발](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Configuring a Computer to Develop Office Solutions](../vsto/configuring-a-computer-to-develop-office-solutions.md)   
 [방법: Office 솔루션을 개발 하도록 컴퓨터 구성](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)   
 [방법: Office 주 Interop 어셈블리 설치](../vsto/how-to-install-office-primary-interop-assemblies.md)   
 [ServerDocument 클래스를 사용 하 여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)  
  
  
---
title: .NET Framework 4 이상으로 Office 솔루션 마이그레이션 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Project.TargetFrameworkWarning
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ac244bebb1a625c7858a62399ee79126e309cf2
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571801"
---
# <a name="migrating-office-solutions-to-the-net-framework-4-or-later"></a>.NET Framework 4 이상으로 Office 솔루션 마이그레이션
  Office 프로젝트의 대상 프레임워크가 이전 버전의 .NET Framework에서 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상으로 변경된 경우 개발 및 최종 사용자 컴퓨터에서 계속 솔루션을 실행하기 위해 몇 가지 추가 단계가 필요할 수 있습니다. 자세한 내용은 참조 [변경 내용이.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Office 프로젝트를 실행 하는 데 필요한](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.  
  
 또한 프로젝트가 더 이상 컴파일되지 않을 수 있습니다. Office 프로젝트의 일부 기능은 각 버전의 .NET Framework에 대해 다른 프로그래밍 모델을 사용합니다. Office 프로젝트의 대상 프레임워크가 이전 버전의 .NET Framework에서 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상으로 변경된 경우 프로젝트의 코드를 다음과 같이 변경해야 합니다.  
  
-   [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Excel 및 Word 프로젝트 업데이트](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Office 프로젝트에서 리본 메뉴 사용자 지정 업데이트](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Outlook 프로젝트에서 양식 영역 업데이트](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
 이전 버전의 Visual Studio에서 해당 프로젝트를 업그레이드하는 경우 Office 프로젝트의 대상 프레임워크가 변경됩니다. 자세한 내용은 참조 [업그레이드 및 Office 솔루션 마이그레이션](../vsto/upgrading-and-migrating-office-solutions.md)합니다.  
  
 이유에 대 한 자세한 내용은 Office 프로젝트의 일부 기능이 다른 프로그래밍 모델을 가져야 대상으로 지정할 경우는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상 [.NET Framework 4 또는.NET Framework 4.5를대상으로하는Office프로젝트의디자인변경](../vsto/changes-to-the-design-of-office-projects-that-target-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md) 및 [Visual Studio Tools for Office runtime 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)합니다.  
  
## <a name="see-also"></a>참고자료  
 [디자인 하 고 Office 솔루션을 만들려면](../vsto/designing-and-creating-office-solutions.md)   
 [방법:.NET Framework의 버전 대상](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [Office 솔루션의 오류 문제 해결](../vsto/troubleshooting-errors-in-office-solutions.md)   
 [Office 솔루션 오류에에서 대 한 추가 지원](../vsto/additional-support-for-errors-in-office-solutions.md)  
  
  
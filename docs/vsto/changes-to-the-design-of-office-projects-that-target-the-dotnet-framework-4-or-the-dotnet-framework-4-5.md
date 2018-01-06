---
title: ".NET Framework 4 또는.NET Framework 4.5 대상으로 하는 Office 프로젝트의 디자인 변경 | Microsoft Docs"
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
- Office development in Visual Studio, what's new
- what's new [Office development in Visual Studio]
ms.assetid: 290f5cb4-e2ee-4ed8-987c-2f013405cee9
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: ea7605ae01dc839dcac8e2cde3f658a94d6bb474
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="changes-to-the-design-of-office-projects-that-target-the-net-framework-4-or-the-net-framework-45"></a>.NET Framework 4 또는 .NET Framework 4.5를 대상으로 하는 Office 프로젝트의 디자인 변경
  [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)]부터 Visual Studio에서는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 Office 프로젝트의 디자인에 몇 가지 변경 사항이 도입되었습니다. 이전 버전의 Visual Studio에서 Office 프로젝트를 사용하는 데 익숙한 경우 .NET Framework 4.0 이상의 버전을 대상으로 하는 Office 프로젝트를 개발하기 전에 이러한 변경 사항을 알고 있어야 합니다. 기본적으로 Visual Studio 2013 이상을 사용하여 만드는 모든 프로젝트는 .NET Framework 4.0 이상을 대상으로 합니다.  
  
 다음 섹션에서는 이러한 Office 프로젝트 디자인 변경 사항에 대해 설명합니다.  
  
## <a name="understanding-the-interface-based-design-of-the-visual-studio-2010-tools-for-office-runtime"></a>Visual Studio 2010 Tools for Office Runtime의 인터페이스 기반 디자인 이해  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 Office 프로젝트를 개발하는 경우 Visual Studio 2010 Tools for Office Runtime에서 사용하는 대부분의 형식은 인터페이스입니다. 이는 이러한 형식이 클래스인 이전 버전의 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 크게 변경된 사항입니다. 예를 들어 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 경우 <xref:Microsoft.Office.Tools.Excel.Worksheet> 및 <xref:Microsoft.Office.Tools.Word.Document> 형식은 클래스가 아닌 인터페이스입니다. 자세한 내용은 [Visual Studio Tools for Office Runtime Overview](../vsto/visual-studio-tools-for-office-runtime-overview.md)을 참조하십시오.  
  
 이전 버전의에서 직접 인스턴스화할 수 있는 모든 형식의 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)], 이제 이러한 형식의 인스턴스를 가져올 수 Globals.Factory 개체의 메서드를 사용 합니다. 예를 들어, 구현 하는 개체를 가져오려면는 <xref:Microsoft.Office.Tools.Excel.SmartTag> 인터페이스를 Globals.Factory.CreateSmartTag 메서드를 사용 합니다. 자세한 내용은 다음 항목을 참조하세요.  
  
-   [Excel 및.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Word 프로젝트 업데이트](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Office 프로젝트에서 리본 메뉴 사용자 지정 업데이트](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
-   [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 Outlook 프로젝트에서 양식 영역 업데이트](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)  
  
### <a name="new-base-classes-in-office-projects"></a>Office 프로젝트의 새 기본 클래스  
 Visual Studio 2010 Tools for Office Runtime의 새로운 인터페이스 기반 디자인은 Office 프로젝트에서 생성된 클래스(예: `ThisDocument`, `ThisWorkbook`및 `ThisAddIn`)에 영향을 줍니다. .NET Framework 3.5 및 이전 버전의 framework 대상으로 하는 Office 프로젝트에서 이러한 생성 된 클래스의 클래스에서 파생 된 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Microsoft.Office.Tools.Word.Document, Microsoft.Office.Tools.Excel.Worksheet, 같은 및 Microsoft.Office.Tools.AddIn 합니다. [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상을 대상으로 하는 프로젝트에서 이러한 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 클래스는 이제 인터페이스입니다. 따라서 Office 프로젝트에서 생성된 클래스는 더 이상 해당 클래스에서 구현을 파생시킬 수 없습니다. 대신 생성된 클래스는 <xref:Microsoft.Office.Tools.Word.DocumentBase>, <xref:Microsoft.Office.Tools.Excel.WorksheetBase>및 <xref:Microsoft.Office.Tools.AddInBase>와 같은 새 기본 클래스에서 파생됩니다. 자세한 내용은 [Programming VSTO Add-Ins](../vsto/programming-vsto-add-ins.md) 및 [Programming Document-Level Customizations](../vsto/programming-document-level-customizations.md)를 참조하세요.  
  
 기본 클래스는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 재배포 가능 패키지의 일부가 아닙니다. 대신 Visual Studio에 포함된 유틸리티 어셈블리에서 정의됩니다. 이러한 어셈블리는 Office 프로젝트를 빌드할 때 출력 폴더에 복사되고 솔루션과 함께 배포되어야 합니다. 유틸리티 어셈블리에 대한 자세한 내용은 [Assemblies in the Visual Studio Tools for Office Runtime](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)를 참조하세요.  
  
## <a name="breaking-changes-in-office-projects-that-are-retargeted-to-the-net-framework-4"></a>.NET Framework 4로 대상이 변경되는 Office 프로젝트의 주요 변경 내용  
 다음 표에는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상으로 대상이 변경되는 Office 프로젝트에서 경험할 수 있는 주요 변경 내용이 나와 있습니다. 자세한 내용은 [Migrating Office Solutions to the .NET Framework 4 or later](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)을 참조하세요.  
  
|주요 변경 내용|결과|  
|---------------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute> 는 Office 프로젝트에서 더 이상 사용되거나 지원되지 않습니다.|Visual Studio 2008에서 업그레이드하는 Office 프로젝트의 AssemblyInfo 코드 파일에서 이 특성을 제거해야 합니다. 자세한 내용은 참조 [.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 실행 Office 프로젝트에 필요한 변경 사항](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.|  
|ExcelLocale1033Attribute는 더 이상 사용 되거나 Excel 프로젝트에서 지원 됩니다.|Excel 프로젝트의 AssemblyInfo 코드 파일에서 이 특성을 제거해야 합니다. 자세한 내용은 참조 [Excel 및 Word 프로젝트는.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 업데이트](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.|  
|**리본(비주얼 디자이너)** 프로젝트 항목의 프로그래밍 모델이 변경되었습니다.|프로젝트에서 모든 리본 항목에 대한 코드 숨김 파일을 수정해야 합니다. 또한 런타임에 리본 컨트롤을 인스턴스화하거나, 리본 이벤트를 처리하거나, 리본 구성 요소의 위치를 프로그래밍 방식으로 설정하는 모든 코드를 수정해야 합니다. 자세한 내용은 참조 [office에서 리본 메뉴 사용자 지정 업데이트를 마이그레이션하는.NET Framework 4 또는.NET Framework 4.5를 투영](../vsto/updating-ribbon-customizations-in-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.|  
|Outlook 양식 영역의 프로그래밍 모델이 변경되었습니다.|프로젝트의 모든 양식 영역에 대한 코드 숨김 파일과 런타임에 특정 양식 영역 클래스를 인스턴스화하는 모든 코드를 수정해야 합니다. 자세한 내용은 참조 [Outlook에서 양식 영역 업데이트 프로젝트를 마이그레이션하는.NET Framework 4 또는.NET Framework 4.5를](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.|  
|Excel 및 Word 프로젝트에서 스마트 태그에 대한 프로그래밍 모델이 변경되었습니다. [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] 및 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]에서는 스마트 태그가 사용되지 않습니다.|솔루션에서 스마트 태그를 사용하는 경우 프로젝트를 빌드할 때 오류가 발생합니다. 스마트 태그가 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] 및 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]에서 더 이상 사용되지 않기 때문에 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] 이상에서 솔루션을 테스트하고 디버그하려면 태그를 제거해야 합니다.|  
|GetVstoObject 및 HasVstoObject 메서드 구문이 변경 되었습니다.|주 interop 어셈블리 (Pia) 로부터 네이티브 개체에 액세스 하면 하거나 프로젝트에서 Globals.Factory 속성에서 반환 되는 개체에서 이러한 메서드에 액세스할 수 있습니다 Globals.Factory 개체를 이러한 메서드에 전달 해야 합니다. 자세한 내용은 참조 [Excel 및 Word 프로젝트는.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 업데이트](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.|  
|Word 콘텐츠 컨트롤의 이벤트가 새 대리자와 연결됩니다.|Word 콘텐츠 컨트롤의 이벤트를 처리하는 모든 코드를 수정하여 새 대리자를 지정해야 합니다. 자세한 내용은 참조 [Excel 및 Word 프로젝트는.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 업데이트](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.|  
|OLEObject 및 OLEControl 클래스 이름이 바뀌었습니다.|이러한 클래스의 인스턴스를 사용하는 모든 코드를 수정하여 <xref:Microsoft.Office.Tools.Excel.ControlSite> 또는 <xref:Microsoft.Office.Tools.Word.ControlSite> 개체를 대신 사용해야 합니다. 자세한 내용은 참조 [Excel 및 Word 프로젝트는.NET Framework 4 또는.NET Framework 4.5로 마이그레이션하는 업데이트](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)합니다.|  
|호스트 항목 클래스와 같은 `ThisWorkbook`, `Sheet`  *n* , `ThisDocument`, 및 `ThisAddIn`, 더 이상 재정의할 수 있는 Dispose 메서드를 제공 합니다.|모든 코드의에서 옮겨야 Dispose 메서드 재정의 호스트 항목 클래스에서 시스템 종료 이벤트 처리기에 예를 들어 `ThisAddIn_Shutdown`, 호스트 항목 클래스에서 Dispose 메서드 재정의 제거 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Migrating Office Solutions to the .NET Framework 4 or later](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Office 개발의 새로운 기능](http://msdn.microsoft.com/en-us/bf054af2-c896-4723-aa15-6381145b14bb)   
 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)  
  
  
---
title: "Visual Studio Tools for Office 런타임의 어셈블리"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio Tools for Office Runtime, 어셈블리"
ms.assetid: d2b7f8f4-0f41-4943-bca5-48c520748b7e
caps.latest.revision: 29
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 28
---
# Visual Studio Tools for Office 런타임의 어셈블리
  Office 프로젝트를 만들면 Visual Studio에서 프로젝트 형식 및 프로젝트의 대상 .NET Framework에 사용되는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 어셈블리에 자동으로 참조를 추가합니다. .NET Framework 3.5, [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 및 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]용 Office 확장에는 각각 다른 어셈블리가 있습니다. Office 확장에 대한 자세한 내용은 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)를 참조하세요.  
  
## .NET Framework 4 및 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]용 Office 확장의 어셈블리  
 다음 표에는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 및 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]용 Office 확장에 포함된 어셈블리가 나열되어 있습니다. 이러한 어셈블리의 네임스페이스 및 형식에 대한 설명서는 [관리되는 참조&#40;Visual Studio에서 Office 개발&#41;](../vsto/managed-reference-office-development-in-visual-studio.md)를 참조하세요.  
  
|어셈블리 이름|설명|  
|-------------|--------|  
|Microsoft.Office.Tools.Common.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   리본 사용자 지정 및 스마트 태그를 만들기 위한 형식입니다. **Note:**      [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] 및 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]에서는 스마트 태그가 사용되지 않습니다.<br />-   문서 수준 사용자 지정의 작업창 및 VSTO 추가 기능의 사용자 지정 작업창을 만들기 위한 형식입니다.|  
|Microsoft.Office.Tools.Excel.dll|Excel 프로젝트에 대한 호스트 항목 및 호스트 컨트롤을 나타내는 인터페이스 및 지원 형식을 제공합니다. 자세한 내용은 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)을 참조하세요.|  
|Microsoft.Office.Tools.Outlook.dll|Outlook VSTO 추가 기능에서 사용자 지정 양식 영역을 만드는 데 사용할 수 있는 형식을 제공합니다.|  
|Microsoft.Office.Tools.Word.dll|Word 프로젝트에 대한 호스트 항목 및 호스트 컨트롤을 나타내는 인터페이스 및 지원 형식을 제공합니다. 자세한 내용은 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)을 참조하세요.|  
|Microsoft.Office.Tools.v4.0.Framework.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   Visual Studio Tools for Office 런타임에서 throw될 수 있는 예외입니다.<br />-   Outlook 양식 영역을 만들 때 사용할 수 있는 특성입니다.|  
|Microsoft.Office.Tools.dll|Visual Studio Tools for Office 런타임 인프라의 일부이며 코드에서 직접 사용할 수 없도록 되어 있는 형식을 제공합니다.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성 및 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType> 인터페이스로, 문서 수준 사용자 지정에서 데이터 개체를 캐시하는 데 사용할 수 있습니다. 자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하세요.<br />-   <xref:Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction> 인터페이스로, Office 솔루션에 대한 ClickOnce 설치 관리자의 최종 단계로 추가 설치 단계를 실행하기 위해 구현할 수 있습니다. 자세한 내용은 [ClickOnce를 사용하여 Office 솔루션 배포](../vsto/deploying-an-office-solution-by-using-clickonce.md)을 참조하세요.<br />-   Visual Studio Tools for Office 런타임에서 throw될 수 있는 예외입니다.<br />-   Visual Studio Tools for Office Runtime 인프라의 일부이며 코드에서 직접 사용할 수 없도록 되어 있는 기타 형식입니다.|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스로, 문서에 사용자 지정 어셈블리를 연결하고 문서에서 캐시된 데이터에 액세스하는 데 사용할 수 있습니다. 자세한 내용은 [ServerDocument 클래스를 사용하여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)을 참조하십시오.<br />-   문서 수준 사용자 지정에서 캐시된 데이터의 계층 구조를 나타내는 여러 클래스입니다. 자세한 내용은 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하세요.|  
  
 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]를 대상으로 하는 프로젝트도 다음과 같은 어셈블리를 참조합니다. 이러한 어셈블리는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 재배포 가능 패키지의 일부가 아닙니다. 대신 솔루션과 함께 배포되어야 하는 종속 어셈블리입니다. 기본적으로 프로젝트에 대한 빌드 출력 폴더에 복사되며, 이러한 어셈블리의 **로컬 복사** 속성은 **True**로 설정됩니다. ClickOnce를 사용하여 프로젝트를 배포하는 경우 이러한 어셈블리는 생성된 패키지에 포함 됩니다.  
  
|어셈블리 이름|설명|  
|-------------|--------|  
|Microsoft.Office.Tools.Common.v4.0.Utilities.dll|VSTO 추가 기능 프로젝트에서 생성된 `ThisAddIn` 클래스 및 모든 프로젝트에서 생성된 리본 클래스에 대해 기본 클래스를 제공합니다.|  
|Microsoft.Office.Tools.Excel.v4.0.Utilities.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   Excel에 대한 문서 수준 프로젝트에서 생성된 `ThisWorkbook` 및 `Sheet` 클래스에 대한 기본 클래스입니다.<br />-   Excel 프로젝트의 워크시트에서 사용할 수 있는 Windows Forms 컨트롤입니다.|  
|Microsoft.Office.Tools.Outlook.v4.0.Utilities.dll|Outlook 프로젝트에서 생성된 `ThisAddIn` 및 양식 영역 클래스에 대해 기본 클래스를 제공합니다.|  
|Microsoft.Office.Tools.Word.v4.0.Utilities.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   Word에 대한 문서 수준 프로젝트에서 생성된 `ThisDocument` 클래스에 대한 기본 클래스입니다.<br />-   Word 프로젝트의 문서에서 사용할 수 있는 Windows Forms 컨트롤입니다.|  
  
## .NET Framework 3.5용 Office 확장의 어셈블리  
 다음 표에는 .NET Framework 3.5용 Office 확장에 포함된 어셈블리가 나열되어 있습니다. 이러한 어셈블리의 네임스페이스 및 클래스에 대한 설명서는 Visual Studio 2008 설명서의 다음과 같은 참조 섹션\([http:\/\/go.microsoft.com\/fwlink\/?LinkId\=160658](http://go.microsoft.com/fwlink/?LinkId=160658)\)을 참조하세요.  
  
|어셈블리 이름|설명|  
|-------------|--------|  
|Microsoft.Office.Tools.Common.v9.0.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   VSTO 추가 기능에 대한 Microsoft.Office.Tools.AddIn 기본 클래스입니다.<br />-   리본 사용자 지정 및 스마트 태그를 만들기 위한 클래스입니다. **Note:**      [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)] 및 [!INCLUDE[Word_14_short](../vsto/includes/word-14-short-md.md)]에서는 스마트 태그가 사용되지 않습니다.<br />-   문서 수준 사용자 지정의 작업창 및 VSTO 추가 기능의 사용자 지정 작업창을 만들기 위한 클래스입니다.|  
|Microsoft.Office.Tools.Excel.v9.0.dll|Excel 솔루션에 대한 호스트 항목 및 호스트 컨트롤을 제공합니다. 자세한 내용은 [확장된 개체를 사용하여 Excel 자동화](../vsto/automating-excel-by-using-extended-objects.md)을 참조하세요.|  
|Microsoft.Office.Tools.Outlook.v9.0.dll|Outlook VSTO 추가 기능에서 사용자 지정 양식 영역을 만드는 데 사용할 수 있는 클래스를 제공합니다.|  
|Microsoft.Office.Tools.Word.v9.0.dll|Word 솔루션에 대한 호스트 항목 및 호스트 컨트롤을 제공합니다. 자세한 내용은 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)을 참조하세요.|  
|Microsoft.Office.Tools.v9.0.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   Microsoft.VisualStudio.Tools.Office.RemoteBindableComponent 클래스로, 문서 수준 사용자 지정에서 호스트 컨트롤에 대해 데이터 바인딩 기능을 제공합니다.<br />-   Visual Studio Tools for Office Runtime 인프라의 일부이며 코드에서 직접 사용할 수 없도록 되어 있는 기타 형식입니다.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v9.0.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute 특성 및 Microsoft.VisualStudio.Tools.Applications.Runtime.ICachedType 인터페이스로, 문서 수준 사용자 지정에서 데이터 개체를 캐시하는 데 사용할 수 있습니다. 자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하세요.<br />-   Visual Studio Tools for Office 런타임에서 throw될 수 있는 예외입니다.<br />-   Visual Studio Tools for Office Runtime 인프라의 일부이며 코드에서 직접 사용할 수 없도록 되어 있는 기타 형식입니다.|  
|Microsoft.VisualStudio.Tools.Applications.Runtime.v10.0.dll|Microsoft.VisualStudio.Tools.Applications.Deployment.IAddInPostDeploymentAction 인터페이스로, Office 솔루션에 대한 ClickOnce 설치 관리자의 최종 단계로 추가 설치 단계를 실행하기 위해 구현할 수 있습니다. 자세한 내용은 [고급 Office 솔루션 배포](http://msdn.microsoft.com/ko-kr/9147b6f6-849f-4cb1-b2c5-e22658d74b02)를 참조하세요.|  
|Microsoft.VisualStudio.Tools.Applications.ServerDocument.v10.0.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   Microsoft.VisualStudio.Tools.Applications.ServerDocument 클래스로, 문서에 사용자 지정 어셈블리를 프로그래밍 방식으로 연결하고 문서에서 캐시된 데이터에 액세스하는 데 사용할 수 있습니다. 자세한 내용은 [ServerDocument 클래스를 사용하여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)을 참조하십시오.<br />-   문서 수준 사용자 지정에서 캐시된 데이터의 계층 구조를 나타내는 여러 클래스입니다. 자세한 내용은 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하세요.|  
|Microsoft.VisualStudio.Tools.Office.Runtime.v10.0.dll|다음과 같은 형식을 제공합니다.<br /><br /> -   Microsoft.VisualStudio.Tools.Office.Runtime.Security.AddInSecurityEntry 및 Microsoft.VisualStudio.Tools.Office.Runtime.Security.UserInclusionList 클래스로, .NET Framework 3.5를 대상으로 하는 Office 솔루션에 신뢰를 부여하는 사용자 포함 목록 항목을 만드는 데 사용할 수 있습니다.<br />-   Visual Studio Tools for Office 런타임 인프라의 일부이며 코드에서 직접 사용할 수 없도록 되어 있는 기타 형식입니다.|  
  
## 참고 항목  
 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Visual Studio Tools for Office 런타임 설치 시나리오](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)  
  
  
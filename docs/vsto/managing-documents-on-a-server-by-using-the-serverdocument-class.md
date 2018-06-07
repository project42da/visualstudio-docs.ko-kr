---
title: ServerDocument 클래스를 사용 하 여 서버의 문서 관리
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], managing on server
- Office documents [Office development in Visual Studio, managing on server
- ServerDocument class, managing documents on server
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97eed0e4cec143e51195347bfb90d430d8e1eadb
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573000"
---
# <a name="manage-documents-on-a-server-by-using-the-serverdocument-class"></a>ServerDocument 클래스를 사용 하 여 서버의 문서 관리
  사용할 수 있습니다는 `ServerDocument` 클래스에 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Microsoft Office Word 및 Microsoft Office Excel 설치 되어 있지 않은 경우에 문서 수준 사용자 지정의 여러 측면을 관리할 수 있습니다. 다음 작업을 수행할 수 있습니다.  
  
-   에 액세스 하 고 문서 또는 통합 문서의 데이터 캐시에 데이터를 수정 합니다. 자세한 내용은 참조 [문서에서 캐시 된 데이터에 사용할](#CachedData)합니다.  
  
-   문서와 연결 된 사용자 지정 어셈블리를 관리 합니다. 자세한 내용은 참조 [문서 사용자 지정 관리](#CustomizationInfo)합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="understand-the-serverdocument-class"></a>ServerDocument 클래스 이해  
 `ServerDocument` 클래스는 Office가 설치 되지 않은 컴퓨터에서 사용 하도록 설계 되었습니다. 따라서 일반적으로 사용이 클래스는 Office 프로젝트 대신 콘솔 프로젝트 또는 Windows Forms 프로젝트와 같은 Office와 함께 통합 되지 않는 응용 프로그램에서 합니다. 사용 하 여는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스에 *Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll* 어셈블리입니다.  
  
 `ServerDocument` 클래스를 사용 하 여 만든 문서 수준 사용자 지정에서 작동 하도록 사용할 수 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]합니다.  
  
 대 한 자세한 내용은 Visual Studio 2010 Tools for Office Runtime과 Office 확장에 대 한.NET Framework에 대 한 참조 [Visual Studio Tools for Office runtime 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)합니다.  
  
> [!NOTE]  
>  사용 하는 레거시 응용 프로그램의 경우는 `ServerDocument` 클래스에 `Visual Studio Tools for Office` system (버전 3.0 런타임), `Visual Studio Tools for Office` system (버전 3.0 런타임) 응용 프로그램을 실행 하는 컴퓨터에 설치 해야 합니다. `Visual Studio 2010 Tools for Office runtime` 이러한 응용 프로그램을 실행할 수 없습니다.  
  
##  <a name="CachedData"></a> 문서에서 캐시 된 데이터 사용  
 `ServerDocument` 클래스는 사용자 지정 된 문서에서 데이터 캐시를 사용 하는 데 사용할 멤버를 제공 합니다. 캐시 된 데이터에 대 한 자세한 내용은 참조 [데이터 캐시](../vsto/caching-data.md) 및 [서버에서 문서 데이터에에서 액세스](../vsto/accessing-data-in-documents-on-the-server.md)합니다.  
  
 다음 표에서 캐시 된 데이터로 작업 하는 데 사용할 수는 멤버를 나열 합니다.  
  
|작업|사용할 멤버|  
|----------|-------------------|  
|문서 데이터 캐시에 있는지 여부를 확인 합니다.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> 메서드|  
|문서에서 캐시 된 데이터에 액세스 하 합니다.<br /><br /> 자세한 내용은 참조 [서버에서 문서 데이터에에서 액세스](../vsto/accessing-data-in-documents-on-the-server.md)합니다.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 속성|  
  
##  <a name="CustomizationInfo"></a> 문서 사용자 지정 관리  
 멤버를 사용할 수는 `ServerDocument` 문서와 연결 된 사용자 지정 어셈블리를 관리 하는 클래스입니다. 예를 들어 없습니다 프로그래밍 방식으로 제거 하 여 사용자 지정 문서에서 문서가 더 이상 사용자 지정의 일부입니다.  
  
 다음 표에서 사용자 지정 어셈블리를 관리 하는 데 사용할 수는 멤버를 나열 합니다.  
  
|작업|사용할 멤버|  
|----------|-------------------|  
|문서 여부를 확인 하려면 문서 수준 사용자 지정의 일부입니다.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> 메서드|  
|프로그래밍 방식으로 런타임에 문서에는 사용자 지정을 연결 합니다.<br /><br /> 자세한 내용은 참조 [하는 방법: 연결 관리 문서에 코드 확장](../vsto/how-to-attach-managed-code-extensions-to-documents.md)|중 하나는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 메서드.|  
|런타임에 프로그래밍 방식으로 문서에서 사용자 지정을 제거 하려면<br /><br /> 자세한 내용은 참조 [하는 방법: 문서에서 관리 코드 확장명 제거](../vsto/how-to-remove-managed-code-extensions-from-documents.md)합니다.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> 메서드|  
|문서와 연결 된 경우 배포 매니페스트의 URL을 가져오려면 합니다.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> 속성|  
  
## <a name="see-also"></a>참고자료  
 [방법: 연결 관리 문서에 코드 확장](../vsto/how-to-attach-managed-code-extensions-to-documents.md)   
 [방법: 문서에서 관리 코드 확장 제거](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [데이터 캐시](../vsto/caching-data.md)  
  
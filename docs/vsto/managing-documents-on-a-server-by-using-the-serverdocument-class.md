---
title: "ServerDocument 클래스를 사용하여 서버의 문서 관리 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 서버에서 관리"
  - "Office 문서[Visual Studio에서 Office 개발], 서버에서 관리"
  - "ServerDocument 클래스, 서버에서 문서 관리"
ms.assetid: 1ac90e89-d07d-4874-9d24-6741d6679a21
caps.latest.revision: 40
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 39
---
# ServerDocument 클래스를 사용하여 서버의 문서 관리
  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 ServerDocument 클래스를 사용하면 Microsoft Office Word 및 Microsoft Office Excel이 설치되어 있지 않은 경우에도 문서 수준 사용자 지정의 여러 가지 측면을 관리할 수 있습니다.  다음 작업을 수행할 수 있습니다.  
  
-   문서 또는 통합 문서의 데이터 캐시에 있는 데이터에 액세스하고 이를 수정할 수 있습니다.  자세한 내용은 [문서의 캐시된 데이터 작업](#CachedData)을 참조하십시오.  
  
-   문서와 연결된 사용자 지정 어셈블리를 관리할 수 있습니다.  자세한 내용은 [문서 사용자 지정 관리](#CustomizationInfo)를 참조하십시오.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## ServerDocument 클래스 이해  
 ServerDocument 클래스는 Office가 설치되어 있지 않은 컴퓨터에서 사용하도록 디자인되었습니다.  따라서 대개 Office 프로젝트가 아니라 콘솔 프로젝트 또는 Windows Forms 프로젝트와 같이 Office와 통합되지 않은 응용 프로그램에서 이 클래스를 사용합니다.  사용 하는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll 어셈블리에 있는 클래스입니다.  
  
 ServerDocument 클래스를 사용 하 여 만든 문서 수준 사용자 지정에서 사용할 수 있습니다 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].  
  
 자세한 내용은 Visual Studio 2010 도구에 대 한 Office 런타임 및 Office 확장에 대 한.NET Framework 대 한 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
> [!NOTE]  
>  사용 하는 레거시 응용 프로그램이 있는 경우는 ServerDocument Office system 용 Visual Studio 도구에서 클래스 \(버전 3.0 런타임\), Office system 용 Visual Studio 도구 \(버전 3.0 런타임\) 응용 프로그램을 실행 하는 컴퓨터에 설치 해야 합니다.  Visual Studio 2010 도구 Office 런타임 응용이 프로그램을 실행할 수 없습니다.  
  
##  <a name="CachedData"></a> 문서의 캐시된 데이터 작업  
 ServerDocument 클래스는 사용자 지정된 문서의 데이터 캐시에 대해 작업하는 데 사용할 수 있는 멤버를 제공합니다.  캐시된 데이터에 대한 자세한 내용은 [데이터 캐싱](../vsto/caching-data.md) 및 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하십시오.  
  
 다음 표에는 캐시된 데이터에 대해 작업하는 데 사용할 수 있는 멤버가 나와 있습니다.  
  
|Task|사용할 멤버|  
|----------|------------|  
|문서에 데이터 캐시가 있는지 여부를 확인|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.IsCacheEnabled%2A> 메서드|  
|문서의 캐시된 데이터에 액세스<br /><br /> 자세한 내용은 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하십시오.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 속성|  
  
##  <a name="CustomizationInfo"></a> 문서 사용자 지정 관리  
 ServerDocument 클래스의 멤버를 사용하여 문서와 연결된 사용자 지정 어셈블리를 관리할 수 있습니다.  예를 들어 문서가 더 이상 사용자 지정의 일부가 되지 않도록 문서에서 사용자 지정을 프로그래밍 방식으로 제거할 수 있습니다.  
  
 다음 표에는 사용자 지정 어셈블리를 관리하는 데 사용할 수 있는 멤버가 나와 있습니다.  
  
|Task|사용할 멤버|  
|----------|------------|  
|문서가 문서 수준 사용자 지정의 일부인지 여부를 확인|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.GetCustomizationVersion%2A> 메서드|  
|런타임에 문서에 사용자 지정을 프로그래밍 방식으로 연결<br /><br /> 자세한 내용은 [방법: 문서에 관리 코드 확장 연결](../vsto/how-to-attach-managed-code-extensions-to-documents.md)을 참조하십시오.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 메서드 중 하나|  
|런타임에 문서에서 사용자 지정을 프로그래밍 방식으로 제거<br /><br /> 자세한 내용은 [방법: 문서에서 관리 코드 확장 제거](../vsto/how-to-remove-managed-code-extensions-from-documents.md)을 참조하십시오.|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> 메서드|  
|문서와 연결된 배포 매니페스트의 URL 가져오기|<xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.DeploymentManifestUrl%2A> 속성|  
  
## 참고 항목  
 [방법: 문서에 관리 코드 확장 연결](../vsto/how-to-attach-managed-code-extensions-to-documents.md)   
 [방법: 문서에서 관리 코드 확장 제거](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [데이터 캐싱](../vsto/caching-data.md)  
  
  
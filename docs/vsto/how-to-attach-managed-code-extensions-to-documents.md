---
title: "방법: 문서에 관리 코드 확장 연결 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 관리 코드 확장"
  - "관리 코드 확장[Visual Studio에서 Office 개발], 연결"
ms.assetid: b38c3a35-8b4a-4e86-8475-88fa8a873a5d
caps.latest.revision: 33
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 32
---
# 방법: 문서에 관리 코드 확장 연결
  사용자 지정 어셈블리를 기존의 Microsoft Office Word 문서 또는 Microsoft Office Excel 통합 문서에 연결할 수 있습니다.  문서 또는 통합 문서의 Microsoft Office 프로젝트와 개발 도구 Visual Studio 의해 지원 되는 파일 형식에서 수 있습니다.  자세한 내용은 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 사용자 지정을 Word 또는 Excel 문서에 연결하려면 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스의 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 메서드를 사용합니다.  <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스는 Microsoft Office가 설치되어 있지 않은 컴퓨터에서 실행하도록 디자인되었으므로 콘솔 또는 Windows Forms 응용 프로그램과 같이 Microsoft Office 개발과 직접 관련되지 않은 솔루션에서 이 메서드를 사용할 수 있습니다.  
  
> [!NOTE]  
>  코드에서 컨트롤을 지정된 문서에 없는 것으로 예상하는 경우 사용자 지정이 로드되지 않습니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.png "비디오에 링크") 관련 비디오 데모를 보려면 [How Do I: Attach or Detach a VSTO Assembly from a Word Document?](http://go.microsoft.com/fwlink/?LinkId=136782)를 참조하십시오.  
  
### 문서에 관리 코드 확장을 연결하려면  
  
1.  프로젝트에서 Microsoft Office 콘솔 응용 프로그램 또는 Windows Forms 프로젝트 같이 있지 않아도, Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll 및 Microsoft.VisualStudio.Tools.Applications.Runtime.dll 어셈블리에 대 한 참조를 추가 합니다.  
  
2.  코드 파일의 맨 위에 다음 **Imports** or **using** 문을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/CS/Program.cs#4)]
     [!code-vb[Trin_VstcoreDeployment#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/VB/Program.vb#4)]  
  
3.  정적 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 메서드를 호출합니다.  
  
     다음 코드 예제에서는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 오버로드를 사용합니다.  이 오버로드에서는 문서의 전체 경로 및 문서에 연결할 사용자 지정에 대한 배포 매니페스트의 위치를 지정하는 <xref:System.Uri>를 사용합니다.  이 예제에서는 **WordDocument1.docx**라는 Word 문서가 데스크톱에 있고 배포 매니페스트가 데스크톱에 있는 **Publish**라는 폴더에 있다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/CS/Program.cs#3)]
     [!code-vb[Trin_VstcoreDeployment#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/VB/Program.vb#3)]  
  
4.  프로젝트를 빌드하고 사용자 지정을 연결하려는 컴퓨터에서 응용 프로그램을 실행합니다.  컴퓨터 Visual Studio 2010 도구 Office 런타임이 설치 되어 있어야 합니다.  
  
## 참고 항목  
 [ServerDocument 클래스를 사용하여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [방법: 문서에서 관리 코드 확장 제거](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Office 솔루션의 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  
  
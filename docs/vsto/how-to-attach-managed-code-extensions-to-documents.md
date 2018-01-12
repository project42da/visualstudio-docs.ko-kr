---
title: "방법: 문서에 관리 코드 확장 연결 | Microsoft Docs"
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
- managed code extensions [Office development in Visual Studio], attaching
- documents [Office development in Visual Studio], managed code extensions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1653b0e903fd931d5df4b1dcce4dcbd99fbbae37
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-attach-managed-code-extensions-to-documents"></a>방법: 문서에 관리 코드 확장명 연결
  기존 Microsoft Office Word 문서 또는 Microsoft Office Excel 통합 문서에 사용자 지정 어셈블리를 연결할 수 있습니다. 문서 또는 통합 Microsoft Office 프로젝트와 Visual Studio에서 개발 도구에서 지원 되는 어떠한 파일 형식도 될 수 있습니다. 자세한 내용은 참조 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)합니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 사용자 지정 Word 또는 Excel 문서를 연결 하려면 사용 하 여는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 의 메서드는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스입니다. 때문에 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스는 Microsoft Office가 설치 되지 않은 컴퓨터에서 실행 되도록 설계 되었습니다, Microsoft Office 개발 (예: 콘솔 또는 Windows Forms 응용 프로그램)에 직접 관련 되지 않는 솔루션에서이 방법을 사용할 수 있습니다.  
  
> [!NOTE]  
>  사용자 지정 코드에서는 지정된 된 문서에 없는 컨트롤을 로드 되지 것입니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [i: 연결 수행 방법 또는 Word 문서에서 VSTO 어셈블리 분리?](http://go.microsoft.com/fwlink/?LinkId=136782)합니다.  
  
### <a name="to-attach-managed-code-extensions-to-a-document"></a>문서에 관리 코드 확장을 연결 하려면  
  
1.  콘솔 응용 프로그램과 같은 Microsoft Office 필요 없는 프로젝트 또는 Windows Forms 프로젝트를 Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll 및 Microsoft.VisualStudio.Tools.Applications.Runtime.dll에 대 한 참조를 추가 합니다. 어셈블리입니다.  
  
2.  다음 추가 **Imports** 또는 **를 사용 하 여** 문을 코드 파일의 맨 위에 있습니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#4](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#4)]
     [!code-vb[Trin_VstcoreDeployment#4](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#4)]  
  
3.  정적 호출 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 메서드.  
  
     다음 코드 예제에서는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.AddCustomization%2A> 오버 로드 합니다. 이 오버 로드 된 문서의 전체 경로 <xref:System.Uri> 문서를 연결 하려면 사용자 지정에 대 한 배포 매니페스트의 위치를 지정 하는 합니다. 이 예제에서는 Word 문서에 명명 된 가정 **WordDocument1.docx** 바탕 화면에 명명 된 폴더에 있는 배포 매니페스트 및 **게시** 바탕 화면에서 이기도 합니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#3](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#3)]
     [!code-vb[Trin_VstcoreDeployment#3](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#3)]  
  
4.  프로젝트를 빌드하고 사용자 지정을 연결 하려는 컴퓨터에 응용 프로그램을 실행 합니다. 컴퓨터는 Visual Studio 2010 Tools for Office Runtime 설치 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ServerDocument 클래스를 사용 하 여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [방법: 문서에서 관리 코드 확장을 제거 합니다.](../vsto/how-to-remove-managed-code-extensions-from-documents.md)   
 [Office 솔루션의 응용 프로그램 및 배포 매니페스트](../vsto/application-and-deployment-manifests-in-office-solutions.md)  
  
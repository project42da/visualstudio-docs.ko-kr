---
title: "방법: 문서에서 관리 코드 확장을 제거 합니다. | Microsoft Docs"
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
- managed code extensions [Office development in Visual Studio], removing
- documents [Office development in Visual Studio], managed code extensions
ms.assetid: e893d9a5-72a5-4087-b81b-04d4d3d9ebf8
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f9da75468ae417bd835b457cdbd5219ef9462df1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-remove-managed-code-extensions-from-documents"></a>방법: 문서에서 관리 코드 확장명 제거
  프로그래밍 방식으로 문서 또는 Microsoft Office Word 또는 Microsoft Office Excel 문서 수준 사용자 지정의 일부인 통합 문서에서 사용자 지정 어셈블리를 제거할 수 있습니다. 사용자 수 다음 문서를 열 내용이 되지만 문서에 추가 사용자 지정 사용자 인터페이스 (UI) 표시 되지 않습니다 및 코드가 실행 되지 않습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 제공 RemoveCustomization 방법 중 하나를 사용 하 여 사용자 지정 어셈블리를 제거할 수 있습니다는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]합니다. 어떤 방법을 사용 하 여 런타임 시 사용자 지정을 제거 하려는 여부에 따라 달라 집니다 (즉, 단어 하는 동안 사용자 지정의 코드를 실행 하 여 문서 또는 Excel 통합 문서를 연) 닫힌된 문서 또는 문서에서 사용자 지정을 제거 하려는 경우 또는 해당 i Microsoft Office가 설치 되지 않은 서버에서를 클릭 합니다.  
  
 ![비디오에 링크](../vsto/media/playvideo.gif "비디오에 링크") 관련된 동영상 데모를 참조 하십시오. [i: 연결 수행 방법 또는 Word 문서에서 VSTO 어셈블리 분리?](http://go.microsoft.com/fwlink/?LinkId=136782)합니다.  
  
### <a name="to-remove-the-customization-assembly-at-run-time"></a>런타임 시 사용자 지정 어셈블리를 제거 하려면  
  
1.  사용자 지정 코드에서 호출 된 <xref:Microsoft.Office.Tools.Word.Document.RemoveCustomization%2A> 메서드 (Word) 또는 <xref:Microsoft.Office.Tools.Excel.Workbook.RemoveCustomization%2A> 메서드 (Excel). 사용자 지정 필요 하지 않은 후에이 메서드를 호출 해야 합니다.  
  
     코드에서이 메서드를 호출 하는 위치는 사용자 지정 사용 방법에 따라 달라 집니다. 예를 들어 문서 자체 (사용자 지정 하지 함)만 해야 하는 다른 클라이언트에 문서를 보낼 준비가 될 때까지 사용자 지정 기능을 사용 하는 고객, 고객이 클릭 때 RemoveCustomization를 호출 하는 몇 가지 UI를 제공할 수 있습니다. 또는 사용자 지정 처음 열 때 고객이 직접 액세스할 수 있는 다른 기능을 제공 하지 않는 데이터로 문서를 채우면를 호출할 수 있습니다 RemoveCustomization 곧 사용자 지정 문서 초기화를 마칩니다.  
  
### <a name="to-remove-the-customization-assembly-from-a-closed-document-or-a-document-on-a-server"></a>닫힌된 문서 또는 문서에는 서버에서 사용자 지정 어셈블리를 제거 하려면  
  
1.  콘솔 응용 프로그램과 같은 Microsoft Office 필요 없는 프로젝트 또는 Windows Forms 프로젝트를 Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll 어셈블리에 대 한 참조를 추가 합니다.  
  
2.  다음 추가 **Imports** 또는 **를 사용 하 여** 문을 코드 파일의 맨 위에 있습니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#1](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#1)]
     [!code-vb[Trin_VstcoreDeployment#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#1)]  
  
3.  정적 호출 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> 의 메서드는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스 하 고 솔루션 문서 경로 매개 변수를 지정 합니다.  
  
     다음 코드 예제에서는 명명 된 문서에서 사용자 지정 제거 된다고 가정 **WordDocument1.docx** 바탕 화면입니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#2](../vsto/codesnippet/CSharp/Trin_VstcoreDeploymentCS/Program.cs#2)]
     [!code-vb[Trin_VstcoreDeployment#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreDeploymentVB/Program.vb#2)]  
  
4.  프로젝트를 빌드하고 사용자 지정을 제거 하려는 컴퓨터에 응용 프로그램을 실행 합니다. 컴퓨터는 Visual Studio 2010 Tools for Office Runtime 설치 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ServerDocument 클래스를 사용 하 여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [방법: 문서에 관리 코드 확장명 연결](../vsto/how-to-attach-managed-code-extensions-to-documents.md)  
  
  
---
title: "방법: 문서에서 관리 코드 확장 제거"
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
  - "관리 코드 확장[Visual Studio에서 Office 개발], 제거"
ms.assetid: e893d9a5-72a5-4087-b81b-04d4d3d9ebf8
caps.latest.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: 문서에서 관리 코드 확장 제거
  Microsoft Office Word 또는 Microsoft Office Excel용 문서 수준 사용자 지정의 일부인 문서 또는 통합 문서에서 사용자 지정 어셈블리를 프로그래밍 방식으로 제거할 수 있습니다.  그런 다음 사용자가 문서를 열어 내용을 보면 문서에 추가한 사용자 지정 UI\(사용자 인터페이스\)가 표시되지 않고 코드가 실행되지 않습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서 제공되는 RemoveCustomization 메서드 중 하나를 사용하여 사용자 지정 어셈블리를 제거할 수 있습니다.  사용하는 메서드는 Word 문서 또는 Excel 통합 문서가 열려 있는 동안 사용자 지정의 코드를 실행하여 런타임에 사용자 지정을 제거할지, 아니면 닫혀 있는 문서나 Microsoft Office가 설치되지 않은 서버에 있는 문서에서 사용자 지정을 제거할지에 따라 달라집니다.  
  
 ![비디오에 링크](~/docs/data-tools/media/playvideo.gif "비디오에 링크") 관련 비디오 데모를 보려면 [How Do I: Attach or Detach a VSTO Assembly from a Word Document?](http://go.microsoft.com/fwlink/?LinkId=136782)를 참조하십시오.  
  
### 런타임에 사용자 지정 어셈블리를 제거하려면  
  
1.  사용자 지정 코드에서 <xref:Microsoft.Office.Tools.Word.Document.RemoveCustomization%2A> 메서드\(Word의 경우\) 또는 <xref:Microsoft.Office.Tools.Excel.Workbook.RemoveCustomization%2A> 메서드\(Excel의 경우\)를 호출합니다.  이 메서드는 사용자 지정이 더 이상 필요하지 않은 경우에만 호출해야 합니다.  
  
     코드에서 이 메서드를 호출하는 위치는 사용자 지정의 사용 방법에 따라 달라집니다.  예를 들어 고객이 다른 고객에게 문서를 보낼 준비가 되기 전까지 사용자 지정이 아닌 문서 자체에만 필요한 사용자 지정 기능을 사용하는 경우, 고객이 클릭하면 RemoveCustomization을 호출하는 몇 가지 UI를 제공할 수 있습니다.  또는 문서를 처음 열 때 사용자 지정을 통해 문서를 데이터로 채우지만 사용자 지정에서 고객이 직접 액세스할 수 있는 다른 기능을 제공하지 않는 경우, 사용자 지정에서 문서 초기화를 완료하는 즉시 RemoveCustomization을 호출할 수 있습니다.  
  
### 닫혀 있는 문서 또는 서버에 있는 문서에서 사용자 지정 어셈블리를 제거하려면  
  
1.  Microsoft Office 등의 콘솔 응용 프로그램을 필요로 하지 않는 프로젝트 또는 Windows Forms 프로젝트에서 Microsoft.VisualStudio.Tools.Applications.ServerDocument.dll 어셈블리에 참조를 추가 합니다.  
  
2.  코드 파일의 맨 위에 다음 **Imports** 또는 **using** 문을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/CS/Program.cs#1)]
     [!code-vb[Trin_VstcoreDeployment#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/VB/Program.vb#1)]  
  
3.  <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스의 정적 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.RemoveCustomization%2A> 메서드를 호출하고 매개 변수의 솔루션 문서 경로를 지정합니다.  
  
     다음 코드 예제에서는 데스크톱에 있는 **WordDocument1.docx**라는 문서에서 사용자 지정을 제거한다고 가정합니다.  
  
     [!code-csharp[Trin_VstcoreDeployment#2](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/CS/Program.cs#2)]
     [!code-vb[Trin_VstcoreDeployment#2](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDeployment/VB/Program.vb#2)]  
  
4.  프로젝트를 빌드하고 사용자 지정을 제거하려는 컴퓨터에서 응용 프로그램을 실행합니다.  컴퓨터 Visual Studio 2010 도구 Office 런타임이 설치 되어 있어야 합니다.  
  
## 참고 항목  
 [ServerDocument 클래스를 사용하여 서버의 문서 관리](../vsto/managing-documents-on-a-server-by-using-the-serverdocument-class.md)   
 [방법: 문서에 관리 코드 확장 연결](../vsto/how-to-attach-managed-code-extensions-to-documents.md)  
  
  
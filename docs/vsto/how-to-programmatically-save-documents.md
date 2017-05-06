---
title: "방법: 프로그래밍 방식으로 문서 저장"
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
  - "문서[Visual Studio에서 Office 개발], 저장"
  - "Word[Visual Studio에서 Office 개발], 문서 저장"
ms.assetid: a6225ae9-94f5-421a-9860-5299002d543d
caps.latest.revision: 44
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 43
---
# 방법: 프로그래밍 방식으로 문서 저장
  Microsoft Office Word 문서는 여러 가지 방법으로 저장할 수 있습니다.  문서의 이름을 변경하지 않고 저장하거나 문서를 새 이름으로 저장할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 이름을 변경하지 않고 문서 저장  
  
#### 문서 수준 사용자 지정에 연결된 문서를 저장하려면  
  
1.  <xref:Microsoft.Office.Tools.Word.Document> 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Save%2A> 메서드를 호출합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 이 코드 예제를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#7](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#7)]
     [!code-vb[Trin_VstcoreWordAutomation#7](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#7)]  
  
#### 활성 문서를 저장하려면  
  
1.  활성 문서에 대해 <xref:Microsoft.Office.Interop.Word._Document.Save%2A> 메서드를 호출합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 코드를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#8](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#8)]
     [!code-vb[Trin_VstcoreWordAutomation#8](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#8)]  
  
 저장하려는 문서가 활성 문서인지 확실하지 않은 경우에는 문서의 이름을 지정합니다.  
  
#### 이름을 지정하여 특정 문서를 저장하려면  
  
1.  문서 이름을 <xref:Microsoft.Office.Interop.Word.Documents> 컬렉션에 대한 인수로 사용합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 코드를 실행하십시오.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#9](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#9)]
     [!code-vb[Trin_VstcoreWordAutomation#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#9)]  
  
## 새 이름으로 문서 저장  
 문서를 새 이름으로 저장하려면 SaveAs 메서드를 사용합니다.  <xref:Microsoft.Office.Tools.Word.Document> 호스트 항목\(문서 수준 Word 프로젝트의 경우\) 또는 네이티브 <xref:Microsoft.Office.Interop.Word.Document> 개체\(모든 Word 프로젝트의 경우\)의 이 메서드를 사용할 수 있습니다.  이 메서드를 사용하려면 새 파일 이름을 지정해야 하지만 나머지 인수는 선택적입니다.  
  
> [!NOTE]  
>  `ThisDocument`의 <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentBeforeSave> 이벤트 처리기 안에 **다른 이름으로 저장** 대화 상자를 표시하고 *Cancel* 매개 변수를 **false**로 설정하면 응용 프로그램이 예기치 않게 종료될 수 있습니다.  *Cancel* 매개 변수를 **true**로 설정하면 자동 저장 기능이 비활성화되었음을 나타내는 오류 메시지가 표시됩니다.  
  
#### 문서 수준 사용자 지정에 연결된 문서를 새 이름으로 저장하려면  
  
1.  정규화된 경로와 파일 이름을 사용하여 프로젝트에 사용된 `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 메서드를 호출합니다.  지정한 폴더에 동일한 이름의 파일이 이미 있으면 자동으로 덮어씁니다.  이 코드 예제를 사용하려면 `ThisDocument` 클래스에서 코드를 실행합니다.  
  
    > [!NOTE]  
    >  대상 디렉터리가 없거나 다른 문제로 인해 파일을 저장할 수 없으면 <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 메서드에서 예외가 throw됩니다.  <xref:Microsoft.Office.Tools.Word.Document.SaveAs%2A> 메서드 주변이나 호출 메서드 내에서 **try…catch** 블록을 사용하는 것이 좋습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#10)]
     [!code-vb[Trin_VstcoreWordAutomation#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#10)]  
  
#### 네이티브 문서를 새 이름으로 저장하려면  
  
1.  정규화된 경로와 파일 이름을 사용하여 저장할 <xref:Microsoft.Office.Interop.Word.Document>의 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 메서드를 호출합니다.  지정한 폴더에 동일한 이름의 파일이 이미 있으면 자동으로 덮어씁니다.  
  
     다음 코드 예제에서는 활성 문서를 새 이름으로 저장합니다.  이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 코드를 실행하십시오.  
  
    > [!NOTE]  
    >  대상 디렉터리가 없거나 다른 문제로 인해 파일을 저장할 수 없으면 <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 메서드에서 예외가 throw됩니다.  <xref:Microsoft.Office.Interop.Word._Document.SaveAs%2A> 메서드 주변이나 호출 메서드 내에서 **try…catch** 블록을 사용하는 것이 좋습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#10)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#10)]  
  
## 코드 컴파일  
 이 코드 예제를 실행하려면 다음이 필요합니다.  
  
-   기존 이름으로 문서를 저장하려면 C 드라이브의 Test라는 디렉터리에 NewDocument.doc라는 문서가 있어야 합니다.  
  
-   새 이름으로 문서를 저장하려면 C 드라이브에 Test라는 디렉터리가 있어야 합니다.  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 문서 닫기](../vsto/how-to-programmatically-close-documents.md)   
 [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)   
 [문서 호스트 항목](../vsto/document-host-item.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  
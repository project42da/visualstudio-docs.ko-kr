---
title: "방법: 프로그래밍 방식으로 문서 닫기 | Microsoft Docs"
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
  - "문서[Visual Studio에서 Office 개발], 닫기"
  - "Word[Visual Studio에서 Office 개발], 문서 닫기"
ms.assetid: d5bee1dc-63d1-4307-828f-b7b077e20fb9
caps.latest.revision: 55
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 54
---
# 방법: 프로그래밍 방식으로 문서 닫기
  활성 문서를 닫거나 닫을 문서를 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 활성 문서 닫기  
 활성 문서를 닫는 절차에는 문서 수준 사용자 지정 및 VSTO 추가 기능에 대해 각각 하나씩, 두 가지가 있습니다.  
  
#### 문서 수준 사용자 지정에서 활성 문서를 닫으려면  
  
1.  프로젝트에서 `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.Document.Close%2A> 메서드를 호출하여 사용자 지정과 연결된 문서를 닫습니다. 다음 코드 예제를 사용하려면 `ThisDocument` 클래스에서 실행합니다.  
  
    > [!NOTE]  
    >  이 예제에서는 <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> 값을 *SaveChanges* 매개 변수에 전달하여 변경 내용을 저장하거나 사용자에게 메시지를 표시하지 않고 닫습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#3)]
     [!code-vb[Trin_VstcoreWordAutomation#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#3)]  
  
#### VSTO 추가 기능에서 활성 문서를 닫으려면  
  
1.  <xref:Microsoft.Office.Interop.Word._Application.ActiveDocument%2A> 속성의 <xref:Microsoft.Office.Interop.Word._Document.Close%2A> 메서드를 호출하여 활성 문서를 닫습니다. 다음 코드 예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  
  
    > [!NOTE]  
    >  이 예제에서는 <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> 값을 *SaveChanges* 매개 변수에 전달하여 변경 내용을 저장하거나 사용자에게 메시지를 표시하지 않고 닫습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#3)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#3](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#3)]  
  
## 이름으로 지정한 문서 닫기  
 이름으로 지정한 문서를 닫는 방법은 VSTO 추가 기능과 문서 수준 사용자 지정에서 동일합니다.  
  
#### 이름으로 지정한 문서를 닫으려면  
  
1.  <xref:Microsoft.Office.Interop.Word._Application.Documents%2A> 컬렉션에 대한 인수로 문서 이름을 지정하고 <xref:Microsoft.Office.Interop.Word._Document.Close%2A> 메서드를 호출합니다. 다음 코드 예제에서는 **NewDocument**라는 문서가 Word에서 열려 있다고 가정합니다.  
  
    > [!NOTE]  
    >  이 예제에서는 <xref:Microsoft.Office.Interop.Word.WdSaveOptions.wdDoNotSaveChanges> 값을 *SaveChanges* 매개 변수에 전달하여 변경 내용을 저장하거나 사용자에게 메시지를 표시하지 않고 닫습니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#4)]
     [!code-vb[Trin_VstcoreWordAutomation#4](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#4)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 기존 문서 열기](../vsto/how-to-programmatically-open-existing-documents.md)   
 [방법: 프로그래밍 방식으로 문서 저장](../vsto/how-to-programmatically-save-documents.md)   
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  
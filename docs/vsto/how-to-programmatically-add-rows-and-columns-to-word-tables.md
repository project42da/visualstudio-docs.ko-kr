---
title: "방법: 프로그래밍 방식으로 Word 표에 행 및 열 추가"
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
  - "열[Visual Studio에서 Office 개발], Word 표에 추가"
  - "행[Visual Studio에서 Office 개발], Word 표에 추가"
  - "표[Visual Studio에서 Office 개발], 행 및 열 추가"
ms.assetid: 01a9b6ca-1373-4a6e-b9e6-2225a1321daf
caps.latest.revision: 42
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 41
---
# 방법: 프로그래밍 방식으로 Word 표에 행 및 열 추가
  Microsoft Office Word 표에서 셀은 행과 열로 구성됩니다.  <xref:Microsoft.Office.Interop.Word.Rows> 개체의 <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 메서드를 사용하여 표에 행을 추가하고, <xref:Microsoft.Office.Interop.Word.Columns> 개체의 <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 메서드를 사용하여 열을 추가할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
## 문서 수준 사용자 지정 예제  
 다음 코드 예제는 문서 수준 사용자 지정에서 사용할 수 있습니다.  이러한 예제를 사용하려면 프로젝트의 `ThisDocument` 클래스에서 실행합니다.  이 예제에서는 사용자 지정과 연결된 문서에 하나 이상의 표가 이미 있다고 가정합니다.  
  
> [!IMPORTANT]  
>  이 코드는 다음 프로젝트 템플릿 중 하나를 사용하여 만든 프로젝트에서만 실행됩니다.  
>   
>  -   Word 2013 문서  
> -   Word 2013 서식 파일  
> -   Word 2010 문서  
> -   Word 2010 서식 파일  
>   
>  다른 형식의 프로젝트에서 이 작업을 수행하려는 경우 **Microsoft.Office.Interop.Word** 어셈블리에 대한 참조를 추가해야 하며, 해당 어셈블리의 클래스를 사용하여 표에 행과 열을 추가해야 합니다.  자세한 내용은 [방법: 주 Interop 어셈블리를 통한 Office 응용 프로그램 대상 선택](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) 및 [Word 2010 주 Interop 어셈블리 참조](http://go.microsoft.com/fwlink/?LinkId=189588)\(영문\)를 참조하세요.  
  
#### 표에 행을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 메서드를 사용하여 표에 행을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#95](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#95)]
     [!code-vb[Trin_VstcoreWordAutomation#95](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#95)]  
  
#### 표에 열을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 메서드를 사용한 다음 <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> 메서드를 사용하여 모든 열 너비를 동일하게 만듭니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomation#96](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#96)]
     [!code-vb[Trin_VstcoreWordAutomation#96](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#96)]  
  
## VSTO 추가 기능 예제  
 다음 코드 예제는 VSTO 추가 기능에서 사용할 수 있습니다.  예제를 사용하려면 프로젝트의 `ThisAddIn` 클래스에서 실행합니다.  이 예제에서는 활성 문서에 하나 이상의 표가 이미 있다고 가정합니다.  
  
> [!IMPORTANT]  
>  이 코드는 Word VSTO 추가 기능 템플릿을 사용하여 만든 프로젝트에서만 실행됩니다.  
>   
>  다른 형식의 프로젝트에서 이 작업을 수행하려는 경우 **Microsoft.Office.Interop.Word** 어셈블리에 대한 참조를 추가해야 하며, 해당 어셈블리의 클래스를 사용하여 표에 행과 열을 추가해야 합니다.  자세한 내용은 [방법: 주 Interop 어셈블리를 통한 Office 응용 프로그램 대상 선택](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) 및 [Word 2010 주 Interop 어셈블리 참조](http://go.microsoft.com/fwlink/?LinkId=189588)\(영문\)를 참조하세요.  
  
#### 표에 행을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Rows.Add%2A> 메서드를 사용하여 표에 행을 추가합니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#95](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#95)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#95](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#95)]  
  
#### 표에 열을 추가하려면  
  
1.  <xref:Microsoft.Office.Interop.Word.Columns.Add%2A> 메서드를 사용한 다음 <xref:Microsoft.Office.Interop.Word.Columns.DistributeWidth%2A> 메서드를 사용하여 모든 열 너비를 동일하게 만듭니다.  
  
     [!code-csharp[Trin_VstcoreWordAutomationAddIn#96](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/CS/ThisAddIn.cs#96)]
     [!code-vb[Trin_VstcoreWordAutomationAddIn#96](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomationAddIn/VB/ThisAddIn.vb#96)]  
  
## 참고 항목  
 [방법: 프로그래밍 방식으로 Word 표 만들기](../vsto/how-to-programmatically-create-word-tables.md)   
 [방법: 프로그래밍 방식으로 Word 표의 셀에 텍스트 및 서식 추가](../vsto/how-to-programmatically-add-text-and-formatting-to-cells-in-word-tables.md)   
 [방법: 프로그래밍 방식으로 문서 속성을 사용하여 Word 표 채우기](../vsto/how-to-programmatically-populate-word-tables-with-document-properties.md)  
  
  
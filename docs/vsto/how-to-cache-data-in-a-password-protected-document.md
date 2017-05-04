---
title: "방법: 암호로 보호된 문서의 데이터 캐시 | Microsoft Docs"
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
  - "데이터[Visual Studio에서 Office 개발], 캐싱"
  - "데이터 캐싱[Visual Studio에서 Office 개발], 보호된 문서"
  - "데이터 집합[Visual Studio에서 Office 개발], 캐싱"
ms.assetid: 91b865fc-bd01-438f-ac63-2fe3175bc2e8
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 23
---
# 방법: 암호로 보호된 문서의 데이터 캐시
  암호로 보호된 문서나 통합 문서에서 데이터 캐시에 개체를 추가하면 캐시된 데이터에 대한 변경 내용이 자동으로 저장되지 않습니다.  프로젝트에서 두 개의 메서드를 재정의하여 캐시된 데이터에 대한 변경 내용을 저장할 수 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## Word 문서에서 캐싱  
  
#### 암호로 보호된 Word 문서에서 데이터를 캐시하려면  
  
1.  `ThisDocument` 클래스에서 공용 필드 또는 속성을 캐시하도록 표시합니다.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
2.  `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> 메서드를 재정의하고 문서의 보호를 해제합니다.  
  
     문서가 저장되면 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 이 메서드를 호출하여 문서의 보호를 해제할 수 있게 해 줍니다.  이를 통해 캐시된 데이터의 변경 사항을 저장할 수 있습니다.  
  
3.  `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> 메서드를 재정의하고 문서에 보호를 다시 적용합니다.  
  
     문서가 저장된 후 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 이 메서드를 호출하여 문서에 보호를 다시 적용할 수 있게 해 줍니다.  
  
### 예제  
 다음 코드 예제에서는 암호로 보호된 Word 문서에서 데이터를 캐시하는 방법을 보여 줍니다.  이 코드에서는 <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> 메서드를 통해 보호를 해제하기 전에 현재 <xref:Microsoft.Office.Tools.Word.Document.ProtectionType%2A> 값을 저장하므로 <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> 메서드에서 동일한 형식의 보호를 다시 적용할 수 있습니다.  
  
 [!code-csharp[Trin_CachedDataProtectedDocument#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_CachedDataProtectedDocument/CS/ThisDocument.cs#1)]
 [!code-vb[Trin_CachedDataProtectedDocument#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_CachedDataProtectedDocument/VB/ThisDocument.vb#1)]  
  
### 코드 컴파일  
 프로젝트의 `ThisDocument` 클래스에 이 코드를 추가합니다.  이 코드에서는 암호가 `securelyStoredPassword`라는 필드에 저장되어 있다고 가정합니다.  
  
## Excel 통합 문서에서 캐싱  
 Excel 프로젝트에서는 <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> 메서드를 사용하여 통합 문서 전체를 암호로 보호할 경우에만 이 절차가 필요합니다.  <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> 메서드를 사용하여 특정 워크시트만 암호로 보호하려는 경우에는 이 절차가 필요하지 않습니다.  
  
#### 암호로 보호된 Excel 통합 문서에서 데이터를 캐시하려면  
  
1.  `ThisWorkbook` 클래스나 `Sheet`*n* 클래스 중 하나에서 공용 필드 또는 속성을 캐시하도록 표시합니다.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
2.  `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> 메서드를 재정의하고 통합 문서의 보호를 해제합니다.  
  
     통합 문서가 저장되면 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 이 메서드를 호출하여 통합 문서의 보호를 해제할 수 있게 해 줍니다.  이를 통해 캐시된 데이터의 변경 사항을 저장할 수 있습니다.  
  
3.  `ThisWorkbook` 클래스의 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> 메서드를 재정의하고 문서에 보호를 다시 적용합니다.  
  
     통합 문서가 저장된 후 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 이 메서드를 호출하여 통합 문서에 보호를 다시 적용할 수 있게 해 줍니다.  
  
### 예제  
 다음 코드 예제에서는 암호로 보호된 Excel 통합 문서에서 데이터를 캐시하는 방법을 보여 줍니다.  이 코드에서는 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> 메서드를 통해 보호를 해제하기 전에 현재 <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectStructure%2A> 및 <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectWindows%2A> 값을 저장하므로 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> 메서드에서 동일한 형식의 보호를 다시 적용할 수 있습니다.  
  
 [!code-csharp[Trin_CachedDataProtectedWorkbook#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_CachedDataProtectedWorkbook/CS/ThisWorkbook.cs#1)]
 [!code-vb[Trin_CachedDataProtectedWorkbook#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_CachedDataProtectedWorkbook/VB/ThisWorkbook.vb#1)]  
  
### 코드 컴파일  
 프로젝트의 `ThisWorkbook` 클래스에 이 코드를 추가합니다.  이 코드에서는 암호가 `securelyStoredPassword`라는 필드에 저장되어 있다고 가정합니다.  
  
## 참고 항목  
 [데이터 캐싱](../vsto/caching-data.md)   
 [방법: 오프라인이나 서버에서 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [방법: Office 문서에서 프로그래밍 방식으로 데이터 소스 캐싱](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)  
  
  
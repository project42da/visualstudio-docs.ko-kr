---
title: "방법: 암호로 보호 된 문서에서 데이터를 캐시 | Microsoft Docs"
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
- data caching [Office development in Visual Studio], protected documents
- datasets [Office development in Visual Studio], caching
- data [Office development in Visual Studio], caching
ms.assetid: 91b865fc-bd01-438f-ac63-2fe3175bc2e8
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: ecc4913d9d508d95347945b8f4aaa816bc3d510c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-cache-data-in-a-password-protected-document"></a>방법: 암호로 보호된 문서의 데이터 캐시
  문서 또는 통합 문서는 암호로 보호 되는 데이터 캐시에 데이터를 추가 하는 경우 캐시 된 데이터의 변경 내용은 자동으로 저장 되지 않습니다. 프로젝트에서 두 개의 메서드를 재정의 하 여 캐시 된 데이터 변경 내용을 저장할 수 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="caching-in-word-documents"></a>Word 문서에서 캐싱  
  
#### <a name="to-cache-data-in-a-word-document-that-is-protected-with-a-password"></a>암호로 보호 되는 Word 문서에 데이터를 캐시  
  
1.  에 `ThisDocument` 클래스, 공용 필드 또는 속성을 캐시 하도록 표시 합니다. 자세한 내용은 [Caching Data](../vsto/caching-data.md)을 참조하세요.  
  
2.  재정의 <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> 에서 메서드는 `ThisDocument` 클래스 및 문서에서 보호를 제거 합니다.  
  
     문서를 저장 하는 경우는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 문서 보호를 해제 하는 기회를 제공 하려면이 메서드를 호출 합니다. 이 캐시 된 데이터를 저장 하는 변경할 수 있습니다.  
  
3.  재정의 <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> 에서 메서드는 `ThisDocument` 클래스 및 문서 보호를 다시 적용 합니다.  
  
     문서를 저장 한 후의 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 문서에 보호를 적용할 수 있는 옵션을 제공 하려면이 메서드를 호출 합니다.  
  
### <a name="example"></a>예  
 다음 코드 예제는 암호로 보호 되는 Word 문서에서 데이터를 캐시 하는 방법을 보여 줍니다. 코드에서 보호를 제거 하기 전에 <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> 메서드를 현재 저장 <xref:Microsoft.Office.Tools.Word.Document.ProtectionType%2A> 값을 동일한 형식의 보호에 다시 적용할 수 있도록는 <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> 메서드.  
  
 [!code-csharp[Trin_CachedDataProtectedDocument#1](../vsto/codesnippet/CSharp/Trin_CachedDataProtectedDocument/ThisDocument.cs#1)]
 [!code-vb[Trin_CachedDataProtectedDocument#1](../vsto/codesnippet/VisualBasic/Trin_CachedDataProtectedDocument/ThisDocument.vb#1)]  
  
### <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 추가 하 고 `ThisDocument` 프로젝트의에서 클래스. 이 코드 라는 필드에 암호가 저장 되어 있다고 가정 `securelyStoredPassword`합니다.  
  
## <a name="caching-in-excel-workbooks"></a>Excel 통합 문서에서 캐싱  
 Excel 프로젝트에는이 절차가 필요를 사용 하 여 암호를 가진 전체 통합 문서를 보호 하는 경우에는 <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> 메서드. 이 절차를 사용 하 여 특정 워크시트를 암호로 보호 하는 경우에 필요 하지 않습니다는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> 메서드.  
  
#### <a name="to-cache-data-in-an-excel-workbook-that-is-protected-with-a-password"></a>암호로 보호 되는 Excel 통합 문서에 데이터를 캐시  
  
1.  에 `ThisWorkbook` 클래스 또는 중 하나는 `Sheet`  *n*  클래스, 공용 필드 또는 속성을 캐시 하도록 표시 합니다. 자세한 내용은 [Caching Data](../vsto/caching-data.md)을 참조하세요.  
  
2.  재정의 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> 에서 메서드는 `ThisWorkbook` 클래스 및 통합 문서에서 보호를 제거 합니다.  
  
     통합 문서가 저장 되는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 통합 문서 보호를 해제 하는 기회를 제공 하려면이 메서드를 호출 합니다. 이 캐시 된 데이터를 저장 하는 변경할 수 있습니다.  
  
3.  재정의 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> 에서 메서드는 `ThisWorkbook` 클래스 및 문서 보호를 다시 적용 합니다.  
  
     통합 문서를 저장 한 후의 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 통합 문서에 대 한 보호를 적용할 수 있는 옵션을 제공 하려면이 메서드를 호출 합니다.  
  
### <a name="example"></a>예  
 다음 코드 예제는 암호로 보호 되는 Excel 통합 문서의 데이터를 캐시 하는 방법을 보여 줍니다. 코드에서 보호를 제거 하기 전에 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> 메서드를 현재 저장 <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectStructure%2A> 및 <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectWindows%2A> 값에 다시 같은 보호 유형을 적용할 수 있도록는 <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> 메서드.  
  
 [!code-vb[Trin_CachedDataProtectedWorkbook#1](../vsto/codesnippet/VisualBasic/Trin_CachedDataProtectedWorkbook/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_CachedDataProtectedWorkbook#1](../vsto/codesnippet/CSharp/Trin_CachedDataProtectedWorkbook/ThisWorkbook.cs#1)]  
  
### <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 추가 하 고 `ThisWorkbook` 프로젝트의에서 클래스. 이 코드 라는 필드에 암호가 저장 되어 있다고 가정 `securelyStoredPassword`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 캐싱](../vsto/caching-data.md)   
 [방법: 오프 라인 상태가 되거나 서버에 사용할 데이터 캐싱](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)   
 [방법: Office 문서에서 프로그래밍 방식으로 데이터 원본 캐시](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)  
  
  
---
title: "방법: 프로그래밍 방식으로 통합 문서에서 워크시트 삭제 | Microsoft Docs"
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
  - "통합 문서, 워크시트 삭제"
  - "워크시트, 제거"
ms.assetid: c5ae99f0-806d-4320-a29c-75ad444fb996
caps.latest.revision: 48
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 47
---
# 방법: 프로그래밍 방식으로 통합 문서에서 워크시트 삭제
  통합 문서의 모든 워크시트를 삭제할 수 있습니다.  워크시트를 삭제하려면 워크시트 호스트 항목을 사용하거나 통합 문서의 시트 컬렉션을 통해 워크시트에 액세스합니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## 워크시트 호스트 항목 사용  
 문서 수준 사용자 지정에서 디자인 타임에 워크시트가 추가된 경우 <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A> 메서드를 사용하여 지정된 워크시트를 삭제합니다.  다음 코드는 워크시트 호스트 항목을 직접 참조하여 통합 문서에서 워크시트를 삭제합니다.  
  
> [!IMPORTANT]  
>  이 코드는 다음 프로젝트 템플릿 중 하나를 사용하여 만든 프로젝트에서만 실행됩니다.  
>   
>  -   Excel 2013 통합 문서  
> -   Excel 2013 서식 파일  
> -   Excel 2010 통합 문서  
> -   Excel 2010 서식 파일  
>   
>  다른 형식의 프로젝트에서 이 작업을 수행하려는 경우 **Microsoft.Office.Interop.Excel** 어셈블리에 대한 참조를 추가해야 하며, 해당 어셈블리의 클래스를 사용하여 통합 문서를 열고 워크시트를 삭제해야 합니다.  자세한 내용은 [방법: 주 Interop 어셈블리를 통한 Office 응용 프로그램 대상 선택](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) 및 [Excel 2010 주 Interop 어셈블리 참조](http://go.microsoft.com/fwlink/?LinkId=189585)\(영문\)를 참조하세요.  
  
#### 워크시트 호스트 항목을 사용하여 워크시트를 삭제하려면  
  
1.  <xref:Microsoft.Office.Tools.Excel.Worksheet.Delete%2A>의 `Sheet1` 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#17](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#17)]
     [!code-vb[Trin_VstcoreExcelAutomation#17](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#17)]  
  
## Excel 통합 문서의 시트 컬렉션 사용  
 다음과 같은 경우 Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Sheets> 컬렉션을 통해 워크시트에 액세스합니다.  
  
-   VSTO 추가 기능에서 워크시트를 삭제하려고 합니다.  
  
-   삭제하려는 워크시트는 문서 수준 사용자 지정에서 런타임에 생성되었습니다.  
  
 다음 코드는 **Sheets** 컬렉션의 인덱스 번호를 통해 시트를 참조하여 통합 문서에서 워크시트를 삭제합니다.  이 코드에서는 새 워크시트가 프로그래밍 방식으로 생성되었다고 가정합니다.  
  
> [!IMPORTANT]  
>  다른 형식의 프로젝트에서 이 작업을 수행하려는 경우 **Microsoft.Office.Interop.Excel** 어셈블리에 대한 참조를 추가해야 하며, 해당 어셈블리의 클래스를 사용하여 통합 문서를 열고 워크시트를 삭제해야 합니다.  자세한 내용은 [방법: 주 Interop 어셈블리를 통한 Office 응용 프로그램 대상 선택](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md) 및 [Excel 2010 주 Interop 어셈블리 참조](http://go.microsoft.com/fwlink/?LinkId=189585)\(영문\)를 참조하세요.  
  
#### Excel 통합 문서의 시트 컬렉션을 사용하여 워크시트를 삭제하려면  
  
1.  <xref:Microsoft.Office.Interop.Excel.Sheets> 컬렉션의 <xref:Microsoft.Office.Interop.Excel._Worksheet.Delete%2A> 메서드를 호출합니다.  
  
     [!code-csharp[Trin_VstcoreExcelAutomation#18](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/CS/Sheet1.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomation#18](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreExcelAutomation/VB/Sheet1.vb#18)]  
  
## 참고 항목  
 [워크시트 작업](../vsto/working-with-worksheets.md)   
 [방법: 프로그래밍 방식으로 워크시트 숨기기](../vsto/how-to-programmatically-hide-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서 내에서 워크시트 이동](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)   
 [방법: 프로그래밍 방식으로 워크시트 선택](../vsto/how-to-programmatically-select-worksheets.md)   
 [방법: 프로그래밍 방식으로 통합 문서에 새 워크시트 추가](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md)   
 [워크시트 호스트 항목](../vsto/worksheet-host-item.md)   
 [Office 프로젝트의 개체에 전역 액세스](../vsto/global-access-to-objects-in-office-projects.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  
---
title: "Office 솔루션에서 런타임에 바인딩 | Microsoft Docs"
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
  - "개체[Office Development in Visual Studio], 캐스팅"
  - "형식[Visual Studio에서 Office 개발], 캐스팅"
  - "자동화[Visual Studio에서 Office 개발], 개체 캐스팅"
  - "캐스팅, 개체를 특정 형식으로"
ms.assetid: 80b0d23e-df68-4ea9-a02b-238aee8ca9c0
caps.latest.revision: 49
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 48
---
# Office 솔루션에서 런타임에 바인딩
  Office 응용 프로그램의 개체 모델에 있는 일부 형식은 런타임에 바인딩 기능을 통해 사용할 수 있는 기능을 제공합니다.  예를 들어, 일부 메서드와 속성은 Office 응용 프로그램의 컨텍스트에 따라 다른 형식의 개체를 반환할 수 있으며 일부 형식은 컨텍스트에 따라 다른 메서드나 속성을 노출할 수도 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Visual Basic 프로젝트나 **Option Strict** 해제 하 고 C\# 프로젝트 대상으로 하는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] 이러한 런타임에 바인딩 기능을 사용 하는 형식에 직접 작업할 수 있습니다.  
  
## 개체 반환 값의 암시적 및 명시적 캐스팅  
 Microsoft Office PIA\(주 interop 어셈블리\)의 많은 메서드 및 속성은 몇 가지 형식의 개체를 반환할 수 있기 때문에 <xref:System.Object> 값을 반환합니다.  예를 들어, <xref:Microsoft.Office.Tools.Excel.Workbook.ActiveSheet%2A> 속성은 해당 반환 값이 활성 시트에 따라 <xref:Microsoft.Office.Interop.Excel.Worksheet> 또는 <xref:Microsoft.Office.Interop.Excel.Chart> 개체일 수 있기 때문에 <xref:System.Object>를 반환합니다.  
  
 메서드나 속성이 반환 하는 경우는 <xref:System.Object>를 명시적으로 \(Visual Basic\)에서 개체를 올바른 형식 Visual Basic 프로젝트에서 변환 해야 위치 **Option Strict** 에.  명시적으로 캐스팅할 필요가 없습니다 <xref:System.Object> 반환 값을 Visual Basic 프로젝트에서 위치 **Option Strict** 꺼져 있습니다.  
  
 대부분의 경우 참조 문서에 <xref:System.Object>를 반환하는 멤버에 대한 가능한 반환 값의 형식이 나와 있습니다.  개체를 변환하거나 캐스팅하면 코드 편집기에서 해당 개체에 대한 IntelliSense를 사용할 수 있습니다.  
  
 Visual Basic에서의 변환에 대한 자세한 내용은 [Implicit and Explicit Conversions &#40;Visual Basic&#41;](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions) 및 [CType 함수&#40;Visual Basic&#41;](/dotnet/visual-basic/language-reference/functions/ctype-function)를 참조하십시오.  
  
### 예제  
 다음 코드 예제에서는 Visual Basic 프로젝트의 개체를 특정 형식으로 캐스팅 하는 방법을 보여 줍니다. 여기서 **Option Strict** 에 있습니다.  이 프로젝트 형식에 명시적으로 캐스팅 해야는 <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Cells%2A> 속성에는 <xref:Microsoft.Office.Interop.Excel.Range>.  이 예제를 실행하려면 `Sheet1`이라는 워크시트 클래스가 포함된 문서 수준 Excel 프로젝트가 있어야 합니다.  
  
 [!code-vb[Trin_VstcoreProgramming#9](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/VB/Sheet1.vb#9)]  
  
 다음 코드 예제에서는 **Option Strict**가 해제된 Visual Basic 프로젝트와 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]를 대상으로 하는 Visual C\# 프로젝트에서 특정 형식으로 개체를 암시적으로 캐스팅하는 방법을 보여 줍니다.  이러한 형식의 프로젝트에서는 <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Cells%2A> 속성이 <xref:Microsoft.Office.Interop.Excel.Range>로 암시적으로 캐스팅됩니다.  이 예제를 실행하려면 `Sheet1`이라는 워크시트 클래스가 포함된 문서 수준 Excel 프로젝트가 있어야 합니다.  
  
 [!code-csharp[Trin_VstcoreProgramming#10](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/CS/Sheet1.cs#10)]
 [!code-vb[Trin_VstcoreProgramming#10](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgramming/VB/Sheet1.vb#10)]  
  
## 런타임에 바인딩을 통해서만 사용할 수 있는 멤버 액세스  
 Office PIA의 일부 속성과 메서드는 런타임에 바인딩을 통해서만 사용할 수 있습니다.  Visual Basic 프로젝트 위치 **Option Strict** 꺼져 있거나 C\# 프로젝트를 대상으로는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 또는 [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], 런타임에 바인딩되는 멤버에 액세스 하려면 이러한 언어의 런타임에 바인딩 기능 사용할 수 있습니다.  Visual Basic 프로젝트 위치 **Option Strict** 켜져 있어야 리플렉션을 사용 하 여 이러한 멤버에 액세스할 수 있습니다.  
  
### 예제  
 다음 코드 예제에서는 **Option Strict**가 해제된 Visual Basic 프로젝트나 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]를 대상으로 하는 Visual C\# 프로젝트에서 런타임에 바인딩되는 멤버에 액세스하는 방법을 보여 줍니다.  이 예제에서는 Word에 있는 **파일 열기** 대화 상자의 런타임에 바인딩되는 **Name** 속성에 액세스합니다.  이 예제를 사용하려면 Word 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 이 예제를 실행하십시오.  
  
 [!code-csharp[Trin_VstcoreWordAutomation#122](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/CS/ThisDocument.cs#122)]
 [!code-vb[Trin_VstcoreWordAutomation#122](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#122)]  
  
 다음 코드 예제에서는 리플렉션을 사용 하 여 Visual Basic 프로젝트에서의 동일한 작업을 수행 하는 방법을 보여 줍니다. 여기서 **Option Strict** 에 있습니다.  
  
 [!code-vb[Trin_VstcoreWordAutomation#102](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreWordAutomation/VB/ThisDocument.vb#102)]  
  
## 참고 항목  
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)   
 [dynamic 형식 사용&#40;C&#35; 프로그래밍 가이드&#41;](/dotnet/csharp/programming-guide/types/using-type-dynamic)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [리플렉션&#40;C&#35; 및 Visual Basic&#41;](../Topic/Reflection%20(C%23%20and%20Visual%20Basic).md)   
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)  
  
  
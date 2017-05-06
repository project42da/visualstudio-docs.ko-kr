---
title: "Office 솔루션의 선택적 매개 변수"
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
  - "응용 프로그램 개발[Visual Studio에서 Office 개발], 선택적 매개 변수"
  - "누락된 필드[Visual Studio에서 Office 개발]"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 선택적 매개 변수"
  - "선택적 매개 변수[Visual Studio에서 Office 개발]"
  - "매개 변수[Visual Studio에서 Office 개발], 선택적"
  - "Visual Basic[Visual Studio에서 Office 개발], 선택적 매개 변수"
  - "Visual C#[Visual Studio에서 Office 개발], 선택적 매개 변수"
ms.assetid: 109eaef6-08bb-4b59-a29e-921f856027cc
caps.latest.revision: 43
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 42
---
# Office 솔루션의 선택적 매개 변수
  Microsoft Office 응용 프로그램의 개체 모델에 있는 메서드 중 상당수가 선택적 매개 변수를 허용합니다.  Visual Studio에서 Visual Basic을 사용하여 Office 솔루션을 개발하는 경우 없는 매개 변수마다 기본값이 자동으로 사용되기 때문에 선택적 매개 변수의 값을 전달할 필요가 없습니다.  대부분의 경우 Visual C\# 프로젝트에서도 선택적 매개 변수를 생략할 수 있습니다. 그러나 문서 수준 Word 프로젝트에서는 `ThisDocument` 클래스의 선택적 **ref** 매개 변수를 생략할 수 없습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Visual C\# 및 Visual Basic 프로젝트에서 선택적 매개 변수로 작업하는 방법에 대한 자세한 내용은 [명명된 인수와 선택적 인수&#40;C&#35; 프로그래밍 가이드&#41;](/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments) 및 [Optional Parameters &#40;Visual Basic&#41;](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters)를 참조하세요.  
  
> [!NOTE]  
>  이전 버전의 Visual Studio에서는 Visual C\# 프로젝트에서 모든 선택적 매개 변수의 값을 전달해야 합니다.  편의를 위해 이러한 프로젝트에는 매개 변수의 기본값을 사용하려고 할 때 선택적 매개 변수에 전달할 수 있는 `missing`이라는 전역 변수가 포함되어 있습니다.  Visual Studio에서 Office용 Visual C\# 프로젝트에는 여전히 `missing` 변수가 포함되어 있지만 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]에서 Office 솔루션을 개발할 때는 이 변수를 사용할 필요가 없습니다. 단, Word의 문서 수준 프로젝트에 있는 `ThisDocument` 클래스에서 선택적 **ref** 매개 변수를 사용하여 메서드를 호출하는 경우는 예외입니다.  
  
## Excel의 예제  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> 메서드에는 많은 선택적 매개 변수가 있습니다.  다음 코드 예제와 같이 일부 매개 변수에는 값을 지정하고 다른 매개 변수에는 기본값을 적용할 수 있습니다.  이 예제에는 `Sheet1`이라는 워크시트 클래스가 포함된 문서 수준 프로젝트가 필요합니다.  
  
 [!code-csharp[Trin_VstrefGeneralExcel#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstrefGeneralExcel/CS/Sheet1.cs#1)]
 [!code-vb[Trin_VstrefGeneralExcel#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstrefGeneralExcel/VB/Sheet1.vb#1)]  
  
## Word의 예제  
 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드에는 많은 선택적 매개 변수가 있습니다.  다음 코드 예제와 같이 일부 매개 변수에는 값을 지정하고 다른 매개 변수에는 기본값을 적용할 수 있습니다.  
  
 [!code-csharp[Trin_VstrefGeneralWord#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstrefGeneralWord/CS/ThisDocument.cs#1)]
 [!code-vb[Trin_VstrefGeneralWord#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstrefGeneralWord/VB/ThisDocument.vb#1)]  
  
## Word의 Visual C\# 문서 수준 프로젝트에 있는 ThisDocument 클래스에서 메서드의 선택적 매개 변수 사용  
 Word 개체 모델에는 <xref:System.Object> 값을 받아들이는 선택적 **ref** 매개 변수가 있는 많은 메서드가 포함되어 있습니다.  그러나 Word의 Visual C\# 문서 수준 프로젝트에서 생성된 `ThisDocument` 클래스에 대한 메서드의 선택적 **ref** 매개 변수는 생략할 수 없습니다.  Visual C\#에서는 클래스가 아니라 인터페이스의 메서드에서만 선택적 **ref** 매개 변수를 생략할 수 있습니다.  예를 들어 다음 코드 예제는 `ThisDocument` 클래스의 <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> 메서드에서 선택적 **ref** 매개 변수를 생략할 수 없기 때문에 컴파일되지 않습니다.  
  
 [!code-csharp[Trin_VstrefGeneralWord#3](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstrefGeneralWord/CS/ThisDocument.cs#3)]  
  
 `ThisDocument` 클래스의 메서드를 호출하는 경우 다음 지침을 따릅니다.  
  
-   선택적 **ref** 매개 변수의 기본값을 적용하려면 `missing` 변수를 매개 변수에 전달합니다.  `missing` 변수는 자동으로 Visual C\# Office 프로젝트에서 정의되고 생성된 프로젝트 코드에서 <xref:System.Type.Missing> 값에 할당됩니다.  
  
-   선택적 **ref** 매개 변수에 대한 고유 값을 지정하려면 지정하려는 값에 할당된 개체를 선언한 다음 개체를 매개 변수에 전달합니다.  
  
 다음 코드 예제에서는 *ignoreUppercase* 매개 변수의 값을 지정하고 다른 매개 변수에는 기본값을 적용하여 <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> 메서드를 호출하는 방법을 보여 줍니다.  
  
 [!code-csharp[Trin_VstrefGeneralWord#4](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstrefGeneralWord/CS/ThisDocument.cs#4)]  
  
 `ThisDocument` 클래스에 있는 메서드의 선택적 **ref** 매개 변수를 생략하는 코드를 작성하려는 경우 <xref:Microsoft.Office.Tools.Word.Document.InnerObject%2A> 속성이 반환하는 <xref:Microsoft.Office.Interop.Word.Document> 개체에 대해 동일한 메서드를 호출하고 해당 메서드에서 매개 변수를 생략할 수도 있습니다.  이렇게 할 수 있는 이유는 <xref:Microsoft.Office.Interop.Word.Document>가 클래스가 아니라 인터페이스이기 때문입니다.  
  
 [!code-csharp[Trin_VstrefGeneralWord#5](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstrefGeneralWord/CS/ThisDocument.cs#5)]  
  
 값 및 참조 형식 매개 변수에 대한 자세한 내용은 [Passing Arguments by Value and by Reference &#40;Visual Basic&#41;](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference)\(Visual Basic의 경우\) 및 [매개 변수 전달&#40;C&#35; 프로그래밍 가이드&#41;](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)을 참조하세요.  
  
## 참고 항목  
 [Office 솔루션 개발](../vsto/developing-office-solutions.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)  
  
  
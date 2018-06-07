---
title: Office 솔루션의 선택적 매개 변수 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], optional parameters
- Visual C# [Office development in Visual Studio], optional parameters
- Visual Basic [Office development in Visual Studio], optional parameters
- application development [Office development in Visual Studio], optional parameters
- missing field [Office development in Visual Studio]
- optional parameters [Office development in Visual Studio]
- parameters [Office development in Visual Studio], optional
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b03f6112ebf44a89da3b4d5cbf6f7ff23f54b9c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571989"
---
# <a name="optional-parameters-in-office-solutions"></a>Office 솔루션의 선택적 매개 변수
  Microsoft Office 응용 프로그램의 개체 모델에 있는 메서드 중 상당수가 선택적 매개 변수를 허용합니다. Visual Studio에서 Visual Basic을 사용하여 Office 솔루션을 개발하는 경우 없는 매개 변수마다 기본값이 자동으로 사용되기 때문에 선택적 매개 변수의 값을 전달할 필요가 없습니다. 대부분의 경우에서 Visual C# 프로젝트에서 선택적 매개 변수를 생략할 수 있습니다. 그러나 선택적 생략할 수 없습니다 **ref** 의 매개 변수는 `ThisDocument` 문서 수준 Word 프로젝트의 클래스.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Visual C# 및 Visual Basic 프로젝트에서 선택적 매개 변수 사용에 대 한 자세한 내용은 참조 [명명 된 인수와 선택적 인수 &#40;C&#35; 프로그래밍 가이드&#41; ](/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments) 및 [ &#40;Visual Basic&#41;](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters)합니다.  
  
> [!NOTE]  
>  이전 버전의 Visual Studio에서는 Visual C# 프로젝트에서 모든 선택적 매개 변수의 값을 전달해야 합니다. 편의를 위해 이러한 프로젝트에는 매개 변수의 기본값을 사용하려고 할 때 선택적 매개 변수에 전달할 수 있는 `missing`이라는 전역 변수가 포함되어 있습니다. Visual Studio에서 Office 용 visual C# 프로젝트를 계속 포함할는 `missing` 변수를 일반적으로 필요가 없습니다의 Office 솔루션을 개발할 때 사용할 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], 옵션을 사용 하 여 메서드를 호출 하는 경우를 제외 하 고 **ref** 매개 변수는 `ThisDocument` Word 용 문서 수준 프로젝트의 클래스.  
  
## <a name="example-in-excel"></a>Excel의 예제  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> 메서드에는 많은 선택적 매개 변수가 있습니다. 다음 코드 예제와 같이 일부 매개 변수에는 값을 지정하고 다른 매개 변수에는 기본값을 적용할 수 있습니다. 이 예제에는 `Sheet1`이라는 워크시트 클래스가 포함된 문서 수준 프로젝트가 필요합니다.  
  
 [!code-csharp[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/CSharp/excelworkbook1/Sheet1.cs#1)]
 [!code-vb[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/VisualBasic/excelworkbook1/Sheet1.vb#1)]  
  
## <a name="example-in-word"></a>Word의 예제  
 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> 메서드에는 많은 선택적 매개 변수가 있습니다. 다음 코드 예제와 같이 일부 매개 변수에는 값을 지정하고 다른 매개 변수에는 기본값을 적용할 수 있습니다.  
  
 [!code-vb[Trin_VstrefGeneralWord#1](../vsto/codesnippet/VisualBasic/worddocument1/ThisDocument.vb#1)]
 [!code-csharp[Trin_VstrefGeneralWord#1](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#1)]  
  
## <a name="use-optional-parameters-of-methods-in-the-thisdocument-class-in-visual-c-document-level-projects-for-word"></a>Word에 대 한 Visual C# 문서 수준 프로젝트에서 ThisDocument 클래스에서 메서드의 선택적 매개 변수 사용  
 Word 개체 모델에 선택적으로 여러 메서드도 포함 되어 **ref** 허용 하는 매개 변수 <xref:System.Object> 값입니다. 그러나 선택적 생략할 수 없습니다 **ref** 생성 된 메서드의 매개 변수가 `ThisDocument` Word 용 문서 수준 프로젝트는 Visual C#에서 클래스입니다. Visual C#에서는 선택적 생략할 수 **ref** 클래스가 아니라 인터페이스의 메서드에 대해서만 매개 변수입니다. 예를 들어 다음 코드 예제에서는 컴파일되지 않습니다, 선택적으로 생략할 수 있으므로 **ref** 의 매개 변수는 <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> 의 메서드는 `ThisDocument` 클래스입니다.  
  
 [!code-csharp[Trin_VstrefGeneralWord#3](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#3)]  
  
 `ThisDocument` 클래스의 메서드를 호출하는 경우 다음 지침을 따릅니다.  
  
-   옵션의 기본값을 적용 하려면 **ref** 매개 변수, 암호는 `missing` 매개 변수입니다. `missing` 변수는 자동으로 Visual C# Office 프로젝트에서 정의되고 생성된 프로젝트 코드에서 <xref:System.Type.Missing> 값에 할당됩니다.  
  
-   선택 사항에 대 한 사용자가 직접 값을 지정 하려면 **ref** 매개 변수를 지정 하려면 원하는 값에 할당 하는 개체를 선언 하 고 다음 매개 변수에 개체를 전달 합니다.  
  
 다음 코드 예제에서는 호출 하는 방법을 보여 줍니다.는 <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> 에 대 한 값을 지정 하 여 메서드는 *ignoreUppercase* 매개 변수 및 다른 매개 변수에 대해 기본값을 수락 합니다.  
  
 [!code-csharp[Trin_VstrefGeneralWord#4](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#4)]  
  
 옵션을 생략 하는 코드를 작성 하려는 경우 **ref** 에 있는 메서드의 매개 변수는 `ThisDocument` 클래스 또는에서 호출할 수 있습니다 같은 메서드는 <xref:Microsoft.Office.Interop.Word.Document> 에서 반환 된 개체는 <xref:Microsoft.Office.Tools.Word.Document.InnerObject%2A> 속성을 생략 하 고는 해당 메서드의 매개 변수입니다. 이렇게 할 수 있는 이유는 <xref:Microsoft.Office.Interop.Word.Document>가 클래스가 아니라 인터페이스이기 때문입니다.  
  
 [!code-csharp[Trin_VstrefGeneralWord#5](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#5)]  
  
 값 및 참조 형식 매개 변수에 대 한 자세한 내용은 참조 하십시오. [참조 및 값으로 인수 전달 &#40;Visual Basic&#41; ](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference) (Visual Basic의 경우)에 대 한 및 [매개 변수를 전달 &#40;C&#35; 프로그래밍 가이드&#41;](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters)합니다.  
  
## <a name="see-also"></a>참고자료  
 [Office 솔루션 개발](../vsto/developing-office-solutions.md)   
 [Office 솔루션에서 코드 작성](../vsto/writing-code-in-office-solutions.md)  
  
  
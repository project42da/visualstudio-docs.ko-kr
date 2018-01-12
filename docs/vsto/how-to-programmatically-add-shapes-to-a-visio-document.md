---
title: "방법: 프로그래밍 방식으로 Visio 문서에 셰이프를 추가 | Microsoft Docs"
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
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 4d73c59ac9ba89a5814a264bb8e8fe3c83b9789e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>방법: 프로그래밍 방식으로 Visio 문서에 셰이프 추가
  스텐실에서 마스터를 검색하고 활성 페이지로 셰이프를 끌어 놓아 Microsoft Office Visio 문서에 셰이프를 추가할 수 있습니다.  
  
 자세한 내용은 [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) 메서드, [Microsoft.Office.Interop.Visio.Application.ActivePage](http://msdn.microsoft.com/library/office/ff765484.aspx) 속성 및 [Microsoft.Office.Interop.Visio.Page.Drop](http://msdn.microsoft.com/library/office/ff765054.aspx) 메서드에 대한 VBA 참조 설명서를 참조하세요.  
  
## <a name="adding-shapes-to-a-visio-document"></a>Visio 문서에 셰이프 추가  
  
#### <a name="to-add-shapes-to-a-visio-document"></a>Visio 문서를 셰이프를 추가하려면  
  
-   문서를 활성화하고 Documents.Masters 컬렉션에서 마스터를 검색하여 활성 문서에 셰이프를 끌어 놓습니다. 인덱스 또는 마스터 이름을 사용하여 마스터를 검색할 수 있습니다.  
  
     다음 코드 예제에서는 빈 Visio 문서를 만든 다음 **기본 셰이프** 스텐실이 도킹된 상태에서 엽니다. 그러면 코드에서 여러 셰이프를 검색하여 활성 페이지에 끌어 놓습니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [Visio 셰이프 작업](../vsto/working-with-visio-shapes.md)   
 [방법: 프로그래밍 방식으로 Visio 문서에서 셰이프 복사 및 붙여넣기](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  
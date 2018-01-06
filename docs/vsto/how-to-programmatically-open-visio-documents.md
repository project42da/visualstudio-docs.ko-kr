---
title: "방법: 프로그래밍 방식으로 Visio 문서 열기 | Microsoft Docs"
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
- documents [Office development in Visual Studio], opening Visio documents
- Visio [Office development in Visual Studio], opening Visio documents
ms.assetid: bddb820c-bde7-4d21-a0b3-6d1968baccab
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1b2a6c395ed6dbfb8265ac131dd4318b590bf92e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-open-visio-documents"></a>방법: 프로그래밍 방식으로 Visio 문서 열기
  기존 Microsoft Office Visio 문서를 여는 방법은 두 가지가: Open 및 OpenEx 합니다. 인수는 호출자에 게 문서가 하는 방법을 지정할 수 있다는 점을 제외 하 고 OpenEx 방법은 Open 메서드와 동일 합니다.  
  
 개체 모델에 대한 자세한 내용은 VBA 참조 설명서에서 [Microsoft.Office.Interop.Visio.Documents.Open](https://msdn.microsoft.com/library/office/ff765240.aspx) 메서드 및 [Microsoft.Office.Interop.Visio.Documents.OpenEx](https://msdn.microsoft.com/library/office/ff767229.aspx) 메서드를 참조하세요.  
  
## <a name="opening-a-visio-document"></a>Visio 문서 열기  
  
#### <a name="to-open-a-visio-document"></a>Visio 문서를 열려면  
  
-   Microsoft.Office.Interop.Visio.Documents.Open 메서드를 호출 하 고 Visio 문서의 정규화 된 경로 지정 합니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#5)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#5](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#5)]  
  
## <a name="opening-a-visio-document-with-specified-arguments"></a>지정된 인수로 Visio 문서 열기  
  
#### <a name="to-open-a-visio-document-as-read-only-and-docked"></a>Visio 문서를 읽기 전용 및 도킹하여 열려면  
  
-   Microsoft.Office.Interop.Visio.Documents.OpenEx 메서드 호출을 Visio 문서의 정규화 된 경로 입력 하 고, 사용 하려는 인수를 포함 시킬-이 case, 도킹 됨 및 읽기 전용입니다.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#6)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#6](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#6)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   이름이 `myDrawing.vsd` 인 Visio 문서가 내 문서 폴더(Windows XP 및 이전) 또는 문서 폴더(Windows Vista)의 `Test` 디렉터리에 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visio 솔루션](../vsto/visio-solutions.md)   
 [Visio 개체 모델 개요](../vsto/visio-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 새 Visio 문서 만들기](../vsto/how-to-programmatically-create-new-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 닫기](../vsto/how-to-programmatically-close-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 저장](../vsto/how-to-programmatically-save-visio-documents.md)   
 [방법: 프로그래밍 방식으로 Visio 문서 인쇄](../vsto/how-to-programmatically-print-visio-documents.md)  
  
  
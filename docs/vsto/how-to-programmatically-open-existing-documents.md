---
title: '방법: 프로그래밍 방식으로 기존 문서 열기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], opening
- Word [Office development in Visual Studio], opening documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0c7542b2222839afc75b3b5b1b84fc5afe56f523
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-open-existing-documents"></a>방법: 프로그래밍 방식으로 기존 문서 열기
  <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> 정규화 된 경로 파일 이름으로 지정 된 기존 Microsoft Office Word 문서를 엽니다. 이 메서드는 반환 된 <xref:Microsoft.Office.Interop.Word.Document> 열려 있는 문서를 나타내는입니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-open-a-document"></a>문서를 열려면  
  
-   호출 된 <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> 의 메서드는 <xref:Microsoft.Office.Interop.Word.Documents> 수집 및 문서에 경로 제공 합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#5)]
     [!code-csharp[Trin_VstcoreWordAutomation#5](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#5)]  
  
### <a name="to-open-a-document-as-read-only"></a>읽기 전용으로 문서를 열려면  
  
-   호출의 <xref:Microsoft.Office.Interop.Word.Documents.Open%2A> 메서드를 문서에 대 한 경로 입력 하 고 설정는 *ReadOnly* 인수를 **True** 메서드 호출에서.  
  
     [!code-vb[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#6)]
     [!code-csharp[Trin_VstcoreWordAutomation#6](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#6)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드 예제에는 다음이 필요합니다.  
  
-   NewDocument.doc 라는 문서는 C 드라이브에 Test 라는 디렉터리에 있어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 새 문서 만들기](../vsto/how-to-programmatically-create-new-documents.md)   
 [방법: 프로그래밍 방식으로 문서 닫기](../vsto/how-to-programmatically-close-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  
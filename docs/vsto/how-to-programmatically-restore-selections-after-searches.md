---
title: "방법: 프로그래밍 방식으로 검색 후 선택 영역 복원 | Microsoft Docs"
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
- searches, restoring selection after
- documents [Office development in Visual Studio], restoring selections
- selections, restoring after a search
ms.assetid: 1e6131ad-0e5b-4189-be67-5b2ed87d193d
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 84e0a9c18d3af7956c90390e5447011d67369216
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-restore-selections-after-searches"></a>방법: 프로그래밍 방식으로 검색 후 선택 영역 복원
  검색 하 고 문서에서 텍스트를 바꿀 경우 검색이 완료 된 후 사용자의 원래 선택 항목을 복원 해야 할 수 있습니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 예제 프로시저의 코드에서는 두 개의 활용 <xref:Microsoft.Office.Interop.Word.Range> 개체입니다. 현재 저장소 하나 <xref:Microsoft.Office.Interop.Word.Selection>, 하나 검색 범위도 사용할 전체 문서를 가져오거나 설정 합니다.  
  
### <a name="to-restore-the-users-original-selection-after-a-search"></a>검색 한 후 사용자의 원래 선택 항목을 복원 하려면  
  
1.  만들기는 <xref:Microsoft.Office.Interop.Word.Range> 문서 및 현재 선택 영역에 대 한 개체입니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#83)]
     [!code-csharp[Trin_VstcoreWordAutomation#83](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#83)]  
  
2.  검색을 수행 하 고 바꾸기 작업 합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#84)]
     [!code-csharp[Trin_VstcoreWordAutomation#84](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#84)]  
  
3.  사용자의 원래 선택 항목을 복원 하려면 시작 범위를 선택 합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#85)]
     [!code-csharp[Trin_VstcoreWordAutomation#85](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#85)]  
  
 다음 예제에서는 전체 메서드를 보여 줍니다.  
  
## <a name="example"></a>예  
 [!code-vb[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#82)]
 [!code-csharp[Trin_VstcoreWordAutomation#82](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#82)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 검색 하 고 문서에서 텍스트 바꾸기](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md)   
 [방법: 프로그래밍 방식으로 Word에서 검색 옵션 설정](../vsto/how-to-programmatically-set-search-options-in-word.md)   
 [방법: 프로그래밍 방식으로 문서에서 찾은 항목 반복](../vsto/how-to-programmatically-loop-through-found-items-in-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  
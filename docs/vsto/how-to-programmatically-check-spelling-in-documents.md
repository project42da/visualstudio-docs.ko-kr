---
title: "방법: 프로그래밍 방식으로 문서에서 맞춤법 검사 | Microsoft Docs"
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
- documents [Office development in Visual Studio], checking spelling
- spelling checker, documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 357e92235f474392c3bdbe1ac1f19af8c9c1538a
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-check-spelling-in-documents"></a>방법: 프로그래밍 방식으로 문서에서 맞춤법 검사
  사용 하 여 문서에서 맞춤법을 검사 하려면는 <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> 메서드. 이 메서드는 제공 된 매개 변수 철자가 있는지 여부를 나타내는 부울 값을 반환 합니다.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
### <a name="to-check-spelling-and-display-results-in-a-message-box"></a>맞춤법을 검사 하 고 메시지 상자에 결과 표시 하려면  
  
1.  호출 된 <xref:Microsoft.Office.Interop.Word._Application.CheckSpelling%2A> 메서드 맞춤법 오류를 확인 하는 텍스트 범위를 전달 합니다. 이 코드 예제를 사용하려면 프로젝트의 `ThisDocument` 또는 `ThisAddIn` 클래스에서 실행합니다.  
  
     [!code-vb[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#113)]
     [!code-csharp[Trin_VstcoreWordAutomation#113](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#113)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 프로그래밍 방식으로 정의 하 고 문서에서 범위 선택](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  
  
  
---
title: '방법: Outlook에서 양식 영역 표시 하지 않기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], canceling display
- canceling form region display
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a5fffde6cd92d490df2a5567763da77e723ed4f3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-prevent-outlook-from-displaying-a-form-region"></a>방법: Outlook에서 양식 영역 표시하지 않기
  하지 않을 Microsoft Office Outlook 특정 항목에 대 한 양식 영역을 표시 하는 경우가 있을 수 있습니다. 예를 들어 연락처 항목에 회사 주소가 없으면 지도 표시에 비즈니스의 위치를 표시 하는 양식 영역을 방지할 수 있습니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### <a name="to-prevent-outlook-from-displaying-a-form-region"></a>Outlook 양식 영역 표시 하지 않도록 설정 하려면  
  
1.  수정 하려는 양식 영역에 대 한 코드 파일을 엽니다.  
  
2.  확장 된 **양식 영역 팩터리** 코드 영역입니다.  
  
3.  코드를 추가 하는 `FormRegionInitializing` 설정 하는 이벤트 처리기는 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 의 속성은 <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> 클래스를 **true**합니다.  
  
 이 예제에서는 연락처 항목에는 주소, 없는 경우에 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성이 **true**, 양식 영역이 표시 되지 않습니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Separate_O12/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Separate_O12/MapIt.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [연습: Outlook에서 디자인한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  
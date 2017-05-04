---
title: "방법: Outlook에서 양식 영역 표시하지 않기 | Microsoft Docs"
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
  - "양식 영역 표시 취소"
  - "양식 영역[Visual Studio에서 Office 개발], 표시 취소"
ms.assetid: 82a25def-776a-476a-a72d-d0a48a827d3c
caps.latest.revision: 24
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 24
---
# 방법: Outlook에서 양식 영역 표시하지 않기
  Microsoft Office Outlook에서 특정 항목의 양식 영역을 표시하지 않도록 하려는 경우가 있을 수 있습니다.  예를 들어 연락처 항목에 회사 주소가 들어 있지 않은 경우 회사의 위치를 지도로 보여 주는 양식 영역이 나타나지 않도록 할 수 있습니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
### Outlook에서 양식 영역을 표시하지 않도록 하려면  
  
1.  수정하려는 양식 영역의 코드 파일을 엽니다.  
  
2.  **양식 영역 팩터리** 코드 영역을 확장합니다.  
  
3.  <xref:Microsoft.Office.Tools.Outlook.FormRegionInitializingEventArgs> 클래스의 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성을 **true**로 설정하는 코드를  `FormRegionInitializing` 이벤트 처리기에 추가합니다.  
  
 이 예제에서 연락처 항목에 주소가 들어 있지 않으면 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 속성은 **true**로 설정되며 양식 영역은 표시되지 않습니다.  
  
## 예제  
 [!code-csharp[Trin_Outlook_FR_Separate#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_Outlook_FR_Separate/CS/MapIt.cs#1)]
 [!code-vb[Trin_Outlook_FR_Separate#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_Outlook_FR_Separate/VB/MapIt.vb#1)]  
  
## 참고 항목  
 [Outlook 양식 영역 만들기](../vsto/creating-outlook-form-regions.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [방법: Outlook 추가 기능 프로젝트에 양식 영역 추가](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)   
 [연습: Outlook 양식 영역 디자인](../vsto/walkthrough-designing-an-outlook-form-region.md)   
 [연습: Outlook에서 디자인한 양식 영역 가져오기](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)  
  
  
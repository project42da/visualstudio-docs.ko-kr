---
title: "방법: 프로그래밍 방식으로 현재 Outlook 항목 확인 | Microsoft Docs"
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
  - "전자 메일[Visual Studio에서 Office 개발], 현재 항목"
  - "메일 항목[Visual Studio에서 Office 개발], 현재"
  - "Outlook[Visual Studio에서 Office 개발], 현재 항목"
  - "SelectionChange 이벤트"
ms.assetid: b4fb5ccd-b297-463e-9208-1fec42482531
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 방법: 프로그래밍 방식으로 현재 Outlook 항목 확인
  이 예제에서는 Explorer.SelectionChange 이벤트를 사용하여 현재 폴더의 이름과 선택한 항목에 대한 일부 정보를 표시합니다.  그런 다음 선택한 항목을 표시합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 예제  
 [!code-csharp[Trin_OL_CurrentItem#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_OL_CurrentItem/CS/thisaddin.cs#1)]
 [!code-vb[Trin_OL_CurrentItem#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_OL_CurrentItem/VB/thisaddin.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Microsoft Office Outlook의 약속, 연락처 및 전자 메일 항목  
  
## 참고 항목  
 [Outlook 개체 모델 개요](../vsto/outlook-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [방법: 프로그래밍 방식으로 특정 연락처 검색](../vsto/how-to-programmatically-search-for-a-specific-contact.md)  
  
  
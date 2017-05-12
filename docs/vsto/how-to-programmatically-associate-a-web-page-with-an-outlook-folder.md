---
title: "방법: 프로그래밍 방식으로 Outlook 폴더에 웹 페이지 연결"
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
  - "폴더[Visual Studio에서 Office 개발], 웹 페이지"
  - "Outlook[Visual Studio에서 Office 개발], 폴더에 연결된 웹 페이지"
  - "웹 페이지[Visual Studio에서 Office 개발], Outlook 폴더"
ms.assetid: b211b1b2-11e4-4316-87b7-98a3d10f95d1
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 16
---
# 방법: 프로그래밍 방식으로 Outlook 폴더에 웹 페이지 연결
  이 예제에서는 Microsoft Office Outlook에 `HtmlView`라는 폴더가 있는지 확인합니다.  해당 폴더가 없으면 코드에서는 폴더를 만들고 폴더에 웹 페이지를 할당합니다.  해당 폴더가 있으면 코드에서는 폴더 내용을 표시합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 예제  
 [!code-csharp[Trin_OL_HTMLFolder#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_OL_HTMLFolder/CS/thisaddin.cs#1)]  
  
## 참고 항목  
 [폴더 사용](../vsto/working-with-folders.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [방법: 프로그래밍 방식으로 사용자 지정 폴더 항목 만들기](../vsto/how-to-programmatically-create-custom-folder-items.md)  
  
  
---
title: "방법: 프로그래밍 방식으로 Outlook 전자 메일 항목의 첨부 파일 저장 | Microsoft Docs"
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
  - "Outlook[Visual Studio에서 Office 개발], 첨부 파일"
  - "메일[Visual Studio에서 Office 개발], 첨부 파일"
  - "전자 메일 첨부 파일 저장"
  - "메일 항목[Visual Studio에서 Office 개발], 첨부 파일"
  - "첨부 파일[Visual Studio에서 Office 개발]"
ms.assetid: 2f05e2bb-ae4f-407c-a6da-a3b1a4c31ab3
caps.latest.revision: 23
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 22
---
# 방법: 프로그래밍 방식으로 Outlook 전자 메일 항목의 첨부 파일 저장
  이 예제는 받은 편지함에 전자 메일이 수신될 때 메일 첨부 파일을 지정된 폴더에 저장합니다.  
  
> [!IMPORTANT]  
>  이 예제는 C 디렉터리의 루트에 **TestFileSave**라는 폴더를 추가한 경우에만 사용할 수 있습니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 예제  
 [!code-csharp[Trin_OL_SaveAttachments#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_OL_SaveAttachments/CS/thisaddin.cs#1)]  
  
## 참고 항목  
 [메일 항목 작업](../vsto/working-with-mail-items.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [방법: 프로그래밍 방식으로 전자 메일 메시지를 받은 경우 작업 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)   
 [방법: 프로그래밍 방식으로 특정 폴더 내용 검색](../vsto/how-to-programmatically-search-within-a-specific-folder.md)  
  
  
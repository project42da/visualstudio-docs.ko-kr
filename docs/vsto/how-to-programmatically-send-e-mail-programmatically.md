---
title: "방법: 프로그래밍 방식으로 전자 메일 보내기"
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
  - "전자 메일[Visual Studio에서 Office 개발], 보내기"
  - "메일 항목[Visual Studio에서 Office 개발], 전자 메일 보내기"
  - "Outlook[Visual Studio에서 Office 개발], 전자 메일 만들기"
  - "Outlook[Visual Studio에서 Office 개발], 전자 메일 보내기"
ms.assetid: 4fa0e1b5-2caf-4a11-8626-df643b23f5f0
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 프로그래밍 방식으로 전자 메일 보내기
  이 예제에서는 전자 메일 주소에 **example.com**이라는 도메인 이름이 있는 연락처로 전자 메일 메시지를 보냅니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 예제  
 [!code-csharp[Trin_OL_ProgramEmail#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_OL_ProgramEMail/CS/thisaddin.cs#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   전자 메일 주소에 도메인 이름 **example.com**이 있는 연락처  
  
## 강력한 프로그래밍  
 도메인 이름 **example.com**을 검색하는 필터 코드를 제거하지 마십시오.  필터를 제거하면 솔루션에서 모든 연락처로 전자 메일 메시지를 보냅니다.  
  
## 참고 항목  
 [메일 항목 작업](../vsto/working-with-mail-items.md)   
 [방법: 프로그래밍 방식으로 전자 메일 항목 만들기](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [방법: 프로그래밍 방식으로 Outlook 연락처 액세스](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [방법: 프로그래밍 방식으로 전자 메일 메시지를 받은 경우 작업 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  
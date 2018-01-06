---
title: "방법: 프로그래밍 방식으로 연락처에서 전자 메일 주소에 대 한 검색 | Microsoft Docs"
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
- e-mail [Office development in Visual Studio], searching
- contacts [Office development in Visual Studio], searching
- searching contacts
ms.assetid: e973a407-8b94-45c7-acdf-fe330115fb33
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 57c0cac0dd2b22b38284caec0a2bfb40d6e5b101
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-programmatically-search-for-an-e-mail-address-in-contacts"></a>방법: 프로그래밍 방식으로 연락처에서 전자 메일 주소 검색
  이 예제에서는 메일 주소에 도메인 이름 **example.com** 이 있는 연락처에 대한 연락처 폴더를 검색합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예  
 [!code-csharp[Trin_OL_SearchEmail#1](../vsto/codesnippet/CSharp/Trin_OL_SearchEmail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   메일 주소에 도메인 이름 **example.com** (예: `somebody@example.com`) 및 이름과 성이 있는 연락처입니다.  
  
## <a name="see-also"></a>참고 항목  
 [연락처 항목 작업](../vsto/working-with-contact-items.md)   
 [방법: 프로그래밍 방식으로 전자 메일 보내기](../vsto/how-to-programmatically-send-e-mail-programmatically.md)   
 [방법: 프로그래밍 방식으로 Outlook 연락처 액세스](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [방법: 프로그래밍 방식으로 Outlook 연락처에 엔트리 추가](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)  
  
  
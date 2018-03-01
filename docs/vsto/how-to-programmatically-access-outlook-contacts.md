---
title: "방법: 프로그래밍 방식으로 Outlook 연락처 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 4d4d88416507f7e63cd112df350dc93b2e13605f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-access-outlook-contacts"></a>방법: 프로그래밍 방식으로 Outlook 연락처 액세스
  이 예제에서는 성이 지정 된 검색 문자열을 포함 하는 모든 연락처를 찾습니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예  
 [!code-csharp[Trin_OL_AccessContacts#1](../vsto/codesnippet/CSharp/Trin_OL_AccessContacts.trin_ol_accesscontacts/thisaddin.cs#1)]
 [!code-csharp[Trin_OL_AccessContacts#1](../vsto/codesnippet/CSharp/Trin_OL_AccessContacts.trin_ol_accesscontacts/thisaddin.cs#1)]
 [!code-vb[Trin_OL_AccessContacts#1](../vsto/codesnippet/VisualBasic/Trin_OL_AccessContacts/thisaddin.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   문자열을 포함 하는 성이 연락처 "**Na"** (예를 들어 Tzipi Butnaru)에 **연락처** 폴더입니다.  
  
## <a name="see-also"></a>참고 항목  
 [연락처 항목 작업](../vsto/working-with-contact-items.md)   
 [방법: 프로그래밍 방식으로 Outlook 연락처에 항목 추가](../vsto/how-to-programmatically-add-an-entry-to-outlook-contacts.md)   
 [방법: 프로그래밍 방식으로 특정 연락처 검색](../vsto/how-to-programmatically-search-for-a-specific-contact.md)   
 [방법: 프로그래밍 방식으로 연락처에서 전자 메일 주소 검색](../vsto/how-to-programmatically-search-for-an-e-mail-address-in-contacts.md)   
 [방법: 프로그래밍 방식으로 Outlook 연락처 삭제](../vsto/how-to-programmatically-delete-outlook-contacts.md)  
  
  
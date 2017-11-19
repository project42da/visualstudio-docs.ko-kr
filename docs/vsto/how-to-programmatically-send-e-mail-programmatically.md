---
title: "방법: 프로그래밍 방식으로 전자 메일을 보낼 | Microsoft Docs"
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
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
ms.assetid: 4fa0e1b5-2caf-4a11-8626-df643b23f5f0
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 98b0eefafa86fdaf8f7a664ac75a2f7c71a43549
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-send-e-mail"></a>방법: 프로그래밍 방식으로 전자 메일 보내기  
  이 예제에서는 도메인 이름을 가진 연락처에 전자 메일 메시지를 보냅니다 **example.com** 전자 메일 주소에 있습니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예제  
 [!code-csharp[Trin_OL_ProgramEmail#1](../vsto/codesnippet/CSharp/Trin_OL_ProgramEMail/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   도메인 이름을 가진 연락처 **example.com** 전자 메일 주소에 있습니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 도메인 이름을 검색 하는 필터 코드를 제거 하지 마십시오 **example.com**합니다. 필터를 제거 하는 경우 솔루션 회원님 연락처의 모든 전자 메일 메시지를 전송 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [메일 항목 작업](../vsto/working-with-mail-items.md)   
 [방법: 프로그래밍 방식으로 전자 메일 항목 만들기](../vsto/how-to-programmatically-create-an-e-mail-item.md)   
 [방법: 프로그래밍 방식으로 Outlook 연락처 액세스](../vsto/how-to-programmatically-access-outlook-contacts.md)   
 [방법: 프로그래밍 방식으로 전자 메일 메시지를 받은 경우 작업 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  
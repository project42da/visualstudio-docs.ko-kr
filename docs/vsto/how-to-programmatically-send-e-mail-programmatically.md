---
title: '방법: 프로그래밍 방식으로 전자 메일을 보낼 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- mail items [Office development in Visual Studio], sending e-mail
- Outlook [Office development in Visual Studio], creating e-mail
- Outlook [Office development in Visual Studio], sending e-mail
- e-mail [Office development in Visual Studio], sending
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: c3ee656a8a4965f01969bad19d66d0ea6215bcbe
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
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
  
  
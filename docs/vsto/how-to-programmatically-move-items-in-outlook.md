---
title: "방법: 프로그래밍 방식으로 Outlook에서 항목을 이동 | Microsoft Docs"
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
helpviewer_keywords: Outlook folders [Office development in Visual Studio], moving items
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 72b35bde8775a859ef15c5e18b381615974bccd7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-move-items-in-outlook"></a>방법: 프로그래밍 방식으로 Outlook에서 항목 이동
  읽지 않은 전자 메일 메시지를 이동 하는이 예제는 **받은 편지함** 라는 폴더 **테스트**합니다. 이 예제에서는 포함 된 메시지가 이동 **테스트** 에 `Subject` 필드입니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예  
 [!code-csharp[Trin_OL_MoveItems#1](../vsto/codesnippet/CSharp/Trin_OL_MoveItems/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   명명 된 Outlook 메일 폴더 **테스트**합니다.  
  
-   전자 메일 메시지를 단어 함께 도착 한 **테스트** 에 `Subject` 필드입니다.  
  
## <a name="see-also"></a>참고 항목  
 [폴더 작업](../vsto/working-with-folders.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [방법: 프로그래밍 방식으로 특정 폴더 내에서 검색](../vsto/how-to-programmatically-search-within-a-specific-folder.md)   
 [방법: 프로그래밍 방식으로 전자 메일 메시지를 받은 경우 작업 수행](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)  
  
  
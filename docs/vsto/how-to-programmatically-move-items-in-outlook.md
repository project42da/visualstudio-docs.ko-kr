---
title: '방법: 프로그래밍 방식으로 Outlook에서 항목을 이동 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], moving items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: a9eca20d533ba429db8b4227d5620c507fd805a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-programmatically-move-items-in-outlook"></a>방법: 프로그래밍 방식으로 Outlook에서 항목 이동
  읽지 않은 전자 메일 메시지를 이동 하는이 예제는 **받은 편지함** 라는 폴더 **테스트**합니다. 이 예제에서는 포함 된 메시지가 이동 **테스트** 에 `Subject` 필드입니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예제  
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
  
  
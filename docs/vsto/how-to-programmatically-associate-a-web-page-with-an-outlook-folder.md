---
title: "방법: 프로그래밍 방식으로 Outlook 폴더에 웹 페이지 연결 | Microsoft Docs"
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
- folders [Office development in Visual Studio], Web pages and
- Outlook [Office development in Visual Studio], Web pages attached to folders
- Web pages [Office development in Visual Studio], Outlook folders
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0fa0ccb3035bc4be8e316c96bd5da8c166dcb4b8
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-associate-a-web-page-with-an-outlook-folder"></a>방법: 프로그래밍 방식으로 Outlook 폴더에 웹 페이지 연결
  이 예제에서는 명명 된 폴더에 대 한 검사 `HtmlView` Microsoft Office Outlook에서. 폴더가 없는 경우 코드는 폴더를 만들고 웹 페이지를 할당 합니다. 폴더가 있으면 코드 폴더의 내용을 표시 합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예  
 [!code-csharp[Trin_OL_HTMLFolder#1](../vsto/codesnippet/CSharp/Trin_OL_HTMLFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>참고 항목  
 [폴더 작업](../vsto/working-with-folders.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [방법: 프로그래밍 방식으로 사용자 지정 폴더 항목 만들기](../vsto/how-to-programmatically-create-custom-folder-items.md)  
  
  
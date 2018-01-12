---
title: "방법: 프로그래밍 방식으로 현재 Outlook 항목 확인 | Microsoft Docs"
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
- mail items [Office development in Visual Studio], current
- e-mail [Office development in Visual Studio], current item
- SelectionChange event
- Outlook [Office development in Visual Studio], current item
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: de17e299e98a46a82547bc38dfecd17a9f5aea58
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-programmatically-determine-the-current-outlook-item"></a>방법: 프로그래밍 방식으로 현재 Outlook 항목 확인
  이 예제에서는 선택한 항목에 대 한 정보 및 현재 폴더의 이름을 표시 하려면 Explorer.SelectionChange 이벤트를 사용 합니다. 그런 다음 선택한 항목을 표시 합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예  
 [!code-vb[Trin_OL_CurrentItem#1](../vsto/codesnippet/VisualBasic/Trin_OL_CurrentItem/thisaddin.vb#1)]
 [!code-csharp[Trin_OL_CurrentItem#1](../vsto/codesnippet/CSharp/Trin_OL_CurrentItem/thisaddin.cs#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   약속, 연락처 및 Microsoft Office Outlook에서 전자 메일 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Outlook 개체 모델 개요](../vsto/outlook-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)   
 [방법: 프로그래밍 방식으로 특정 연락처 검색](../vsto/how-to-programmatically-search-for-a-specific-contact.md)  
  
  
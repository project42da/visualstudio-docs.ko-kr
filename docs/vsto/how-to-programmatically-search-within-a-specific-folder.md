---
title: "방법: 프로그래밍 방식으로 특정 폴더 내에서 검색 | Microsoft Docs"
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
helpviewer_keywords: Outlook folders [Office development in Visual Studio], searching
ms.assetid: 8f2cdc8b-f757-412c-aa2b-ebd5bc52f697
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 97776e667333d00ecbd10feeb12620b16f2d3ac9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-programmatically-search-within-a-specific-folder"></a>방법: 프로그래밍 방식으로 특정 폴더 내용 검색
  사용 하 여이 코드 예제는 `Find` 및 `FindNext` 에 있는 전자 메일 메시지의 제목 필드에 텍스트를 검색 하는 메서드는 **받은 편지함**합니다. 이 메서드는 문자열 필터를 사용 하 여의 시작 문자가 문자 T에 대 한 확인은 `Subject` 텍스트입니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## <a name="example"></a>예제  
 [!code-csharp[Trin_OL_SearchFolder#1](../vsto/codesnippet/CSharp/Trin_OL_SearchFolder/thisaddin.cs#1)]  
  
## <a name="see-also"></a>참고 항목  
 [폴더 작업](../vsto/working-with-folders.md)   
 [Outlook 개체 모델 개요](../vsto/outlook-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)  
  
  
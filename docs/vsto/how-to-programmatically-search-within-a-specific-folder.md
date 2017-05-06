---
title: "방법: 프로그래밍 방식으로 특정 폴더 내용 검색"
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
  - "Outlook 폴더[Visual Studio에서 Office 개발], 검색"
ms.assetid: 8f2cdc8b-f757-412c-aa2b-ebd5bc52f697
caps.latest.revision: 30
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 29
---
# 방법: 프로그래밍 방식으로 특정 폴더 내용 검색
  이 코드 예제에서는 `Find` 및 `FindNext` 메서드를 사용하여 **받은 편지함**에 있는 전자 메일 메시지의 제목 필드에서 텍스트를 검색합니다.  이 메서드는 문자열 필터를 사용하여 시작 문자가 문자 T인 `Subject` 텍스트를 검색합니다.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
## 예제  
 [!code-csharp[Trin_OL_SearchFolder#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_OL_SearchFolder/CS/thisaddin.cs#1)]  
  
## 참고 항목  
 [폴더 사용](../vsto/working-with-folders.md)   
 [Outlook 개체 모델 개요](../vsto/outlook-object-model-overview.md)   
 [방법: 프로그래밍 방식으로 이름으로 폴더 검색](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)  
  
  
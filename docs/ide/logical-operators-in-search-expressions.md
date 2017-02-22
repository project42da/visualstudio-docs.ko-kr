---
title: "검색 식의 논리 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도움말 뷰어 2.0, 검색의 논리 연산자"
  - "검색의 논리 연산자[도움말 뷰어 2.0]"
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
caps.latest.revision: 9
caps.handback.revision: 9
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 검색 식의 논리 연산자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

논리 연산자를 사용하면 간단한 검색 표현으로부터 더 복잡한 검색 표현을 만들어 콘텐츠 검색을 상세하게 할 수 있다.  다음 표에서 알 수 있듯이 논리 연산자로 검색 쿼리에 검색어를 몇 개나 조합할 수 있는지 지정한다.  
  
> [!IMPORTANT]
>  논리 연산자는 모두 대문자로 입력해야 검색 엔진에서 식별할 수 있습니다.  
  
|검색하기|사용할 도구|예제|결과|  
|----------|------------|--------|--------|  
|두 용어가 항목이 같음|AND|dib AND 색상표|"dib" 및 "색상표"를 모두 포함하는 항목입니다.|  
|두 용어 중 하나가 항목에 포함됨|또는|래스터 OR 벡터|"래스터" 또는 "벡터" 중 하나를 포함하는 항목입니다.|  
|첫 번째 용어만 같은 항목이고 두 번째 용어는 아님|NOT|"운영 체제"는 DOS가 아님|"DOS"를 제외한 "운영 체제"를 포함하는 항목입니다.|  
|두 용어가 한 항목에서 서로 밀접하게 연관됨|근사값|사용자 NEAR 커널|"커널"과 매우 유사한 항목 중 "사용자"를 포함하는 항목입니다.|  
  
## 참고 항목  
 [전체 텍스트 검색 팁](../ide/full-text-search-tips.md)   
 [정보 찾기](../ide/locate-information.md)
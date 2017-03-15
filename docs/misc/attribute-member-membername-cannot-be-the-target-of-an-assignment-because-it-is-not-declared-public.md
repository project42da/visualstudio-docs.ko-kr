---
title: "특성 멤버 &#39;&lt;membername&gt;&#39;은 &#39;Public&#39;으로 선언되지 않았으므로 할당 대상일 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31511"
  - "bc31511"
helpviewer_keywords: 
  - "BC31511"
ms.assetid: f8c958f6-58a4-4aff-b8c3-f2e9481e8132
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 특성 멤버 &#39;&lt;membername&gt;&#39;은 &#39;Public&#39;으로 선언되지 않았으므로 할당 대상일 수 없습니다.
특성의 전용 멤버에 값을 할당하려고 했습니다.  
  
 **오류 ID:** BC31511  
  
### 이 오류를 해결하려면  
  
1.  할당을 제거합니다.  
  
2.  개발한 사용자 지정 특성을 사용하는 경우 특성 멤버의 액세스 한정자를 `Public`으로 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)
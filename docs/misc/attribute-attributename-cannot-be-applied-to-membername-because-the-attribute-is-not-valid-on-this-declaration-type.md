---
title: "이 선언 형식에서는 &#39;&lt;attributename&gt;&#39; 특성이 유효하지 않으므로 &#39;&lt;membername&gt;&#39;에 적용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30662"
  - "bc30662"
helpviewer_keywords: 
  - "BC30662"
ms.assetid: 5cd07950-37d0-45e9-8770-3eaac54ff7d9
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 선언 형식에서는 &#39;&lt;attributename&gt;&#39; 특성이 유효하지 않으므로 &#39;&lt;membername&gt;&#39;에 적용할 수 없습니다.
사용 중인 특성이 사용 중인 항목에 적합하지 않습니다.  
  
 **오류 ID:** BC30662  
  
### 이 오류를 해결하려면  
  
1.  사용하는 항목에 맞는 특성을 선택합니다. 예를 들어 메서드를 사용하는 경우 메서드에서 사용하도록 디자인된 특성을 선택합니다.  
  
2.  직접 개발한 사용자 지정 특성을 사용하는 경우 사용 중인 항목의 종류와 일치하도록 `AttributeUsage` 특성을 변경합니다.  
  
## 참고 항목  
 <xref:System.AttributeUsageAttribute>   
 [빌드에 없음: Visual Basic의 특성](http://msdn.microsoft.com/ko-kr/620bfc0e-4582-4c8b-8432-ebc5c3dccc22)   
 [빌드에 없음: Visual Basic의 사용자 지정 특성](http://msdn.microsoft.com/ko-kr/d72d8a5c-8f64-4614-b15b-cad66845d047)
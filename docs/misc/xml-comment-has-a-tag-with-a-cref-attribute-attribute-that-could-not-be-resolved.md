---
title: "XML 주석에 확인할 수 없는 &#39;cref&#39; 특성 &#39;&lt;attribute&gt;&#39;가 포함된 태그가 있습니다. | Microsoft Docs"
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
  - "bc42309"
  - "vbc42309"
helpviewer_keywords: 
  - "BC42309"
ms.assetid: c9f3cfa5-565f-48bf-8616-cfb25d24f89e
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 주석에 확인할 수 없는 &#39;cref&#39; 특성 &#39;&lt;attribute&gt;&#39;가 포함된 태그가 있습니다.
XML 주석에 확인할 수 없는 'cref' 특성 '\<attribute\>'가 포함된 태그가 있습니다. XML 주석이 무시됩니다.  
  
 태그에 식별자의 상대적 이름을 지정하여 XML의 다른 요소에 대한 링크를 지정하는 `cref` 특성을 사용할 수 있습니다. 컴파일 시간에 컴파일러는 사용자가 가리킨 값에 대한 정규화된 XML 식별자로 값을 바꿉니다. 컴파일러는 형식 또는 멤버를 찾기 위해 일반적인 확인 규칙을 사용합니다.  
  
 **오류 ID:** BC42309  
  
### 이 오류를 해결하려면  
  
-   유효한 코드 포인트를 가리키도록 `cref` 특성의 유효성을 검사합니다.  
  
## 참고 항목  
 [How to: Create XML Documentation](../Topic/How%20to:%20Create%20XML%20Documentation%20in%20Visual%20Basic.md)   
 [XML Comment Tags](/dotnet/visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments)
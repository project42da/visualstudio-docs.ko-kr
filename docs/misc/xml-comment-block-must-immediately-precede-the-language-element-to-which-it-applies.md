---
title: "XML 주석 블록은 이 주석 블록이 적용되는 언어 요소의 바로 앞에 와야 함 | Microsoft Docs"
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
  - "vbc42300"
  - "bc42300"
helpviewer_keywords: 
  - "BC42300"
ms.assetid: f9f7d1da-a723-4237-bd78-6db7ed8bc4aa
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML 주석 블록은 이 주석 블록이 적용되는 언어 요소의 바로 앞에 와야 함
XML 주석 블록은 이 주석 블록이 적용되는 언어 요소의 바로 앞에 와야 합니다. XML 주석이 무시됩니다.  
  
 이 오류는 태그가 잘못 배치되었거나 형식이 잘못된 경우에도 발생할 수 있습니다.  
  
 **오류 ID:** BC42300  
  
### 이 오류를 해결하려면  
  
1.  주석 블록을 적용되는 언어 요소의 앞에 오도록 이동합니다. 관련 없는 문자가 초기 태그 앞에 잘못 삽입되지 않았는지 확인합니다.  
  
2.  태그가 유효한지 확인합니다.  
  
## 참고 항목  
 [How to: Create XML Documentation](../Topic/How%20to:%20Create%20XML%20Documentation%20in%20Visual%20Basic.md)   
 [XML Comment Tags](/dotnet/visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments)
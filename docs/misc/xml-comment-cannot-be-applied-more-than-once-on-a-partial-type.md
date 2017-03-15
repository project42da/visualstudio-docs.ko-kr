---
title: "부분 &lt;type&gt;에는 XML 주석을 두 번 이상 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc42314"
  - "vbc42314"
helpviewer_keywords: 
  - "BC42314"
ms.assetid: 23c76238-843a-44fe-88b7-25e604ee924b
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 부분 &lt;type&gt;에는 XML 주석을 두 번 이상 적용할 수 없습니다.
부분 \<type\>에는 XML 주석을 두 번 이상 적용할 수 없습니다. 이 \<type\>에 대한 XML 주석이 무시됩니다.  
  
 XML 주석 블록은 부분 형식\(Partial Type\)의 한 부분 위에만 표시될 수 있습니다.  
  
 XML 주석 블록이 부분 형식\(Partial Type\)의 둘 이상의 부분 위에 표시되는 경우 각 주석 블록에 대해 이 경고가 만들어지고 최상위 XML 주석이 무시됩니다.  
  
 **오류 ID:** BC42314  
  
### 이 오류를 해결하려면  
  
-   불필요한 주석 블록을 제거합니다.  
  
## 참고 항목  
 [How to: Create XML Documentation](../Topic/How%20to:%20Create%20XML%20Documentation%20in%20Visual%20Basic.md)   
 [XML Comment Tags](/dotnet/visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments)
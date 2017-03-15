---
title: "전자 문자는 XML 구분 기호로 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31197"
  - "bc31197"
helpviewer_keywords: 
  - "BC31197"
ms.assetid: f5d724f8-545b-4cf8-9606-12c63814c6e8
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 전자 문자는 XML 구분 기호로 사용할 수 없습니다.
XML 리터럴이 구분 기호로 전자 문자를 포함하여 정의되었습니다. 전자 문자는 와이드 문자 또는 멀티바이트 문자라고도 합니다.  
  
 **오류 ID:** BC31197  
  
### 이 오류를 해결하려면  
  
-   XML 리터럴 정의에서 전자 문자를 제거하고 유효한 ANSI 구분 기호 문자로 바꿉니다. 유효한 구분 기호 문자는 `<`, `>`, `=`, `:`, `/`입니다.  
  
## 참고 항목  
 [XML Literals](/dotnet/visual-basic/language-reference/xml-literals/index)   
 [.NET Framework의 문자 인코딩](../Topic/Character%20Encoding%20in%20the%20.NET%20Framework.md)   
 [XML](/dotnet/visual-basic/programming-guide/language-features/xml/index)
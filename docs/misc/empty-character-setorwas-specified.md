---
title: "빈 문자 집합이 지정되었습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.message.VS_E_RE_EMPTYSET"
  - "vs.message.0x800A00DF"
ms.assetid: 27ed2ebe-a492-4bc9-ab33-a09fba6cf1d3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 빈 문자 집합이 지정되었습니다.
이 오류는 정규식 옵션을 선택한 후 완전하지 않은 구문이 포함된 문자열을 **문자 집합 \[\]** 또는 **집합에 없는 문자 \[^\]** 패턴에 지정한 경우 발생합니다.  예를 들면 `[}` 문자열을 입력한 경우입니다.  
  
### 이 오류를 해결하려면  
  
1.  정규식 항목에서 올바른 패턴 구문에 대한 내용을 검토한 후 문자열을 다시 입력합니다.  
  
## 참고 항목  
 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)   
 [NIB: Find and Replace, Quick Find](http://msdn.microsoft.com/ko-kr/dad03582-4931-4893-83ba-84b37f5b1600)   
 [파일에서 찾기](../ide/find-in-files.md)   
 [텍스트 찾기 및 바꾸기](../ide/finding-and-replacing-text.md)
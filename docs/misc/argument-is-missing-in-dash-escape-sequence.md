---
title: "Argument is missing in &#39;\&#39; escape sequence. | Microsoft Docs"
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
  - "vs.message.VS_E_RE_ESCAPEMISSINGARG"
  - "vs.message.0x800A00BD"
ms.assetid: 5bd6559b-8cd9-450f-91c8-335ff1b1ef86
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Argument is missing in &#39;\&#39; escape sequence.
이 오류는 검색 문자열에 정규식이나 와일드카드를 사용하여 검색 또는 바꾸기를 수행하는 경우 발생합니다.  이 오류는 패턴 끝에 단일 백슬래시\(`\`\)가 있거나 올바른 16진수 유니코드 문자 없이 `\x` 또는 `\u`를 입력하는 경우 발생할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  정규식 이스케이프 문자를 사용하여 검색하려면 `\`를 입력하십시오.  
  
2.  유니코드 문자를 검색하려면 `\x` 또는 `\u` 다음에 유니코드 값을 입력하십시오.  
  
3.  리터럴 백슬래시를 검색하려면 `\\`를 사용하십시오.  
  
## 참고 항목  
 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)   
 [NIB: Find and Replace, Quick Find](http://msdn.microsoft.com/ko-kr/dad03582-4931-4893-83ba-84b37f5b1600)   
 [파일에서 찾기](../ide/find-in-files.md)
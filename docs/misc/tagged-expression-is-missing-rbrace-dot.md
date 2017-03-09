---
title: "Tagged expression is missing &#39;}&#39;. | Microsoft Docs"
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
  - "vs.message.VS_E_RE_TAGMISSINGCLOSE"
  - "vs.message.0x800A00D6"
ms.assetid: 832905d3-0faa-43c8-9c37-37130e66e6d2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Tagged expression is missing &#39;}&#39;.
이 오류는 찾기 문자열에 여는 중괄호\(`{`\)만 지정하고 닫는 중괄호\(`}`\)를 생략한 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  리터럴 문자 `{`를 검색하려면 `\{`를 사용하십시오.  
  
2.  식에 태그를 지정하려면 누락된 `}`를 입력하십시오.  
  
## 참고 항목  
 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)   
 [NIB: Find and Replace, Quick Find](http://msdn.microsoft.com/ko-kr/dad03582-4931-4893-83ba-84b37f5b1600)   
 [파일에서 찾기](../ide/find-in-files.md)
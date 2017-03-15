---
title: "Unknown argument for &#39;:&#39; operator. Complete Regular Expression required in search string. | Microsoft Docs"
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
  - "vs.message.0x800A00BE"
  - "vs.message.VS_E_RE_SPECIALUNKNOWN"
ms.assetid: 8cbc2f7f-7ea1-4803-904c-1f716cd36376
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Unknown argument for &#39;:&#39; operator. Complete Regular Expression required in search string.
이 오류는 검색 문자열에 정규식이나 와일드카드를 사용하여 검색 또는 바꾸기를 수행하는 경우 발생합니다.  연산자 콜론\(`:`\)을 입력했지만 다음에 오는 인수가 잘못되었습니다.  
  
> [!NOTE]
>  콜론\(`:`\) 연산자의 인수는 대\/소문자를 구분합니다.  
  
### 이 오류를 해결하려면  
  
1.  "정규식" 항목에 있는 올바른 정규식 구문을 검토하십시오.  
  
2.  인수의 대\/소문자가 올바르게 사용되었는지 다시 한 번 확인하십시오.  
  
3.  IME를 사용 중인 경우 인수가 전자 문자를 사용하여 지정되었는지 여부를 확인하십시오.  
  
## 참고 항목  
 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)   
 [NIB: Find and Replace, Quick Find](http://msdn.microsoft.com/ko-kr/dad03582-4931-4893-83ba-84b37f5b1600)   
 [파일에서 찾기](../ide/find-in-files.md)
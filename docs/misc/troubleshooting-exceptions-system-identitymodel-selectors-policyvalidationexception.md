---
title: "예외 문제 해결: System.IdentityModel.Selectors.PolicyValidationException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PolicyValidationException 예외"
  - "System.IdentityModel.Selectors.PolicyValidationException 예외"
ms.assetid: 510c7698-a12b-4bcb-a9d8-87c704b62ffa
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IdentityModel.Selectors.PolicyValidationException
받는 사람이 제공한 정책의 유효성을 검사할 수 없는 경우 <xref:System.IdentityModel.Selectors.PolicyValidationException> 예외가 throw됩니다. 정책 요구 사항에 대한 자세한 내용은 [정보 카드 프로필 V1.0에 대한 기술 참조](http://go.microsoft.com/fwlink/?LinkID=102401)를 참조하세요.  
  
 모든 잘못된 정책 콘텐츠가 이 오류를 발생시킬 수 있습니다. 정책 콘텐츠와 관련된 일반적인 문제는 다음과 같습니다.  
  
-   잘못된 키 형식  
  
-   잘못된 키 크기  
  
-   잘못된 XML  
  
-   정책에 지정된 클레임이 없음\(옵션이 아닌 클레임이 적어도 하나는 지정되어야 함\)  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.PolicyValidationException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
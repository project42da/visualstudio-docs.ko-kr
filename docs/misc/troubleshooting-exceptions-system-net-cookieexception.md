---
title: "예외 문제 해결: System.Net.CookieException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "CookieException 클래스"
ms.assetid: 7db6b962-cc5e-4b63-be65-894a8f186b38
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Net.CookieException
<xref:System.Net.CookieException> 예외는 쿠키 컨테이너에 쿠기를 추가할 때 오류가 발생하면 throw됩니다.  
  
## 관련 팁  
 **쿠키 크기가 쿠키 컨테이너에서 허용하는 최대 크기를 초과하지 않는지 확인하십시오.**  
 이 예외는 <xref:System.Net.Cookie>보다 길이가 더 긴 <xref:System.Net.CookieContainer.MaxCookieSize%2A>를 <xref:System.Net.CookieContainer>에 추가하려는 경우에 throw됩니다. 최대 쿠키 크기의 기본값은 4096바이트입니다.  
  
 **쿠키의 Name 속성을 설정할 때 값이 null 참조 또는 빈 문자열이 아닌지 확인하십시오.**  
 <xref:System.Net.Cookie.Name%2A> 클래스의 인스턴스를 사용하려면 <xref:System.Net.Cookie> 속성을 먼저 초기화해야 합니다. 등호, 세미콜론, 쉼표, 줄 바꿈\(\\n\), 캐리지 리턴\(\\r\), 탭\(\\t\) 문자는 예약되어 있으므로 이 특성 값으로 사용할 수 없습니다. 달러 기호\($\) 문자는 첫 번째 문자로 사용할 수 없습니다.  
  
 **쿠키의 Port 속성을 설정할 때 값이 유효하며 큰따옴표로 묶여 있는지 확인하십시오.**  
 <xref:System.Net.Cookie.Port%2A> 특성은 쿠키를 보낼 수 있는 포트를 제한합니다. 기본값을 적용하면 이 포트에 제한이 없습니다. 이 속성을 빈 문자열\(""\)로 설정하면 포트가 HTTP 응답에 사용되는 포트 하나로 제한됩니다. 포트를 지정하려면 포트 값을 쉼표로 구분하고 따옴표로 묶은 문자열을 값으로 사용해야 합니다.  
  
 **쿠키의 Value 속성을 설정할 때 값이 null이 아닌지 확인하십시오.**  
 세미콜론과 쉼표는 예약된 문자이므로 이 속성에 사용할 수 없습니다.  
  
## 참고 항목  
 <xref:System.Net.CookieException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [How to: Write a Cookie](../Topic/How%20to:%20Write%20a%20Cookie.md)
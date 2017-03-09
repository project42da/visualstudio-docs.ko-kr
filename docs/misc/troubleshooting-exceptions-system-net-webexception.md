---
title: "예외 문제 해결: System.Net.WebException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "WebException 클래스"
ms.assetid: 6cd69a2c-c52b-420d-be47-a4e34eaec6f3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Net.WebException
<xref:System.Net.WebException> 예외는 플러그형 프로토콜을 통해 네트워크에 액세스하는 동안 오류가 발생할 때 throw됩니다.  
  
## 관련 팁  
 **예외의 Response 속성을 확인하면 요청이 실패한 이유를 알 수 있습니다.**  
 <xref:System.Net.WebException> 클래스에서 파생된 클래스가 <xref:System.Net.WebRequest> 예외를 throw하는 경우 <xref:System.Net.WebException.Response%2A> 속성에서는 응용 프로그램에 인터넷 응답을 제공합니다.  
  
 **예외의 Status 속성을 확인하면 요청이 실패한 이유를 알 수 있습니다.**  
 예외의 <xref:System.Net.WebException.Status%2A> 속성은 오류에 대한 상태 정보를 제공합니다. 자세한 내용은 <xref:System.Net.WebExceptionStatus>을 참조하세요.  
  
 **XML Web Services를 한 단계씩 실행할 때 시간이 초과되면 XML Web Service 호출의 시간 제한 값을 무한대로 설정하십시오.**  
 자세한 내용은 [오류: 웹 서비스를 디버깅하는 동안 시간이 초과되었습니다.](../debugger/error-timeout-while-debugging-web-services.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Net.WebException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [방법: WebRequest 클래스를 사용하여 데이터 보내기](../Topic/How%20to:%20Send%20Data%20Using%20the%20WebRequest%20Class.md)   
 [방법: WebRequest 클래스를 사용하여 데이터 요청](../Topic/How%20to:%20Request%20Data%20Using%20the%20WebRequest%20Class.md)   
 [방법: WebRequest와 일치하는 프로토콜 관련 WebResponse 검색](../Topic/How%20to:%20Retrieve%20a%20Protocol-Specific%20WebResponse%20that%20Matches%20a%20WebRequest.md)
---
title: "예외 문제 해결: System.Net.Sockets.SocketException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "SocketException 클래스"
ms.assetid: 89e8194d-83b0-450f-91f5-548e5c13944d
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Net.Sockets.SocketException
<xref:System.Net.Sockets.SocketException> 예외는 네트워크에서 오류가 발생한 경우 <xref:System.Net.Sockets.Socket> 및 <xref:System.Net.Dns> 클래스를 통해 throw됩니다.  
  
## 관련 팁  
 **Errorcode 속성을 확인하면 소켓 오류가 발생한 이유를 알 수 있습니다.**  
 <xref:System.Net.Sockets.SocketException> 클래스의 기본 생성자는 마지막으로 발생한 운영 체제 소켓 오류로 <xref:System.Net.Sockets.SocketException.ErrorCode%2A> 속성을 설정합니다.  
  
## 참고 항목  
 <xref:System.Net.Sockets.SocketException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [SSL\(Secure Sockets Layer\) 사용](../Topic/Using%20Secure%20Sockets%20Layer.md)
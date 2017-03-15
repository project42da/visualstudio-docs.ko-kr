---
title: "예외 문제 해결: System.Net.HttpListenerException | Microsoft Docs"
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
  - "HttpListenerException 클래스"
ms.assetid: 1595c5b6-4710-4076-9bfc-9f70f52e679a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.Net.HttpListenerException
<xref:System.Net.HttpListenerException>은 HTTP\(Hypertext Transfer Protocol\) 요청을 처리하는 동안 오류가 발생하는 경우에 throw됩니다.  
  
## 관련 팁  
 등록하려는 URI 접두사가 이미 등록되어 있지 않은지 확인합니다.  
 URI 접두사가 이미 등록되어 있으면 이 예외가 발생합니다.  
  
 HTTP 요청이 올바른지 확인합니다.  
 HTTP 요청에 대한 응답을 만들거나 보내는 과정이나 <xref:System.Net.HttpListener>를 초기화하는 과정에서 오류가 발생하면 <xref:System.Net.HttpListener> 클래스와 해당 관련 클래스에서 이 예외가 throw됩니다.  
  
 `HttpListenerPrefixCollection.Add` 메서드를 사용하는 경우 `uriPrefix`가 이미 추가되지 않았는지 확인합니다.  
 다른 <xref:System.Net.HttpListener>에서 `uriPrefix` 접두사를 이미 추가한 경우 이 예외가 throw됩니다.  
  
## 참고 항목  
 <xref:System.Net.HttpListenerException>   
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpListenerPrefixCollection>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
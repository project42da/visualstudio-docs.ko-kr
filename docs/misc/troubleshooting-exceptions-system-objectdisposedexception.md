---
title: "예외 문제 해결: System.ObjectDisposedException | Microsoft Docs"
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
  - "ObjectDisposedException 클래스, 문제 해결"
ms.assetid: 702912b6-e927-4f8e-8b7c-2e1880312b0e
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.ObjectDisposedException
<xref:System.ObjectDisposedException> 예외는 닫힌 스트림이나 닫힌 레지스트리 키 같이 삭제된 개체에 대해 작업을 수행하려는 경우에 throw됩니다.  
  
## 관련 팁  
 **리소스를 사용하기 전에 리소스가 해제되지 않았는지 확인하세요.**  
 예를 들어, 스트림을 조작하려는 경우 이 스트림이 이미 닫혀 있지 않은지 확인해야 합니다.  
  
## 참고 항목  
 <xref:System.ObjectDisposedException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
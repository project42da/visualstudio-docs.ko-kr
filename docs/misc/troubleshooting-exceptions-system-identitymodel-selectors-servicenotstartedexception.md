---
title: "예외 문제 해결: System.IdentityModel.Selectors.ServiceNotStartedException | Microsoft Docs"
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
  - "System.IdentityModel.Selectors.ServiceNotStartedException 예외"
  - "ServiceNotStartedException 예외"
ms.assetid: 6d34bab2-994a-4b0c-893d-19b5d7acf92d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IdentityModel.Selectors.ServiceNotStartedException
사용자 컴퓨터에서 CardSpace가 시작되지 않은 경우 <xref:System.IdentityModel.Selectors.ServiceNotStartedException> 예외가 throw됩니다. CardSpace를 시작하려고 했지만 어떠한 이유로 시작되지 않은 경우 이 예외가 throw됩니다.  
  
 컴퓨터에서 CardSpace 서비스가 설치되어 있고 실행되고 있는지 확인합니다. MMC\(Microsoft Management Console\)를 사용하여 CardSpace 서비스를 수동으로 시작해 보십시오.  
  
 CardSpace 버전 1은 FAT 파일 시스템을 지원하지 않습니다. FAT 시스템에서는 CardSpace가 시작되지 않으며 이 예외가 발생합니다.  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.ServiceNotStartedException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
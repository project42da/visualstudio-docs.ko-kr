---
title: "예외 문제 해결: Microsoft.VisualBasic.ApplicationServices.CantStartSingleInstanceException | Microsoft Docs"
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
  - "CantStartSingleInstanceException 예외"
  - "Microsoft.VisualBasic.ApplicationServices.CantStartSingleInstanceException 예외"
ms.assetid: 3639f15d-9547-43da-8145-60da34782991
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: Microsoft.VisualBasic.ApplicationServices.CantStartSingleInstanceException
단일 인스턴스 응용 프로그램의 두 번째 인스턴스를 원래 인스턴스에 연결할 수 없는 경우 throw되는 예외입니다.  
  
## 설명  
 이 문제가 발생하는 원인은 다음과 같습니다.  
  
-   원래 인스턴스의 응답이 중지되었습니다.  
  
-   커널 개체를 만들 수 있는 권한이 응용 프로그램에 없습니다.  
  
     커널 개체의 기본 이름은 어셈블리의 GUID, 주 버전 번호 및 부 버전 번호를 연결하여 만들어집니다. 예를 들어, 기본 이름은 3639f15d\-9547\-43da\-8145\-60da347829915.1이 될 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ApplicationServices.CantStartSingleInstanceException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)
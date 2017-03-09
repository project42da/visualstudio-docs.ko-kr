---
title: "MSBuild 오류 MSB1007 | Microsoft Docs"
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
  - "MSBuild.MissingLoggerError"
helpviewer_keywords: 
  - "MSB1007"
ms.assetid: bf45dbc3-50cd-488a-87df-9e647cd71f10
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1007
**로거를 지정하십시오.**  
  
 **\/logger** 스위치에 로거를 지정해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  로거 클래스와 로거 어셈블리를 모두 사용하여 로거를 지정합니다.  `<logger>` 구문은 다음과 같습니다.  
  
     `<logger class>,<logger assembly>[;<logger parameters>]`  
  
     `<logger class>` 구문은 다음과 같습니다.  
  
    ```  
    [<partial or full namespace>.]<logger class name>  
    ```  
  
     `<logger assembly>` 구문은 다음과 같습니다.  
  
    ```  
    {<assembly name>[,<strong name>] | <assembly file>}  
    ```  
  
     `<logger parameters>`은 선택적 요소이며 입력된 그대로 로거에 전달됩니다.  
  
     **\/logger** 스위치의 몇 가지 예는 다음과 같습니다.  
  
     `/logger:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`  
  
     `/logger:XMLLogger,C:\Loggers\MyLogger.dll`  
  
     `/logger:XMLLogger,..  \Loggers\MyLogger.dll;OutputAsHTML`  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
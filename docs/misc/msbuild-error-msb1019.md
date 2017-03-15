---
title: "MSBuild 오류 MSB1019 | Microsoft Docs"
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
  - "MSBuild.InvalidLoggerError"
helpviewer_keywords: 
  - "MSB1019"
ms.assetid: 5d0169f7-f878-433a-ac30-d9d6010130af
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1019
**로거 스위치의 형식이 잘못되었습니다.**  
  
 **\/logger** 스위치를 잘못 지정했습니다.  로거를 지정하려면 적어도 로거 어셈블리는 제공해야 합니다. 로드할 로거를 명시적으로 지정하려면 로거 클래스와 로거 어셈블리를 모두 제공해야 합니다.  로거 매개 변수는 선택 사항입니다.  
  
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
  
     예: \/`logger:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)   
 [빌드 로거](../msbuild/build-loggers.md)
---
title: "MSBuild 오류 MSB1027 | Microsoft Docs"
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
  - "MSBuild.CannotAutoDisableAutoResponseFile"
helpviewer_keywords: 
  - "MSB1027"
ms.assetid: 2ef8d643-616c-4608-be76-5c2c8e18a9e7
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1027
**MSBuild.rsp 자동 지시 파일과 자동 지시 파일에서 참조하는 모든 지시 파일에는 \/noautoresponse 스위치를 지정할 수 없습니다.**  
  
 MSBuild.rsp 파일 또는 MSBuild.rsp 파일에 포함된 다른 지시 파일 안에 **\/noautoresponse** 스위치가 있습니다.  자동 지시 파일은 이 파일 자체를 해제하는 데 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   다른 지시 파일을 지정합니다.  
  
-   MSBuild.rsp 지시 파일에서 **\/noautoresponse** 스위치를 제거합니다.  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
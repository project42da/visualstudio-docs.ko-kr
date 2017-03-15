---
title: "MSBuild 오류 MSB3115 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.InvalidEntryPoint"
helpviewer_keywords: 
  - "MSB3115"
ms.assetid: 7d9d4156-fd6a-455a-8a3d-b191485f1294
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3115
**MSB3115: 파일 '\<file\>'은\(는\) 올바른 진입점이 아닙니다.**  
  
 이 오류는 매니페스트에서 잘못된 진입점을 지정하는 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   매니페스트에서 유효한 진입점을 지정했는지 확인합니다.  응용 프로그램 매니페스트의 경우 유효한 진입점은 .exe 파일입니다.  배포 매니페스트의 경우 유효한 진입점은 응용 프로그램 매니페스트입니다.
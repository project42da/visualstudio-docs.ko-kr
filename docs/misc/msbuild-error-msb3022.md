---
title: "MSBuild 오류 MSB3022 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.Copy.ExactlyOneTypeOfDestination"
helpviewer_keywords: 
  - "MSB3022"
ms.assetid: 74ebcced-8a56-4502-8fef-43d36c79a640
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3022
**프로젝트 파일에서 "'\<attribute\>'"과\(와\) "'\<attribute\>'"을\(를\) 입력 매개 변수로 지정했습니다.  둘 중 하나만 선택하십시오.**  
  
 `Copy` 작업에 대해 `DestinationFiles` 또는 `DestinationDirectory` 작업 특성 중 하나만 지정해야 합니다. 둘 다 지정할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트 파일에서 `Copy` 작업에 대해 `DestinationFiles` 또는 `DestinationDirectory` 중 하나만 지정합니다.  
  
## 참고 항목  
 [Copy Task](../msbuild/copy-task.md)   
 [작업](../msbuild/msbuild-tasks.md)
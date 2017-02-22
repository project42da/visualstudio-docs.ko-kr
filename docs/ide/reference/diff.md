---
title: "/Diff | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
caps.latest.revision: 2
caps.handback.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# /Diff
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

두 파일을 비교합니다.  차이점이 특수 Visual Studio 창에서 표시 됩니다.  
  
## 구문  
  
```  
devenv /Diff SourceFile, TargetFile, [SourceDisplayName],  
[TargetDisplayName]  
```  
  
## 인수  
 `SourceFile`  
 필수 요소.  비교할 첫 번째 파일의 이름 및 전체 경로.  
  
 `TargetFile`  
 필수 요소.  비교할 두 번째 파일의 이름과 전체 경로  
  
 `SourceDisplayName`  
 선택 사항입니다.  첫 번째 파일의 표시 이름입니다.  
  
 `TargetDisplayName`  
 선택 사항입니다.  두 번째 파일의 표시 이름입니다.
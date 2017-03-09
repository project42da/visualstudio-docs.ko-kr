---
title: "MSBuild 오류 MSB3021 | Microsoft Docs"
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
  - "MSBuild.Copy.Error"
helpviewer_keywords: 
  - "MSB3021"
ms.assetid: 8cb3a860-6916-4406-b5c7-b1106b44b92a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3021
**"'\<file\>'" 파일을 "'\<file\>'" 파일로 복사할 수 없습니다. '  \<error\>'**  
  
 `Copy` 작업에서 지정된 파일을 복사할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   대상 파일이 다른 응용 프로그램에서 사용 중이어서 잠겨 있는지 확인하십시오.  원본 파일을 읽고 대상 파일을 대상 폴더에 쓸 수 있는 권한이 있어야 합니다.  대상 파일 경로가 매우 긴 경우에 다른 위치에 복사 해야 합니다.  
  
## 참고 항목  
 [Copy Task](../msbuild/copy-task.md)   
 [작업](../msbuild/msbuild-tasks.md)
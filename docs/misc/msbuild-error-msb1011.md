---
title: "MSBuild 오류 MSB1011 | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.AmbiguousProjectError"
helpviewer_keywords: 
  - "MSB1011"
ms.assetid: f3cb16e5-288c-4dba-941f-a0ed3bf92db7
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB1011
**사용할 프로젝트 또는 솔루션 파일을 지정하십시오. 이 폴더에 프로젝트 또는 솔루션 파일이 두 개 이상 있습니다.**  
  
 명령줄에 프로젝트 파일이 지정되지 않으면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]는 현재 작업 디렉터리에서 파일 확장명이 "proj" 또는 "sln"으로 끝나는 파일을 찾아 사용합니다.  현재 작업 디렉터리에 파일 확장명이 "proj" 또는 "sln"으로 끝나는 파일이 두 개 이상 들어 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  명령줄에 프로젝트 파일 이름을 포함합니다.  예를 들어, `msbuild`를 입력하는 대신 `msbuild myapp.proj`를 입력합니다.  
  
## 참고 항목  
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
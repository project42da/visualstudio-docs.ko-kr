---
title: "MSBuild Response Files | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "response files, MSBuild"
  - "MSBuild, response files"
  - "MSBuild, .rsp files"
  - ".rsp files"
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
caps.latest.revision: 3
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 3
---
# MSBuild Response Files
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지시 파일\(.rsp\)은 MSBuild.exe 명령줄 스위치가 들어 있는 텍스트 파일입니다.  각 스위치가 별도의 줄에 있을 수도 있고 모든 스위치가 한 줄에 있을 수도 있습니다.  주석 줄 앞에는 **\#** 기호가 추가됩니다.  **@** 스위치는 MSBuild.exe에 다른 지시 파일을 전달하는 데 사용됩니다.  
  
 자동 지시 파일은 MSBuild.exe에서 프로젝트를 빌드할 때 자동으로 사용하는 특수한 .rsp 파일입니다.  이 MSBuild.rsp 파일은 MSBuild.exe와 같은 디렉터리에 있어야 합니다. 그렇지 않으면 이 파일을 찾을 수 없습니다.  이 파일을 편집하여 MSBuild.exe에 기본 명령줄 스위치를 지정할 수 있습니다.  예를 들어 프로젝트를 빌드할 때마다 동일한 로거를 사용하는 경우 MSBuild.rsp에 **\/logger** 스위치를 추가하면 MSBuild.exe에서는 프로젝트를 빌드할 때마다 해당 로거를 사용하게 됩니다.  
  
## 참고 항목  
 [MSBuild Reference](../msbuild/msbuild-reference.md)   
 [Command\-Line Reference](../msbuild/msbuild-command-line-reference.md)
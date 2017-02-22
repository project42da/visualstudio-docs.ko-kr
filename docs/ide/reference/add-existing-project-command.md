---
title: "기존 프로젝트 추가 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "file.addexistingproject"
helpviewer_keywords: 
  - "기존 프로젝트 추가 명령"
  - "File.AddExistingProject 명령"
ms.assetid: 71cf3e31-c76b-405b-ad6a-1b1bc654bd40
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 기존 프로젝트 추가 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 솔루션에 기존 프로젝트를 추가합니다.  
  
## 구문  
  
```  
File.AddExistingProject filename  
```  
  
## 인수  
 `filename`  
 선택적 요소.  솔루션에 추가되는 프로젝트의 전체 경로 및 프로젝트 이름\(확장명 포함\)입니다.  
  
 `filename` 인수에 공백이 있으면 인수를 따옴표로 묶어야 합니다.  
  
 파일 이름을 지정하지 않으면 사용자가 프로젝트를 선택할 수 있도록 파일 대화 상자가 열립니다.  
  
## 설명  
 올바른 경로 및 입력한 파일 이름을 찾기 위해 자동 완성 기능이 사용됩니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트인 TestProject1을 현재 솔루션에 추가합니다.  
  
```  
>File.AddExistingProject "c:\visual studio projects\TestProject1.vbproj"  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
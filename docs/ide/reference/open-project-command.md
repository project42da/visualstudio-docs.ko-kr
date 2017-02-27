---
title: "프로젝트 열기 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "file.openproject"
helpviewer_keywords: 
  - "File.OpenProject 명령"
  - "op 명령"
  - "프로젝트 열기 명령"
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 프로젝트 열기 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기존 프로젝트를 엽니다.  
  
## 구문  
  
```  
File.OpenProject filename  
```  
  
## 인수  
 `filename`  
 필수 요소.  열려는 프로젝트의 전체 경로 및 파일 이름입니다.  
  
 `filename` 인수에 대한 구문에서 공백을 포함하는 경로는 따옴표를 사용해야 합니다.  
  
## 설명  
 올바른 경로 및 입력한 파일 이름을 찾기 위해 자동 완성 기능이 사용됩니다.  
  
 이 명령은 디버깅하는 동안 사용할 수 없습니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트인 Test1을 엽니다.  
  
```  
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
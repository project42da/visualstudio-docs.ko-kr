---
title: "솔루션 열기 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "file.opensolution"
helpviewer_keywords: 
  - "File.OpenSolution 명령"
  - "솔루션 열기 명령"
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 솔루션 열기 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기존 솔루션을 열고 열려 있는 다른 솔루션은 닫습니다.  
  
## 구문  
  
```  
File.OpenSolution filename  
```  
  
## 인수  
 `Filename`  
 필수 요소.  열려는 솔루션의 전체 경로와 파일 이름입니다.  
  
 `filename` 인수에 대한 구문에서 공백을 포함하는 경로는 따옴표를 사용해야 합니다.  
  
## 설명  
 올바른 경로 및 입력한 파일 이름을 찾기 위해 자동 완성 기능이 사용됩니다.  
  
## 예제  
 다음 예제에서는 Test1.sln 솔루션을 엽니다.  
  
```  
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
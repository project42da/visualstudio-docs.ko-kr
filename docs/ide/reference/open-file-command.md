---
title: "파일 열기 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "file.openfile"
helpviewer_keywords: 
  - "File.OpenFile 명령"
  - "of 명령"
  - "파일 열기 명령"
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 파일 열기 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기존 파일을 열고 편집기를 지정할 수 있습니다.  
  
## 구문  
  
```  
File.OpenFile filename [/e:editorname]  
```  
  
## 인수  
 `filename`  
 필수 요소.  열려는 파일의 전체 또는 부분 경로와 파일 이름입니다.  공백이 포함된 경로는 따옴표로 묶어야 합니다.  
  
## 스위치  
 \/e:`editorname`  
 선택적 요소.  파일이 열리는 편집기 이름입니다.  인수를 지정하고 편집기 이름을 제공하지 않으면 **연결 프로그램** 대화 상자가 표시됩니다.  
  
 \/E:`editorname`인수구문을 사용 하 여편집기이름을 열려 있는 대화 상자의 따옴표를, 것입니다.  
  
 예를 들어, 소스 코드 편집기에서 파일을 열려면 \/e:`editorname` 인수에 대해 다음과 같이 입력합니다.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## 설명  
 경로를 입력할 때 올바른 경로 및 파일 이름을 찾기 위해 자동 완성 기능이 사용됩니다.  
  
## 예제  
 다음 예제에서는 소스 코드 편집기에서 스타일 파일인 "Test1.css"를 엽니다.  
  
```  
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [직접 실행 창](../../ide/reference/immediate-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
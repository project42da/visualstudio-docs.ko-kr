---
title: "기존 항목 추가 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "project.addexistingitem"
helpviewer_keywords: 
  - "기존 항목 추가 명령"
  - "File.AddExistingItem 명령"
ms.assetid: 41f56131-d4c7-4f81-83b7-bdac713ea870
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 기존 항목 추가 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 솔루션에 기존 파일을 추가하고 엽니다.  
  
## 구문  
  
```  
File.AddExistingItem filename [/e:editorname]  
```  
  
## 인수  
 `filename`  
 필수 요소.  현재 솔루션에 추가되는 항목의 전체 경로 및 파일 이름\(확장명 포함\)입니다.  파일 경로 또는 파일 이름에 공백이 포함된 경우 전체 경로를 따옴표로 묶습니다.  
  
## 스위치  
 \/e: `editorname`  
 선택적 요소.  파일이 열리는 편집기 이름입니다.  인수를 지정하고 편집기 이름을 제공하지 않으면 **연결 프로그램** 대화 상자가 표시됩니다.  
  
 \/e:`editorname` 인수 구문은 **연결 프로그램 대화 상자**에서처럼 따옴표로 묶인 편집기 이름을 사용합니다.  예를 들어, 소스 코드 편집기에서 스타일 시트를 열려면 \/e:`editorname` 인수에 다음과 같이 입력합니다.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## 설명  
 입력할 때 올바른 경로 및 파일 이름을 찾기 위해 자동 완성 기능이 사용됩니다.  
  
## 예제  
 다음 예제에서는 현재 솔루션에 Form1.frm 파일을 추가합니다.  
  
```  
>File.AddExistingItem "C:\public\solution files\Form1.frm"  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
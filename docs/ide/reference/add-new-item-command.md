---
title: "새 항목 추가 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "project.addnewitem"
helpviewer_keywords: 
  - "새 항목 추가 명령"
  - "File.AddNewItem 명령"
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 새 항목 추가 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 솔루션에 .htm, .css, .txt, 프레임셋과 같은 새 솔루션 항목을 추가하고 엽니다.  
  
## 구문  
  
```  
File.AddNewItem [filename] [/t:templatename] [/e:editorname]  
```  
  
## 인수  
 `filename`  
 선택적 요소.  솔루션에 추가되는 항목의 경로 및 파일 이름입니다.  
  
## 스위치  
 \/t: `templatename`  
 선택적 요소.  만들 파일의 형식을 지정합니다.  템플릿 이름을 지정하지 않으면 기본적으로 텍스트 파일이 만들어집니다.  
  
 \/t:`templatename` 인수 구문은 **새 솔루션 항목 추가** 대화 상자에 있는 정보를 미러링합니다.  전체 범주, 파일 형식 순으로 입력해야 하며 범주 이름과 파일 형식은 백슬래시\(`\`\)로 구분하고 전체 문자열은 따옴표로 묶습니다.  
  
 예를 들어, 새 텍스트 파일을 만들려면 \/t:`templatename` 인수에 다음과 같이 입력합니다.  
  
```  
/t:"General\Style Sheet"  
```  
  
 \/e: `editorname`  
 선택적 요소.  파일이 열리는 편집기 이름입니다.  인수를 지정하고 편집기 이름을 제공하지 않으면 **연결 프로그램** 대화 상자가 표시됩니다.  
  
 \/e:`editorname` 인수 구문은 **연결 프로그램 대화 상자**에서처럼 따옴표로 묶인 편집기 이름을 사용합니다.  
  
 예를 들어, 소스 코드 편집기에서 스타일 시트를 열려면 \/e:`editorname` 인수에 다음과 같이 입력합니다.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## 예제  
 다음 예제에서는 현재 솔루션에 새 솔루션 항목인 MyHTMLpg를 추가합니다.  
  
```  
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
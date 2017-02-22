---
title: "새 파일 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "file.newfile"
helpviewer_keywords: 
  - "File.NewFile 명령"
  - "새 파일 명령"
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
caps.latest.revision: 12
caps.handback.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 새 파일 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

새 파일을 만들어 엽니다.  이 파일은 기타 파일 폴더에 표시됩니다.  
  
## 구문  
  
```  
File.NewFile [filename] [/t:templatename] [/editor:editorname]  
```  
  
## 인수  
 `filename`  
 선택적 요소.  파일 이름입니다.  이름을 지정하지 않으면 기본 이름이 사용됩니다.  템플릿 이름을 표시하지 않으면 텍스트 파일이 만들어집니다.  
  
## 스위치  
 \/t:`templatename`  
 선택적 요소.  만들 파일의 형식을 지정합니다.  
  
 \/T:`templatename`인수구문 새 파일 대화 상자에 있는 정보를 미러링합니다.  범주 이름, 백슬래시\(`\`\), 템플릿 이름을 차례로 입력하고 전체 문자열을 따옴표로 묶습니다.  
  
 예를 들어, [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 소스 파일을 새로 만들려면 \/t:`templatename` 인수에 다음과 같이 입력합니다.  
  
```  
/t:"Visual C++\C++ File (.cpp)"  
```  
  
 위의 예제는 C\+\+ 파일 템플릿이 **새 파일** 대화 상자의 Visual C\+\+ 범주에 있음을 나타냅니다.  
  
 \/e:`editorname`  
 선택적 요소.  파일이 열리는 편집기 이름입니다.  인수를 지정하고 편집기 이름을 제공하지 않으면 **연결 프로그램** 대화 상자가 표시됩니다.  
  
 \/E:`editorname`인수구문을 사용 하 여편집기이름을 열려 있는 대화 상자의 따옴표를, 것입니다.  
  
 예를 들어, 소스 코드 편집기에서 파일을 열려면 \/e:`editorname` 인수에 대해 다음과 같이 입력합니다.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## 예제  
 다음 예제에서는 "test1.htm"이라는 새 웹 페이지를 만들어 소스 코드 편집기에서 엽니다.  
  
```  
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [직접 실행 창](../../ide/reference/immediate-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
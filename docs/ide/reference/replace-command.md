---
title: "바꾸기 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "edit.replace"
helpviewer_keywords: 
  - "Edit.Replace 명령"
  - "바꾸기 명령"
ms.assetid: a15767f1-5a3d-44f5-8c77-7b0f1157f340
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 바꾸기 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**찾기 및 바꾸기** 창의 **파일에서 바꾸기** 탭에 있는 옵션의 하위 집합을 사용하여 파일의 텍스트를 바꿉니다.  
  
## 구문  
  
```  
Edit.Replace findwhat replacewith [/all] [/case]  
[/doc|/proc|/open|/sel] [/hidden] [/options] [/reset] [/up]  
[/wild|/regex] [/word]  
```  
  
## 인수  
 `findwhat`  
 필수 요소.  일치시킬 텍스트입니다.  
  
 `replacewith`  
 필수 요소.  일치하는 텍스트를 대신할 텍스트입니다.  
  
## 스위치  
 \/all 또는 \/a 또는 \/모두  
 선택적 요소.  검색 텍스트와 일치하는 모든 항목을 대체 텍스트로 바꿉니다.  
  
 \/case 또는 \/c 또는 \/대\/소문자  
 선택적 요소.  `findwhat` 인수에 지정된 텍스트와 대\/소문자가 정확하게 일치하는 항목만 표시합니다.  
  
 \/doc 또는 \/d 또는 \/문서  
 선택적 요소.  현재 문서만 검색합니다.  사용 가능한 검색 범위인 `/doc`, `/proc`, `/open` 또는 `/sel` 중 하나만 지정합니다.  
  
 \/hidden 또는 \/h 또는 \/숨김  
 선택적 요소.  디자인 타임 컨트롤, 개요 문서의 숨겨진 영역 또는 축소된 클래스나 메서드의 메타데이터처럼 숨겨지거나 축소된 텍스트를 검색합니다.  
  
 \/open 또는 \/o 또는 \/열기  
 선택적 요소.  모든 열린 문서를 마치 한 문서인 것처럼 검색합니다.  사용 가능한 검색 범위인 `/doc`, `/proc`, `/open` 또는 `/sel` 중 하나만 지정합니다.  
  
 \/options 또는 \/t 또는 \/옵션  
 선택적 요소.  현재 찾기 옵션 설정 목록을 표시하며 검색은 수행하지 않습니다.  
  
 \/proc 또는 \/p 또는 \/프로시저  
 선택적 요소.  현재 프로시저만 검색합니다.  사용 가능한 검색 범위인 `/doc`, `/proc`, `/open` 또는 `/sel` 중 하나만 지정합니다.  
  
 \/regex 또는 \/r 또는 \/정규식  
 선택적 요소.  리터럴 문자 대신 텍스트 패턴을 나타내는 표기법으로서 미리 정의된 특수 문자를 `findwhat` 인수에 사용합니다.  전체 정규식 문자 목록을 보려면 [정규식](../../ide/using-regular-expressions-in-visual-studio.md)을 참조하십시오.  
  
 \/reset 또는 \/e 또는 \/다시설정  
 선택적 요소.  찾기 옵션을 기본 설정으로 반환하며 검색은 수행하지 않습니다.  
  
 \/sel 또는 \/s 또는 \/선택  
 선택적 요소.  현재 선택 영역만 검색합니다.  사용 가능한 검색 범위인 `/doc`, `/proc`, `/open` 또는 `/sel` 중 하나만 지정합니다.  
  
 \/up 또는 \/u 또는 \/위로  
 선택적 요소.  파일 내의 현재 위치에서 시작하여 위쪽 방향으로 검색합니다.  기본적으로 파일 내의 현재 위치에서 시작하여 아래쪽 방향으로 검색이 진행됩니다.  
  
 \/wild 또는 \/l 또는 \/와일드카드  
 선택적 요소.  문자 또는 문자 시퀀스를 나타내는 표기법으로서 미리 정의된 특수 문자를 `findwhat` 인수에 사용합니다.  
  
 \/word 또는 \/w 또는 \/단어  
 선택적 요소.  단어 단위로만 검색합니다.  
  
## 예제  
 다음 예제에서는 열려 있는 모든 문서에서 `btnSend`를 `btnSubmit`로 바꿉니다.  
  
```  
>Edit.Replace btnSend btnSubmit /open  
```  
  
## 참고 항목  
 [텍스트 찾기 및 바꾸기](../../ide/finding-and-replacing-text.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
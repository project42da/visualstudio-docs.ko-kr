---
title: "파일에서 찾기 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "edit.findinfiles"
helpviewer_keywords: 
  - "Edit.FindInFiles 명령"
  - "파일에서 찾기 명령"
ms.assetid: 2fc78bfe-b339-4599-97f9-4cafd8a194d9
caps.latest.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 파일에서 찾기 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

**찾기 및 바꾸기** 창의 **파일에서 찾기** 탭에 있는 옵션의 하위 집합을 사용하여 파일을 검색합니다.  
  
## 구문  
  
```  
Edit.FindinFiles findwhat [/case] [/ext:extensions]  
[/lookin:searchpath] [/names] [/options] [/reset] [/stop] [/sub]  
[/text2] [/wild|/regex] [/word]  
```  
  
## 인수  
 `findwhat`  
 필수 요소.  일치시킬 텍스트입니다.  
  
## 스위치  
 \/case 또는 \/c 또는 \/대\/소문자  
 선택적 요소.  `findwhat` 인수에 지정된 텍스트와 대\/소문자가 정확하게 일치하는 항목만 표시합니다.  
  
 \/ext: `extensions`  
 선택적 요소.  검색할 파일에 대한 파일 확장명을 지정합니다.  확장명을 지정하지 않으면 이전에 입력한 확장명이 있는 경우 이 확장명이 사용됩니다.  
  
 \/lookin: `searchpath`  
 선택적 요소.  검색할 디렉터리입니다.  경로에 공백이 포함된 경우 전체 경로를 따옴표로 묶습니다.  
  
 \/names 또는 \/n 또는 \/이름  
 선택적 요소.  일치 항목을 포함하는 파일 이름의 목록을 표시합니다.  
  
 \/options 또는 \/t 또는 \/옵션  
 선택적 요소.  현재 찾기 옵션 설정 목록을 표시하며 검색은 수행하지 않습니다.  
  
 \/regex 또는 \/r 또는 \/정규식  
 선택적 요소.  리터럴 문자 대신 텍스트 패턴을 나타내는 표기법으로서 미리 정의된 특수 문자를 `findwhat` 인수에 사용합니다.  전체 정규식 문자 목록을 보려면 [정규식](../../ide/using-regular-expressions-in-visual-studio.md)을 참조하십시오.  
  
 \/reset 또는 \/e 또는 \/다시설정  
 선택적 요소.  찾기 옵션을 기본 설정으로 반환하며 검색은 수행하지 않습니다.  
  
 \/stop 또는 \/중지  
 선택적 요소.  현재 검색 작업이 진행 중인 경우 이를 중단합니다.  `/stop` 을 지정하면 검색에서 다른 인수는 모두 무시됩니다.  예를 들어, 현재 검색을 중지하려면 다음과 같이 입력합니다.  
  
```  
>Edit.FindinFiles /stop  
```  
  
 \/sub 또는 \/s 또는 \/하위폴더  
 선택적 요소.  \/lookin:`searchpath` 인수에 지정한 디렉터리의 하위 폴더를 검색합니다.  
  
 \/text2 또는 \/2 또는 \/찾기2에표시  
 선택적 요소.  찾기 결과 2 창에 검색 결과를 표시합니다.  
  
 \/wild 또는 \/l 또는 \/와일드카드  
 선택적 요소.  문자 또는 문자 시퀀스를 나타내는 표기법으로서 미리 정의된 특수 문자를 `findwhat` 인수에 사용합니다.  
  
 \/word 또는 \/w 또는 \/단어  
 선택적 요소.  단어 단위로만 검색합니다.  
  
## 예제  
 다음 예제에서는 "My Visual Studio Projects" 폴더에 있는 모든 .cls 파일에서 btnCancel을 검색하고 찾기 결과 2 창에 일치 항목 정보를 표시합니다.  
  
```  
>Edit.FindinFiles btnCancel /lookin:"c:/My Visual Studio Projects" /ext:*.cls /text2  
```  
  
## 참고 항목  
 [파일에서 찾기](../../ide/find-in-files.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
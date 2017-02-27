---
title: "디스어셈블리 목록 표시 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.listdisassembly"
helpviewer_keywords: 
  - "Debug.ListDisassembly 명령"
  - "디스어셈블리 목록 표시 명령"
ms.assetid: eb363e35-e86a-4121-966f-991210c27e2a
caps.latest.revision: 13
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 13
---
# 디스어셈블리 목록 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 프로세스를 시작하고 오류를 처리하는 방법을 지정할 수 있습니다.  
  
## 구문  
  
```  
Debug.ListDisassembly [/count:number] [/endaddress:expression]  
[/codebytes:yes|no] [/source:yes|no] [/symbolnames:yes|no]  
[/linenumbers:yes|no]  
```  
  
## 스위치  
 완전한 형식이나 약식 표현을 사용하여 각 스위치를 호출할 수 있습니다.  
  
 \/count: `number` \[또는\] \/c: `number` \[또는\] \/length: `number` \[또는\] \/l: `number`  
 선택적 요소.  표시할 명령의 수 입니다.  기본값은 8입니다.  
  
 \/endaddress: `expression` \[또는\] \/e: `expression`  
 선택적 요소.  디스어셈블리를 중지할 주소입니다.  
  
 \/codebytes:`yes`&#124;`no` \[또는\] \/bytes:`yes`&#124;`no` \[또는\] \/b:`yes`&#124;`no`  
 선택적 요소.  코드 바이트를 표시할지 여부를 나타냅니다.  기본값은 `no`으로,  
  
 \/source:`yes`&#124;`no` \[또는\] \/s:`yes`&#124;`no`  
 선택적 요소.  소스 코드를 표시할지 여부를 나타냅니다.  기본값은 `no`으로,  
  
 \/symbolnames:`yes`&#124;`no` \[또는\] \/names:`yes`&#124;`no` \[또는\] \/n:`yes`&#124;`no`  
 선택적 요소.  기호 이름을 표시할지 여부를 나타냅니다.  기본값은 `yes`으로,  
  
 \[\/linenumbers:`yes`&#124;`no`\]  
 선택적 요소.  소스 코드와 연결된 줄 번호를 표시합니다.  \/source 스위치에 `yes` 값이 있어야 \/linenumbers 스위치를 사용할 수 있습니다.  
  
## 예제  
  
```  
>Debug.ListDisassembly  
```  
  
## 참고 항목  
 [호출 스택 목록 표시 명령](../../ide/reference/list-call-stack-command.md)   
 [스레드 목록 표시 명령](../../ide/reference/list-threads-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
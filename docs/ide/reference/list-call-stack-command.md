---
title: "호출 스택 목록 표시 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.listcallstack"
helpviewer_keywords: 
  - "Debug.ListCallStack 명령"
  - "호출 스택 목록 표시 명령"
ms.assetid: a8b20bf2-81d2-4069-aea8-23e6b15b4347
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 12
---
# 호출 스택 목록 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

현재 호출 스택을 표시합니다.  
  
## 구문  
  
```  
Debug.ListCallStack [/Count:number] [/ShowTypes:yes|no]  
[/ShowNames:yes|no] [/ShowValues:yes|no] [/ShowModule:yes|no]  
[/ShowLineOffset:yes|no] [/ShowByteOffset:yes|no]  
[/ShowLanguage:yes|no] [/IncludeCallsAcrossThreads:yes|no]  
[/ShowExternalCode:yes|no] [Thread:n] [index]  
```  
  
## 인수  
 `index`  
 선택적 요소.  현재 스택 프레임을 설정하며 출력을 표시하지 않습니다.  
  
## 스위치  
 완전한 형식이나 약식 표현을 사용하여 각 스위치를 호출할 수 있습니다.  
  
 \/Count:`number` \[또는\] \/C:`number`  
 선택적 요소.  표시할 호출 스택의 최대 개수입니다.  기본값은 제한 없음입니다.  
  
 \/ShowTypes:`yes`&#124;`no` \[또는\] \/T:`yes`&#124;`no`  
 선택적 요소.  매개 변수 형식을 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/ShowNames:`yes`&#124;`no` \[또는\] \/N:`yes`&#124;`no`  
 선택적 요소.  매개 변수 이름을 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/ShowValues:`yes`&#124;`no` \[또는\] \/V:`yes`&#124;`no`  
 선택적 요소.  매개 변수 값을 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/ShowModule:`yes`&#124;`no` \[또는\] \/M:`yes`&#124;`no`  
 선택적 요소.  모듈 이름을 표시할지 여부를 지정합니다.  기본값은 `yes`으로,  
  
 \/ShowLineOffset:`yes`&#124;`no` \[또는\] \/\#:`yes`&#124;`no`  
 선택적 요소.  줄 오프셋을 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/ShowByteOffset:`yes`&#124;`no` \[또는\] \/B:`yes`&#124;`no`  
 선택적 요소.  바이트 오프셋을 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/ShowLanguage:`yes`&#124;`no` \[또는\] \/L:`yes`&#124;`no`  
 선택적 요소.  언어를 표시할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/IncludeCallsAcrossThreads:`yes`&#124;`no` \[또는\] \/I:`yes`&#124;`no`  
 선택적 요소.  다른 스레드와의 호출을 포함할지 여부를 지정합니다.  기본값은 `no`으로,  
  
 \/ShowExternalCode:`yes`&#124;`no`  
 선택적 요소.  호출 스택에 대해 내 코드만 표시할지 여부를 지정합니다.  내 코드만을 해제하면 사용자가 작성하지 않은 코드가 모두 표시됩니다.  내 코드만을 설정하면 호출 스택 출력에 사용자가 작성하지 않은 코드가 `[external]`로 표시됩니다.  
  
 Thread:`n`  
 선택적 요소.  스레드 `n`의 호출 스택을 표시합니다.  스레드를 지정하지 않으면 현재 스레드의 호출 스택을 표시합니다.  
  
## 설명  
 인수 또는 스위치에 대한 변경 내용은 다음에 이 명령을 호출할 때 적용됩니다.  디버그.호출스택목록표시만 `` 실행하는 경우 전체 호출 스택이 표시됩니다.  예를 들어, 다음과 같이 인덱스를 지정하면  
  
```  
Debug.ListCallStack 2  
```  
  
 현재 스택 프레임이 해당 프레임\(이 경우 둘째 프레임\)으로 설정됩니다.  
  
 미리 정의된 별칭인 kb를 사용하여 이 명령을 작성할 수도 있습니다.  예를 들어, 다음을 입력하여  
  
```  
kb 2  
```  
  
 현재 스택 프레임을 둘째 프레임으로 설정할 수 있습니다.  
  
## 예제  
  
```  
>Debug.CallStack /Count:4 /ShowTypes:yes  
```  
  
## 참고 항목  
 [디스어셈블리 목록 표시 명령](../../ide/reference/list-disassembly-command.md)   
 [스레드 목록 표시 명령](../../ide/reference/list-threads-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
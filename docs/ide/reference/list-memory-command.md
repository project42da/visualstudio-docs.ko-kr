---
title: "메모리 목록 표시 명령 | Microsoft Docs"
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
  - "debug.listmemory"
helpviewer_keywords: 
  - "Debug.ListMemory 명령"
  - "메모리 목록 표시 명령"
  - "ListMemory 명령"
ms.assetid: a84de361-a6a6-4f6d-96aa-a0d4a424371e
caps.latest.revision: 11
caps.handback.revision: 11
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 메모리 목록 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 범위의 메모리 내용을 표시합니다.  
  
## 구문  
  
```  
Debug.ListMemory [/ANSI|Unicode] [/Count:number] [/Format:formattype]  
[/Hex|Signed|Unsigned] [expression]  
```  
  
## 인수  
 `expression`  
 선택적 요소.  메모리 표시를 시작할 메모리 주소입니다.  
  
## 스위치  
 \/ANSI&#124;Unicode  
 선택적 요소.  메모리 바이트\(ANSI 또는 유니코드\)에 해당하는 문자로 메모리를 표시합니다.  
  
 \/Count:`number`  
 선택적 요소.  `expression`에서부터 시작하여 표시되는 메모리 바이트 수를 결정합니다.  
  
 \/Format:`formattype`  
 선택적 요소.  **메모리** 창에 메모리 정보를 표시하는 형식으로서 1바이트, 2바이트, 4바이트, 8바이트, Float\(32비트\) 또는 Double\(64비트\)이 있습니다.  1바이트를 사용하는 경우에는 `/Unicode`를 사용할 수 없습니다.  
  
 \/Hex&#124;Signed&#124;Unsigned  
 선택적 요소.  숫자 보기 형식을 부호 있는 형식, 부호 없는 형식, 또는 16진수로 지정합니다.  
  
## 설명  
 모든 스위치와 함께 전체 **Debug.ListMemory** 명령을 작성하는 대신, 특정 스위치가 지정된 값으로 미리 설정되어 있는 미리 정의된 별칭을 사용하여 명령을 호출할 수 있습니다.  예를 들면, 다음과 같습니다.  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
 다음 코드를 작성할 수 있습니다.  
  
```  
>df /Count:30 /Unicode  
```  
  
 다음은 **Debug.ListMemory** 명령에 사용할 수 있는 별칭 목록입니다.  
  
|Alias|명령 및 스위치|  
|-----------|--------------|  
|**d**|디버그.메모리목록표시|  
|**da**|디버그.메모리목록표시 \/Ansi|  
|**db**|디버그.메모리목록표시 \/Format:OneByte|  
|**dc**|디버그.메모리목록표시 \/Format:FourBytes \/Ansi|  
|**dd**|디버그.메모리목록표시 \/Format:FourBytes|  
|**df**|디버그.메모리목록표시 \/Format:Float|  
|**dq**|디버그.메모리목록표시 \/Format:EightBytes|  
|**du**|디버그.메모리목록표시 \/Unicode|  
  
## 예제  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
## 참고 항목  
 [호출 스택 목록 표시 명령](../../ide/reference/list-call-stack-command.md)   
 [스레드 목록 표시 명령](../../ide/reference/list-threads-command.md)   
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [명령 창](../../ide/reference/command-window.md)   
 [찾기\/명령 상자](../../ide/find-command-box.md)   
 [Visual Studio 명령 별칭](../../ide/reference/visual-studio-command-aliases.md)
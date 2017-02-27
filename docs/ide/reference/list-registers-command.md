---
title: "레지스터 목록 표시 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "debug.listregisters"
helpviewer_keywords: 
  - "Debug.ListRegisters 명령"
  - "레지스터 열거 명령"
  - "ListRegisters 명령"
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
caps.latest.revision: 7
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# 레지스터 목록 표시 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

선택한 레지스터의 값을 표시하고 표시할 레지스터 목록을 수정할 수 있게 합니다.  
  
## 구문  
  
```  
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]  
[/Watch [{register|registerGroup}...]]  
[/Unwatch [{register|registerGroup}...]]  
```  
  
## 스위치  
 \/Display \[{`register`&#124;`registerGroup`}...\]  
 지정한 `register`나 `registerGroup`의 값을 표시합니다.  `register`나 `registerGroup`이 지정되지 않은 경우 레지스터의 기본 목록이 표시됩니다.  스위치가 지정되지 않으면 동작이 동일합니다.  예를 들면 다음과 같습니다.  
  
 `Debug.ListRegisters /Display eax`  
  
 동일한 함수는  
  
 `Debug.ListRegisters eax`  
  
 \/List  
 모든 레지스터 그룹을 목록에 표시합니다.  
  
 \/Watch \[{`register`&#124;`registerGroup`}...\]  
 하나 이상의 `register` 또는 `registerGroup` 값을 목록에 추가합니다.  
  
 \/Unwatch \[{`register`&#124;`registerGroup`}...\]  
 하나 이상의 `register` 또는 `registerGroup` 값을 목록에서 제거합니다.  
  
## 설명  
 `r` 별칭을 `Debug.ListRegisters` 대신 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `Debug.ListRegisters` 별칭 `r`를 사용하여 레지스터 그룹 `Flags`의 값을 표시합니다.  
  
```  
r /Display Flags  
```  
  
## 참고 항목  
 [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)   
 [디버깅 기본 사항: 레지스터 창](../../debugger/debugging-basics-registers-window.md)   
 [방법: 레지스터 창 사용](../../debugger/how-to-use-the-registers-window.md)